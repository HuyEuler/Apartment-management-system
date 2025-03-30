# Functional Requirements - Yêu cầu chức năng 

## 1. User Management
- Hệ thống hỗ trợ đăng nhập và phân quyền cho:
  - Ban quản lý chung cư (Admin)
  - Nhân viên hỗ trợ (Staff)
- Quản lý thông tin tài khoản: Tạo, sửa, xóa, reset mật khẩu.

## 2. Resident Management
- Thêm mới cư dân với thông tin:
  - Họ và tên
  - Căn hộ
  - Số điện thoại
  - Email
  - Ngày vào ở
- Cập nhật thông tin cư dân.
- Xóa cư dân khi đã chuyển đi.
- Tìm kiếm và lọc cư dân theo tên, số căn hộ.

## 3. Apartment Management
- Thêm mới căn hộ:
  - Số căn hộ
  - Diện tích
  - Loại căn hộ
  - Trạng thái (đang ở/trống)
- Cập nhật, xóa thông tin căn hộ.
- Danh sách tất cả các căn hộ, có thể lọc theo trạng thái.

## 4. Fee Management (Thu phí)
- Quản lý các loại phí:
  - Phí dịch vụ
  - Phí gửi xe
  - Phí bảo trì
- Thêm hóa đơn thu phí cho từng căn hộ theo tháng.
- Ghi nhận thanh toán: ngày thu, hình thức thanh toán.
- Theo dõi công nợ và nhắc nhở cư dân chưa đóng phí.

## 5. Notification Management
- Gửi thông báo đến cư dân:
  - Thông báo phí
  - Thông báo bảo trì, sự kiện
  - Thông báo khẩn cấp
- Lưu lịch sử thông báo.

## 6. Report Management
- Xuất báo cáo:
  - Báo cáo danh sách cư dân.
  - Báo cáo công nợ theo tháng.
  - Báo cáo thu phí tổng hợp.

## 7. System Security
- Hỗ trợ đăng nhập bảo mật.
- Phân quyền truy cập theo vai trò.
- Ghi log các hoạt động quản trị.

## 8. Database Management
- Kết nối cơ sở dữ liệu MySQL.
- Backup định kỳ dữ liệu.
- Khôi phục dữ liệu khi cần thiết.

....