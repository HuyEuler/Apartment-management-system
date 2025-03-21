# TÀI LIỆU THIẾT KẾ HỆ THỐNG PHẦN MỀM QUẢN LÝ CHUNG CƯ 

## 1. GIỚI THIỆU CHUNG

### 1.1. Mục đích tài liệu

Tài liệu này mô tả mục tiêu và phạm vi của hệ thống phần mềm quản lý chung cư, nhằm hỗ trợ Ban Quản Trị trong việc quản lý thu phí, thông tin cư dân và phương tiện một cách hiệu quả. Tài liệu cung cấp chi tiết về các chức năng, kiến trúc và các thành phần chính của hệ thống.

**Mục tiêu:**

- Tự động hóa việc thu phí và quản lý cư dân.
- Nâng cao hiệu quả vận hành của Ban Quản Trị.
- Cung cấp thông tin minh bạch về tình trạng cư trú và thanh toán.

**Đối tượng sử dụng tài liệu:**

- Nhóm phát triển phần mềm.
- Ban Quản Trị chung cư.
- Các bên liên quan trong quá trình xây dựng và triển khai hệ thống.

### 1.2. Phạm vi hệ thống

Hệ thống phần mềm quản lý chung cư được xây dựng nhằm hỗ trợ Ban Quản Trị thực hiện các công việc quản lý thu phí, cư dân và phương tiện. Phần mềm này sẽ thay thế phương pháp thủ công bằng một nền tảng số hóa hiện đại, giúp tối ưu hóa quy trình làm việc.

**Mục tiêu kinh doanh và lợi ích:**

- Giảm thời gian xử lý thu phí và quản lý dữ liệu cư dân.
- Cung cấp hệ thống báo cáo và thống kê chi tiết.
- Hỗ trợ cư dân tra cứu thông tin nhanh chóng.
- Tăng tính minh bạch và hiệu suất quản lý tài chính.

**Các bên liên quan:**

- Ban Quản Trị chung cư: Quản lý toàn bộ hệ thống.
- Cư dân chung cư: Người đóng các khoản phí và sử dụng dịch vụ.
- Nhà cung cấp dịch vụ (điện, nước, internet)\*\*: Cung cấp thông tin hóa đơn cho Ban Quản Trị để thu hộ.

### 1.3. Tài liệu tham khảo

- Tài liệu yêu cầu hệ thống.
- Các tài liệu hướng dẫn kỹ thuật liên quan đến công nghệ sử dụng (React, Node.js, v.v.).
- Tiêu chuẩn bảo mật dữ liệu.

### 1.4. Định nghĩa và từ viết tắt

- UC: Use Case - Trường hợp sử dụng.
- Ban Quản Trị: Ban Quản Trị chung cư.
- Cư dân: Người sinh sống tại chung cư.
- Phí dịch vụ: Khoản phí bắt buộc hàng tháng dựa trên diện tích căn hộ.
- Phí quản lý: Chi phí vận hành chung cư, thu theo m2.
- Phí gửi xe: Phí đăng ký xe máy, ô tô hàng tháng.

---

## 2. TỔNG QUAN VỀ HỆ THỐNG

### 2.1. Kiến trúc tổng quan

Hệ thống sử dụng kiến trúc Client-Server, trong đó:

- Frontend: Ứng dụng web chạy trên trình duyệt, phát triển bằng React.js.
- Backend: API sử dụng Node.js để xử lý dữ liệu.
- Cơ sở dữ liệu: MySQL lưu trữ thông tin cư dân, căn hộ, phí thu.

**Sơ đồ kiến trúc hệ thống:**

```
[User] <--> [Frontend (React)] <--> [Backend (Node.js)] <--> [Database (MySQL)]
```

### 2.2. Chức năng chính

Hệ thống bao gồm các chức năng chính sau:

#### **Quản lý tài khoản**

- UC01: Đăng nhập
- UC02: Đăng xuất
- UC03: Sửa thông tin cá nhân
- UC04: Đổi mật khẩu

#### **Quản lý cư dân và căn hộ**

- UC05: Xem danh sách cư dân
- UC06: Thêm cư dân
- UC07: Xóa cư dân
- UC08: Sửa thông tin cư dân
- UC09: Tìm kiếm cư dân theo tên
- UC10: Xem danh sách căn hộ
- UC11: Thêm căn hộ
- UC12: Xóa căn hộ
- UC13: Sửa thông tin chủ căn hộ
- UC14: Tìm kiếm căn hộ theo số phòng

#### **Quản lý thu phí**

- UC15: Xem danh sách phí
- UC16: Thêm khoản phí thu
- UC17: Xóa khoản phí thu
- UC18: Sửa khoản phí thu
- UC19: Tìm kiếm khoản phí
- UC20: Thanh toán phí
- UC21: Tạo thanh toán hàng tháng
- UC22: Xem danh sách đã nộp phí
- UC23: Xem danh sách chưa nộp phí
- UC24: Xem danh sách quá hạn

#### **Quản lý phương tiện**

- UC25: Xem danh sách phương tiện
- UC26: Thêm phương tiện
- UC27: Xóa phương tiện
- UC28: Tìm kiếm phương tiện theo biển số

---

### 2.3. Các thành phần chính của hệ thống

Hệ thống bao gồm các module chính sau:

- Module Quản lý tài khoản: Xử lý xác thực người dùng, quản lý thông tin đăng nhập và quyền hạn truy cập.
- Module Quản lý cư dân: Quản lý thông tin nhân khẩu, hộ khẩu, lịch sử cư trú của cư dân.
- Module Quản lý căn hộ: Lưu trữ thông tin căn hộ, chủ sở hữu và trạng thái căn hộ.
- Module Quản lý thu phí: Ghi nhận, tính toán và theo dõi các khoản phí dịch vụ, phí gửi xe, chi phí điện nước.
- Module Quản lý phương tiện: Theo dõi phương tiện đăng ký của cư dân.
- Module Báo cáo và thống kê: Cung cấp báo cáo về tình trạng thanh toán, danh sách cư dân và phương tiện.
