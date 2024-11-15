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
  - Lớp data access được thiết kế để tương tác với DB2 database cũ, bảo toàn hệ thống hiện tại và tiết kiệm chi phí.

### 1.3. Explanation of Each Component
1. **Client Layer**:
   - The interface where employees and administrators interact with the system.
   - Examples: Employees submit timecards, select payment methods; administrators add new employees or generate reports.

2. **Application Layer**:
   - Manages processes such as:
     - Calculating wages based on working hours, orders, and employee type.
     - Validating conditions for timecards and payment methods.
   - Executes automated payroll schedules to ensure timely payments.

3. **Database Layer**:
   - Responsible for storing and managing data.
   - Ensures requirements such as:
     - Retrieving employee and project data from the DB2 database.
     - Storing payroll data, timecards, and reports.

### 1.4. Package Diagram
The package diagram below shows the main components and their relationships:
![Diagram](https://www.planttext.com/api/plantuml/png/V5D1JiCm4Bpx5LOlmA52ujW3AhG7aAY42eZprjbI2ySEkqwh2FLb77WINy19ar8NDpvwPcTdP-sVh-ynUo1VvaOKeDxX3ULWOZHQBn-WGXh8Jo73KGQOvU25aUIzzKXBKDY1kwDjKVfddQC2oiul3X16Wye_GfK7tHdwbOlnZnAfccFXoBVtMx4LVuPkYi9e1LuxctGLbCaP8oTWL6aQNcnDjG3UkP9CzHfKENAm9po10TAOzL0cBiyrSsYoDtlWfGj0pi06ZNhYs0l36fCfhS7eBEWVWTkZIMl5a-85EONCBItsx-nIKvxQGfps53miW34PzVJsIdQ4excy8woXg2kX3t6k3u6csvcSusvJlD85omNw3QBTjK6MO3FPEcBnxzaDXzSdjZwI9P-iIEwcjoALTrUGxDzKnI6DGWYGNMv8UnHf3ycg9b2HjD335sEqMVsTVm400F__0m00)

