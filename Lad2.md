# PAYROLL SYSTEM ARCHITECURAL ANALYSIS SOLUTION
## Phân tích và Mô phỏng Ca Sử Dụng Maintain Timecard trong Hệ Thống Lương
### 1. Phân tích các Ca Sử Dụng Còn Lại
- **Quản lý Thông tin Nhân Viên**
  - Thêm mới nhân viên:
    - Thu thập thông tin cơ bản: Họ tên, ngày sinh, số CMND, địa chỉ, số điện thoại, email, phòng ban, chức vụ, ngày vào làm, mức lương cơ bản, tài khoản ngân hàng,...
    - Kiểm tra tính hợp lệ của dữ liệu nhập vào.
    - Lưu thông tin vào cơ sở dữ liệu.
      
  - Cập nhật thông tin nhân viên:
    - Cho phép cập nhật mọi thông tin của nhân viên (trừ mã nhân viên).
    - Kiểm tra tính hợp lệ của dữ liệu mới.
    - Cập nhật thông tin vào cơ sở dữ liệu.
      
  - Xóa nhân viên:
    - Xóa thông tin nhân viên khỏi cơ sở dữ liệu.
    - Cân nhắc các trường hợp đặc biệt: nhân viên đang có dự án, nhân viên đã nghỉ việc nhưng vẫn cần lưu trữ thông tin,...
      
- **Quản lý Dự Án**
  - Thêm mới dự án:
    -Thu thập thông tin về dự án: tên dự án, mô tả, ngày bắt đầu, ngày kết thúc, người quản lý,...
    - Liên kết dự án với các nhân viên tham gia.
    - Lưu thông tin vào cơ sở dữ liệu.
  - Cập nhật thông tin dự án:
    - Cho phép cập nhật mọi thông tin về dự án.
    - Cập nhật thông tin vào cơ sở dữ liệu.
  - Xóa dự án:
    - Xóa thông tin dự án khỏi cơ sở dữ liệu.
    - Cân nhắc các trường hợp đặc biệt: dự án đang diễn ra, dự án đã hoàn thành nhưng cần lưu trữ thông tin,...
  - Quản lý Mã Công Việc
    - Thêm mới mã công việc:
    - Thu thập thông tin về mã công việc: tên mã, mô tả công việc, mức lương cho mỗi giờ làm việc,...
    - Liên kết mã công việc với các dự án.
    - Lưu thông tin vào cơ sở dữ liệu.
  - Cập nhật thông tin mã công việc:
    - Cho phép cập nhật mọi thông tin về mã công việc.
    - Cập nhật thông tin vào cơ sở dữ liệu.
  - Xóa mã công việc:
    - Xóa thông tin mã công việc khỏi cơ sở dữ liệu.
    - Cân nhắc các trường hợp đặc biệt: mã công việc đang được sử dụng trong các dự án,...
- **Tính Lương**
  - Tính toán lương:
    - Lấy thông tin từ thẻ chấm công, mức lương cơ bản, phụ cấp, và các khoản khấu trừ.
    - Áp dụng các công thức tính lương theo quy định của công ty.
    - Tính tổng thu nhập và tổng khấu trừ.
  - Tạo phiếu lương:
    - Hiển thị chi tiết các khoản thu nhập và khấu trừ.
    - Cho phép in hoặc xuất file phiếu lương.
- **Báo cáo**
  - Báo cáo tổng hợp lương:
    - Tổng hợp thông tin lương của tất cả nhân viên trong một khoảng thời gian nhất định.
    - Hiển thị tổng chi phí lương, số lượng nhân viên, mức lương trung bình,...
  - Báo cáo chi tiết lương theo nhân viên:
    - Hiển thị chi tiết các khoản thu nhập và khấu trừ của từng nhân viên.
  - Báo cáo số giờ làm việc:
    - Hiển thị số giờ làm việc của từng nhân viên trong một khoảng thời gian nhất định.
    - Phân tích hiệu suất làm việc của nhân viên.
- **Quản lý Quyền Hạn**
  - Cấp quyền:
    - Xác định các vai trò người dùng (admin, quản lý, nhân viên).
    - Cấp quyền truy cập vào các chức năng khác nhau cho từng vai trò.
  - Thu hồi quyền:
    - Thu hồi quyền truy cập của người dùng khi cần thiết.

  
