# Payroll System Analysis and Design (Phân tích và thiết kế hệ thống Payroll System)

## 1. Phân tích kiến ​​trúc

### 1.1. Kiến trúc đề xuất
Kiến trúc được đề xuất cho Hệ thống Payroll System là **Kiến trúc 3 tầng**. Mô hình này chia hệ thống thành ba lớp chính, đảm bảo khả năng mở rộng, khả năng bảo trì và đáp ứng các yêu cầu kinh doanh của hệ thống.

- **Presentation Layer**:
  + Giao diện người dùng mà nhân viên và quản trị viên tương tác, cho phép nhập dữ liệu và truy vấn dữ liệu.
  + Hỗ trợ các tác vụ như gửi thẻ chấm công, chọn phương thức thanh toán và xem báo cáo.
    
- **Business Logic Layer**:
  + Chịu trách nhiệm thực hiện logic kinh doanh cốt lõi của hệ thống, bao gồm:
  + Tính toán bảng lương tự động.
  + Xử lý thẻ chấm công và quản lý đơn hàng.
  + Quản lý và xác minh thông tin thanh toán.
  + Được triển khai dưới dạng dịch vụ trên máy chủ trung tâm, xử lý các đợt chạy bảng lương theo lịch trình.

- **Data Access Layer**:
  + Quản lý việc lưu trữ và truy xuất dữ liệu nhân viên, thông tin bảng lương, thẻ chấm công và các dữ liệu liên quan khác trong DB2 database.
  + Giao tiếp với cơ sở dữ liệu quản lý dự án hiện có mà không làm gián đoạn hệ thống hiện tại.

### 1.2. Cơ sở lý luận cho sự lựa chọn kiến ​​trúc
- **Khả năng mở rộng**:  
  + Kiến trúc 3 lớp cho phép mỗi lớp có thể được mở rộng độc lập, cho phép nâng cấp giao diện mà không ảnh hưởng đến logic kinh doanh hoặc các lớp database.
  
- **Khả năng bảo trì**:  
  + Phân tách rõ ràng interface, business logic, và data access giúp phát triển và bảo trì dễ dàng hơn.

- **Yêu cầu bảo mật**:  
  + Bằng cách hạn chế quyền truy cập vào các lớp Business Logic và Data Access layers, dữ liệu nhạy cảm sẽ được bảo vệ, đảm bảo chỉ những người dùng được ủy quyền mới có thể truy cập thông tin cần thiết.

- **Tích hợp hệ thống**:  
  + Lớp data access được thiết kế để tương tác với DB2 database cũ, bảo toàn hệ thống hiện tại và tiết kiệm chi phí.

### 1.3. Giải thích từng thành phần
1. **Client Layer**:
    - Giao diện nơi nhân viên và quản trị viên tương tác với hệ thống.
    - Ví dụ: Nhân viên gửi thẻ chấm công, chọn phương thức thanh toán; quản trị viên thêm nhân viên mới hoặc tạo báo cáo.
2. **Application Layer**:
   - Quản lý các quy trình như:
      + Tính lương dựa trên giờ làm việc, đơn đặt hàng và loại nhân viên.
      + Xác thực các điều kiện cho thẻ chấm công và phương thức thanh toán.
      + Thực hiện lịch trình tính lương tự động để đảm bảo thanh toán kịp thời.

3. **Database Layer**:
    - Chịu trách nhiệm lưu trữ và quản lý dữ liệu.
    - Đảm bảo các yêu cầu như:
      + Truy xuất dữ liệu nhân viên và dự án từ DB2 database.
      + Lưu trữ dữ liệu bảng lương, thẻ chấm công và báo cáo.

### 1.4. Package Diagram (Biểu đồ gói)
Sơ đồ gói bên dưới hiển thị các thành phần chính và mối quan hệ của chúng:
![Diagram](https://www.planttext.com/api/plantuml/png/V5D1JiCm4Bpx5LOlmA52ujW3AhG7aAY42eZprjbI2ySEkqwh2FLb77WINy19ar8NDpvwPcTdP-sVh-ynUo1VvaOKeDxX3ULWOZHQBn-WGXh8Jo73KGQOvU25aUIzzKXBKDY1kwDjKVfddQC2oiul3X16Wye_GfK7tHdwbOlnZnAfccFXoBVtMx4LVuPkYi9e1LuxctGLbCaP8oTWL6aQNcnDjG3UkP9CzHfKENAm9po10TAOzL0cBiyrSsYoDtlWfGj0pi06ZNhYs0l36fCfhS7eBEWVWTkZIMl5a-85EONCBItsx-nIKvxQGfps53miW34PzVJsIdQ4excy8woXg2kX3t6k3u6csvcSusvJlD85omNw3QBTjK6MO3FPEcBnxzaDXzSdjZwI9P-iIEwcjoALTrUGxDzKnI6DGWYGNMv8UnHf3ycg9b2HjD335sEqMVsTVm400F__0m00)



## 2. Cơ chế phân tích
### 2.1. Cơ chế chính cho hệ thống
Các cơ chế chính sau đây được xác định cho "Payroll System" dựa trên các yêu cầu của hệ thống:

- **Automated Payroll Calculation (Tính toán tiền lương tự động)**:
  + Tự động tính lương cho nhiều loại nhân viên khác nhau (theo giờ, theo lương tháng và theo hoa hồng).
  + Xử lý giờ làm thêm cho nhân viên theo giờ.
  + Lên lịch chạy bảng lương thường xuyên (hàng tuần và hàng tháng).
    
- **Timecard Management (Quản lý thẻ chấm công)**:
  + Thu thập, lưu trữ và xác thực dữ liệu thẻ chấm công của nhân viên.
  + Hỗ trợ xử lý thẻ chấm công điện tử và tích hợp tự động với tính toán bảng lương.
    
- **Payment Options (Tùy chọn thanh toán)**:
  + Cung cấp ba phương thức thanh toán: gửi tiền trực tiếp, gửi séc qua thư hoặc nhận trực tiếp.
  + Hỗ trợ yêu cầu thay đổi phương thức thanh toán của nhân viên.
    
- **System Integration (Tích hợp hệ thống)**:
  + Giao tiếp với cơ sở dữ liệu quản lý dự án DB2 hiện có để lấy thông tin và chi phí liên quan đến dự án mà không làm gián đoạn hệ thống cũ.
    
- **Employee Reports (Báo cáo nhân viên)**:
  + Cung cấp báo cáo chi tiết về:
  + Tổng giờ làm việc.
  + Tổng tiền lương nhận được.
  + Thời gian nghỉ phép còn lại.
  + Báo cáo phải có thể truy cập nhanh chóng và an toàn.
 
- **System Security (Hệ thống bảo mật)**:
  + Đảm bảo rằng mỗi nhân viên chỉ có thể truy cập thông tin của họ.
  + Hạn chế quyền chỉnh sửa cho những người quản trị được ủy quyền.

### 2.2. Cơ sở lý luận cho các cơ chế
- **Automated Payroll Calculation (Tính toán tiền lương tự động)**:
  Đáp ứng nhu cầu xử lý tính lương nhanh chóng và chính xác cho hơn 5.000 nhân viên, giảm thiểu sai sót thủ công.
  
- **Timecard Management (Quản lý thẻ thời gian)**:
  Cần thiết để xử lý các loại thẻ chấm công khác nhau (theo giờ, lương) và ghi lại thông tin liên quan đến dự án.
  
- **Payment Options (Tùy chọn thanh toán)**:
  Cung cấp sự linh hoạt và cá nhân hóa cho nhân viên.

- **System Integration (Tích hợp hệ thống)**:
  Tận dụng cơ sở dữ liệu hiện có để giảm chi phí và duy trì tính nhất quán của dữ liệu.

- **Employee Reports (Báo cáo nhân viên)**:
  Đáp ứng nhu cầu truy xuất thông tin nhanh chóng, cung cấp các số liệu quan trọng cho nhân viên.
  
- **System Security (Bảo mật hệ thống)**:
  Đảm bảo bảo vệ dữ liệu, bảo mật các thông tin nhạy cảm (tiền lương, thông tin cá nhân) của từng nhân viên.
  
### 2.3. Danh sách các cơ chế
- Tính toán tiền lương tự động: Lên lịch và tự động tính lương cho mọi loại nhân viên, bao gồm cả xử lý làm thêm giờ.
- Quản lý thẻ chấm công: Thu thập, lưu trữ và xác thực dữ liệu thẻ chấm công; xử lý dữ liệu cho nhân viên theo giờ.
- Tùy chọn thanh toán: Hỗ trợ ba phương thức thanh toán với các tùy chọn chuyển đổi linh hoạt.
- Tích hợp hệ thống: Giao diện với cơ sở dữ liệu DB2 hiện có mà không bị gián đoạn.
- Báo cáo nhân viên: Tạo báo cáo nhanh chóng, chi tiết và dễ truy cập.
- Hệ thống bảo mật: Đảm bảo hạn chế truy cập và mã hóa dữ liệu nhạy cảm.
