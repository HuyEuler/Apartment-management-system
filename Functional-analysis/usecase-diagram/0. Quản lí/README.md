## 👀 Use case chi tiết:

Dưới đây là một use case điển hình liên quan đến **Customer quản lý tài khoản**:

**- Tên Use Case:** Quản lý tài khoản cư dân

**- Ngữ cảnh:** Cư dân thực hiện quản lý thông tin tài khoản cá nhân và thay đổi trạng thái cư trú nếu cần.

**- Sự kiện kích hoạt:** Cư dân truy cập hệ thống và thao tác quản lý tài khoản.

**- Mô tả:**
Khi cư dân muốn quản lý tài khoản, họ có thể xem thông tin, cập nhật thông tin hoặc thay đổi trạng thái cư trú. Nếu yêu cầu thay đổi trạng thái cư trú, cư dân cần cung cấp minh chứng. Quản lý sẽ nhận, kiểm tra, xác thực thông tin và quyết định duyệt hoặc chuyển tiếp yêu cầu cho nhà cung cấp dịch vụ nếu cần. Sau đó, thông tin cư trú sẽ được cập nhật.

**- Tác nhân:**

* Cư dân (Customer)
* Ban quản lý (Manager)

**- Use case liên hệ:**

* Xem thông tin tài khoản
* Cập nhật thông tin tài khoản
* Thay đổi trạng thái cư trú
* Xem đơn yêu cầu
* Xác thực thông tin
* Cập nhật trạng thái cư trú

**- Bên liên quan:**

* Cư dân: Người yêu cầu thay đổi thông tin.
* Ban quản lý: Xem xét, xác thực và cập nhật thông tin cư trú.
* Nhà cung cấp dịch vụ: Tham gia xử lý nếu cần thiết.

**- Tiền điều kiện:**

* Cư dân phải đăng nhập hệ thống.
* Thông tin tài khoản đã có sẵn trong hệ thống.

**- Hậu điều kiện:**

* Thông tin tài khoản được cập nhật.
* Trạng thái cư trú của cư dân được thay đổi (nếu được duyệt).
* Cư dân nhận thông báo kết quả.

**- Luồng sự kiện:**

| Actor                                                                                                                                                  | System                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------- |
| 1. Cư dân mở chức năng quản lý tài khoản.                                                                                                              | 1.1 Hiển thị thông tin tài khoản.                   |
| 2. Cư dân xem thông tin tài khoản.                                                                                                                     | 2.1 Cung cấp thông tin tài khoản chi tiết.          |
| 3. Cư dân cập nhật thông tin tài khoản (nếu có).                                                                                                       | 3.1 Ghi nhận thông tin cập nhật.                    |
| 4. Cư dân yêu cầu thay đổi trạng thái cư trú.                                                                                                          | 4.1 Ghi nhận yêu cầu thay đổi trạng thái cư trú.    |
| 5. Cư dân tải lên minh chứng.                                                                                                                          | 4.2 Cho phép tải lên minh chứng.                    |
| 6. Hệ thống gửi yêu cầu đến Manager.                                                                                                                   | 4.3 Thông báo cho Manager về yêu cầu mới.           |
| 7. Manager xem thông tin đơn thay đổi trạng thái cư trú.                                                                                               | 7.1 Hiển thị chi tiết đơn yêu cầu.                  |
| 8. Manager xác thực thông tin cư dân và minh chứng.                                                                                                    | 8.1 Kiểm tra và xác nhận tính hợp lệ của thông tin. |
| 9. Manager quyết định xử lý hoặc chuyển tiếp. <br>- Nếu tự xử lý, chuyển sang bước 10. <br>- Nếu không tự xử lý, chuyển tiếp cho nhà cung cấp dịch vụ. |                                                     |
| 10. Manager cập nhật trạng thái cư trú.                                                                                                                | 10.1 Cập nhật thông tin trạng thái cư trú.          |
| 11. Hệ thống thông báo kết quả cho cư dân.                                                                                                             | 11.1 Gửi thông báo hoặc liên hệ trực tiếp nếu cần.  |

**- Điều kiện ngoại lệ:**

* Nếu cư dân không đăng nhập hoặc không hợp lệ → Từ chối thực hiện.
* Nếu minh chứng không hợp lệ hoặc thiếu → Từ chối hoặc yêu cầu bổ sung.
* Nếu Manager không thể xử lý → Bắt buộc chuyển tiếp cho nhà cung cấp dịch vụ.
* Nếu thông tin thay đổi cần làm rõ thêm → Có thể liên hệ trực tiếp cư dân.

