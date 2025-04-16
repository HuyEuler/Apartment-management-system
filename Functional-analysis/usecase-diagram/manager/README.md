## **Biểu đồ Use case:**
![alt text](Manager-UC.drawio.svg)

## ✅ **Bảng Use Case đầy đủ:**

| STT | Tên Use Case                    | Mô tả ngắn gọn                                                                                                  |
| --- | ------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| 1   | Đăng nhập hệ thống              | Đăng nhập vào hệ thống với tài khoản quản trị để thực hiện các chức năng quản lý.                               |
| 2   | Quản lý thông tin cư dân        | Thêm, sửa, xóa, cập nhật thông tin của cư dân trong chung cư.                                                   |
| 3   | Quản lý danh sách phòng         | Quản lý (thêm, sửa, xóa, cập nhật) thông tin, trạng thái các phòng trong chung cư.                              |
| 4   | Xem thông tin cư dân            | Xem và tìm kiếm danh sách cư dân đang cư trú tại chung cư.                                                      |
| 5   | Xem thông tin phòng             | Xem và tìm kiếm danh sách, trạng thái phòng hiện có trong chung cư.                                             |
| 6   | Duyệt yêu cầu của cư dân        | Phê duyệt hoặc từ chối các yêu cầu đặt phòng, đổi phòng, trả phòng do cư dân gửi.                               |
| 7   | Quản lý hợp đồng thuê phòng     | Tạo mới, cập nhật, gia hạn hoặc chấm dứt hợp đồng thuê phòng của cư dân.                                        |
| 8   | Tạo và quản lý khoản phí        | Tạo các khoản phí (phí điện, nước, vệ sinh, bảo trì, phí gửi xe…) theo định kỳ hoặc một lần.                    |
| 9   | Quản lý thanh toán              | Tra cứu lịch sử thanh toán của cư dân theo phòng, khoản phí và thời gian cụ thể, cập nhật trạng thái thanh toán.|
| 10  | Thông báo cho cư dân            | Gửi các thông báo, thông tin cần thiết đến cư dân qua hệ thống, email hoặc ứng dụng.                            |
| 11  | Xuất báo cáo thống kê           | Xuất báo cáo tổng hợp về cư dân, tình trạng phòng, doanh thu và công nợ của chung cư.                           |

---

## 👀 Use case chi tiết:

Dưới đây là một use case chi tiết điển hình của actor **Ban quản lý chung cư**:

**- Tên Use Case:** Duyệt yêu cầu của cư dân

**- Ngữ cảnh:** Duyệt yêu cầu đặt, đổi hoặc trả phòng của cư dân

**- Sự kiện kích hoạt:** Cư dân gửi yêu cầu đặt phòng, đổi phòng hoặc trả phòng thông qua hệ thống.

**- Mô tả:** Khi cư dân gửi yêu cầu đặt mới, đổi hoặc trả phòng, ban quản lý sẽ nhận thông báo, kiểm tra thông tin yêu cầu, xác minh tình trạng phòng, xác nhận hoặc từ chối yêu cầu và thông báo lại cho cư dân.

**- Tác nhân:** Ban quản lý chung cư

**- Use case liên hệ:** Xem thông tin phòng, Thông báo cho cư dân

**- Bên liên quan:**

- Bộ phận quản lý cư dân: Kiểm tra và xử lý yêu cầu cư dân.
- Bộ phận quản lý phòng: Xác nhận trạng thái phòng có thể đáp ứng yêu cầu hay không.

**- Tiền điều kiện:**

- Cư dân phải tồn tại trong hệ thống.
- Các thông tin về phòng phải luôn được cập nhật đầy đủ, chính xác.

**- Hậu điều kiện:**

- Yêu cầu của cư dân được cập nhật trạng thái là đã duyệt hoặc từ chối.
- Thông tin phòng được cập nhật theo yêu cầu đã được duyệt (nếu có).
- Cư dân nhận được thông báo kết quả yêu cầu.

**- Luồng sự kiện:**

| Actor                                                                                                                         | System                                                          |
| ----------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| 1. Ban quản lý nhận được thông báo yêu cầu từ cư dân.                                                                         | 1.1 Hiển thị thông báo yêu cầu mới từ cư dân.                   |
| 2. Ban quản lý xem thông tin chi tiết của yêu cầu.                                                                            | 2.1 Hiển thị chi tiết yêu cầu và thông tin cư dân liên quan.    |
| 3. Ban quản lý kiểm tra trạng thái phòng liên quan.                                                                           | 3.1 Hiển thị trạng thái phòng (đã đặt, trống, sẵn sàng,...).    |
| 4. Ban quản lý quyết định duyệt hoặc từ chối yêu cầu.<br>- Nếu duyệt, chuyển đến bước 5.<br>- Nếu từ chối, chuyển đến bước 7. |                                                                 |
| 5. Ban quản lý cập nhật thông tin phòng theo yêu cầu được duyệt.                                                              | 5.1 Cập nhật thông tin phòng theo yêu cầu.                      |
| 6. Ban quản lý xác nhận và cập nhật trạng thái của yêu cầu.                                                                   | 6.1 Cập nhật trạng thái của yêu cầu (đã duyệt hoặc đã từ chối). |
| 7. Ban quản lý gửi thông báo kết quả cho cư dân.                                                                              | 7.1 Tạo và gửi thông báo kết quả xử lý cho cư dân.              |

**- Điều kiện ngoại lệ:**

- Nếu cư dân không tồn tại trong hệ thống, ban quản lý dừng xử lý và yêu cầu cập nhật thông tin cư dân.
- Nếu phòng yêu cầu không hợp lệ hoặc không thể đáp ứng, ban quản lý sẽ từ chối yêu cầu và thông báo lý do từ chối cho cư dân.
