# Thiết kế cơ sở dữ liệu - Hệ thống quản lý chung cư

Sơ đồ thiết kế cơ sở dữ liệu 

![Sơ đồ thiết kế cơ sở dữ liệu ](./Apartment-management%20.png)

Dưới đây là phần giải thích chi tiết ý nghĩa các bảng trong hệ thống quản lý chung cư cùng với bảng mô tả các trường dữ liệu trong từng bảng.

---

## 1. Bảng `User` - Thông tin người dùng
Bảng lưu thông tin cư dân và ban quản lý chung cư.

| Trường | Kiểu dữ liệu | Ý nghĩa |
|--------|---------------|---------|
| userId | int (PK) | Mã định danh người dùng |
| role | nvarchar(50) | 2 role (`resident` : cư dân, `manager` : ban quản lý) |
| apartmentId | int | Mã căn hộ người dùng đang ở |
| name | nvarchar(50) | Họ tên người dùng |
| birthday | date | Ngày sinh |
| gender | bit | Giới tính (1: Nam, 0: Nữ) |
| phoneNumber | nvarchar(12) | Số điện thoại |
| nationality | nvarchar(50) | Quốc tịch |
| image | varbinary(MAX) | Ảnh đại diện |
| address | nvarchar(100) | Địa chỉ thường trú |
| isOwner | bit | Có phải chủ hộ hay không |
| relationshipWithOwner | nvarchar(50) | Quan hệ với chủ hộ (nếu không phải chủ hộ) |
| status | int | Trạng thái cư trú: -1 (chưa đặt phòng), 0 (đã rời), 1 (thường trú), 2 (tạm trú), 3 (tạm vắng) |

---

## 2. Bảng `Login` - Tài khoản đăng nhập
Lưu thông tin đăng nhập của người dùng.

| Trường | Kiểu dữ liệu | Ý nghĩa |
|--------|---------------|---------|
| userId | int (PK, unique) | Liên kết với bảng `User` |
| username | varchar(50) | Tên đăng nhập |
| password | varchar(50) | Mật khẩu |

---

## 3. Bảng `Apartment` - Quản lý căn hộ
Thông tin chi tiết các căn hộ trong chung cư.

| Trường | Kiểu dữ liệu | Ý nghĩa |
|--------|---------------|---------|
| apartmentId | int (PK) | Mã định danh căn hộ |
| ownerId | int | Mã chủ sở hữu căn hộ (userId) |
| area | float | Diện tích căn hộ (m²) |
| floor | int | Tầng |
| room | nvarchar(20) | Số phòng |

---

## 4. Bảng `Activity` - Lịch sử cư trú của cư dân
Theo dõi trạng thái và thời gian cư trú của cư dân.

| Trường | Kiểu dữ liệu | Ý nghĩa |
|--------|---------------|---------|
| activityId | int (PK) | Mã hoạt động |
| residentId | int | Mã cư dân |
| status | int | Trạng thái: -1 (chưa đặt phòng), 0 (đã rời), 1 (thường trú), 2 (tạm trú), 3 (tạm vắng) |
| dateOfEvent | date | Ngày diễn ra sự kiện |
| note | nvarchar(500) | Ghi chú |

---

## 5. Bảng `Fee` - Các loại phí
Định nghĩa các loại phí áp dụng trong chung cư.

| Trường | Kiểu dữ liệu | Ý nghĩa |
|--------|---------------|---------|
| feeId | int (PK) | Mã phí |
| name | varchar(255) | Tên phí |
| createTime | date | Ngày tạo phí |
| ratePerSquareMeter | double | Mức phí tính trên m² |
| isMandatory | boolean | Có bắt buộc hay không |
| feeType | varchar(50) | Loại phí (`service fee`, `contribution fee`) |
| payForMonthCycle | int | Chu kỳ đóng phí hàng tháng (= 0 nếu không áp dụng) |
| payForYearCycle | int | Chu kỳ đóng phí hàng năm (= 0 nếu không áp dụng) |
| providerName | nvarchar(100) | Tên đơn vị cung cấp dịch vụ (nếu có) |

---

## 6. Bảng `Payment` - Giao dịch thanh toán
Ghi nhận các khoản thanh toán phí.

| Trường | Kiểu dữ liệu | Ý nghĩa |
|--------|---------------|---------|
| paymentId | int (PK) | Mã giao dịch |
| feeId | int | Mã phí liên quan |
| apartmentId | int | Mã căn hộ đóng phí |
| amountDue | double | Số tiền phải trả |
| amountPaid | double | Số tiền đã trả |
| paymentDate | date | Ngày thanh toán |

---

## 7. Bảng `Vehicle` - Quản lý phương tiện
Thông tin phương tiện của cư dân trong chung cư.

| Trường | Kiểu dữ liệu | Ý nghĩa |
|--------|---------------|---------|
| vehicleId | int (PK) | Mã phương tiện |
| residentId | int | Mã cư dân sở hữu phương tiện |
| type | nvarchar(30) | Loại phương tiện (ô tô, xe máy, v.v.) |
| licensePlate | varchar(30) | Biển số xe |

---

Nếu bạn cần thêm biểu đồ ERD hoặc file xuất sang PDF, mình có thể hỗ trợ ngay!

## 8. Bảng `Report` - Báo cáo sự cố, phản hồi 
Thông tin báo cáo về sự cố, hoặc phản hồi từ người dùng 

| Trường         | Kiểu dữ liệu     | Ý nghĩa                                                                 |
|----------------|------------------|-------------------------------------------------------------------------|
| reportId       | int              | Mã định danh duy nhất cho mỗi báo cáo (khóa chính, duy nhất).          |
| userId         | int              | ID người dùng gửi báo cáo (có thể liên kết với bảng `User`).            |
| problemTitle   | nvarchar(50)     | Tiêu đề ngắn mô tả vấn đề được báo cáo (bắt buộc nhập).                |
| description    | nvarchar(200)    | Mô tả chi tiết hơn về sự cố hoặc tình huống cần phản ánh.              |
| timeOfEvent    | time             | Thời điểm gửi báo cáo / phản hồi                                       | 
| type           | int              | `type = 0` : Gặp sự cố về dịch vụ.   `type = 1` : Vấn đề khác.        |
| attachment     | varbinary(max)   | File đính kèm (ảnh, tài liệu...), có thể để trống nếu không có file.   |


