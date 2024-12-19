# BÁO CÁO CUỐI KỲ
# Mentcare: A mental health support system

## MỤC LỤC
**Mô tả công việc**  
- Thông tin thành viên nhóm, vai trò  
- Phân công công việc và mức độ hoàn thành  

**1. Mô tả tóm tắt bài toán**  
- Sự cần thiết, lợi ích khi giải quyết bài toán  
- Các yêu cầu chức năng  
- Các yêu cầu phi chức năng  

**2. Phân tích các ca sử dụng**  
- Kiến trúc đề xuất  
- Các cơ chế phân tích  
- Kết quả phân tích từng ca sử dụng  
    - Kết quả phân tích ca sử dụng 1  
    - Kết quả phân tích ca sử dụng 2  
    - Kết quả phân tích ca sử dụng 3, …  

**3. Xác định các phần tử thiết kế**  
**4. Thiết kế hệ thống con**  
**5. Thiết kế các lớp**  
**6. Kết luận**

---

## Mô tả công việc
### Thông tin thành viên nhóm, vai trò
- **Phan Thành Danh** - 4551190006 - Nhóm trưởng  
- **Thái Sinh Gia Bảo** - 4551190003 - Thành viên  
- **Trần Quốc Khánh** - 4551190031 - Thành viên  
- **Văn Vũ Bảo Ngọc** - 4551190038 - Thành viên  

### Phân công công việc và mức độ hoàn thành
| **Thành viên**          | **Công việc**                      | **Tiến độ**     |
|-------------------------|------------------------------------|-----------------|
| Trần Quốc Khánh         | 1. Mô tả tóm tắt bài toán          | Hoàn thành      |
| Phan Thành Danh         | 2. Phân tích các ca sử dụng        | Hoàn thành      |
| Thái Sinh Gia Bảo       | 3. Xác định các phần tử thiết kế   | Hoàn thành      |
| Văn Vũ Bảo Ngọc         | 4. Thiết kế hệ thống con           | Hoàn thành      |
| Cả nhóm                 | 5. Thiết kế các lớp                | Hoàn thành      |
|                         | 6. Kết luận                        | Hoàn thành      |

---

## 1. Mô tả tóm tắt bài toán
### Sự cần thiết khi giải quyết bài toán Mentcare
- **Đảm bảo an toàn cho bệnh nhân và nhân viên y tế**:  
Với tính chất là một hệ thống an toàn thứ cấp, sự thất bại của Mentcare có thể dẫn đến hậu quả nghiêm trọng như sai sót trong điều trị, gây nguy hiểm cho cả bệnh nhân và nhân viên y tế.  

- **Quản lý thông tin chuyên biệt cho sức khỏe tâm thần**:  
Việc thiết kế hệ thống chuyên biệt giúp theo dõi sát sao tình trạng bệnh nhân, từ đó hỗ trợ quá trình điều trị hiệu quả hơn.  

- **Tuân thủ các quy định pháp luật**:  
Một hệ thống như Mentcare cần đảm bảo sự tuân thủ luật pháp về bảo mật, quyền riêng tư và quản lý hồ sơ.  

- **Hỗ trợ ra quyết định y tế**:  
Hệ thống cung cấp thông tin chi tiết và chính xác, hỗ trợ các bác sĩ đưa ra quyết định điều trị hiệu quả.

### Lợi ích khi giải quyết bài toán Mentcare
- Cải thiện chất lượng chăm sóc sức khỏe tâm thần.  
- Bảo mật và quản lý dữ liệu tốt hơn.  
- Tăng cường sự an toàn.  
- Tiết kiệm thời gian và nguồn lực.  
- Giải quyết xung đột giữa bảo mật và an toàn.  
- Tạo tiền đề cho các nghiên cứu và cải tiến.  
- Ứng dụng trong đào tạo và phát triển chuyên môn.  

---

### Các yêu cầu chức năng (Functional Requirements)
- **Quản lý thông tin bệnh nhân**:  
    - Tạo, cập nhật, lưu trữ hồ sơ bệnh nhân.  
    - Theo dõi lịch sử khám bệnh và đơn thuốc.  

- **Hỗ trợ chẩn đoán và điều trị**:  
    - Hiển thị tác dụng phụ của thuốc và cảnh báo dị ứng.  
    - Theo dõi rủi ro tự tử hoặc nguy hiểm của bệnh nhân.  

- **Hỗ trợ báo cáo**:  
    - Tạo báo cáo cá nhân hóa và ẩn danh.  

- **Hỗ trợ quản lý cuộc hẹn**:  
    - Tích hợp đặt lịch hẹn và theo dõi vắng mặt.  

- **Hỗ trợ nhân viên y tế di động**:  
Cho phép tải xuống, cập nhật và đồng bộ hồ sơ trên máy tính xách tay.

---

### Các yêu cầu phi chức năng (Non-functional Requirements)
- **Hiệu suất**: Phản hồi trong vòng 2 giây.  
- **Bảo mật**: Mã hóa dữ liệu và kiểm soát truy cập dựa trên vai trò.  
- **Quyền riêng tư**: Tuân thủ Đạo luật Bảo vệ Dữ liệu 1998.  
- **Khả năng tương tác**: Tích hợp với hệ thống hồ sơ bệnh nhân quốc gia.  
- **An toàn**: Cảnh báo rủi ro như tự tử, bạo lực, hoặc tác dụng phụ.  
- **Sử dụng**: Giao diện dễ sử dụng và giảm thiểu sai sót người dùng.  

---

## 2. Phân tích các ca sử dụng
### Kiến trúc đề xuất
Hệ thống Mentcare được thiết kế dựa trên **kiến trúc 3 lớp**:
- **Lớp giao diện (Presentation Layer)**:  
Hiển thị thông tin và tương tác với người dùng.  

- **Lớp xử lý nghiệp vụ (Business Logic Layer)**:  
Xử lý các quy trình nghiệp vụ như chẩn đoán, điều trị, và quản lý cuộc hẹn.  

- **Lớp dữ liệu (Data Layer)**:  
Lưu trữ và truy xuất cơ sở dữ liệu bệnh nhân, báo cáo và lịch hẹn.  

### Mô hình triển khai (Deployment)
- **Máy chủ trung tâm**: Hệ điều hành Linux, bộ nhớ 32GB.  
- **Máy trạm người dùng**: Máy tính của bác sĩ và nhân viên y tế.  
- **Máy tính xách tay di động**: Hỗ trợ khám bệnh tại nhà với chức năng đồng bộ dữ liệu.  
