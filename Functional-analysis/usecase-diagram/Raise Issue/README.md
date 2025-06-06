## 👀 Use case chi tiết:

Dưới đây là một use case điển hình liên quan đến **Báo cáo vấn đề**:

**- Tên Use Case:** Xử lý báo cáo vấn đề từ khách hàng

**- Ngữ cảnh:** Khách hàng gửi báo cáo vấn đề cần được xác minh và giải quyết.

**- Sự kiện kích hoạt:** Khách hàng gửi báo cáo vấn đề thông qua hệ thống.

**- Mô tả:**
Khi khách hàng gửi báo cáo, họ sẽ chọn loại vấn đề, cung cấp thông tin và có thể đăng kèm chứng cứ (nếu cần). Manager nhận và xem xét vấn đề, xác thực thông tin, và quyết định xử lý trực tiếp hoặc chuyển tiếp cho nhà cung cấp dịch vụ. Sau khi xử lý xong, kết quả sẽ được thông báo đến khách hàng (có thể liên hệ trực tiếp nếu cần).

**- Tác nhân:**

* Khách hàng
* Manager
* Nhà cung cấp dịch vụ (Service Provider)

**- Use case liên hệ:**

* Chọn loại vấn đề
* Cung cấp thông tin
* Đăng chứng cứ
* Xem thông tin vấn đề
* Chuyển tiếp yêu cầu
* Thông báo kết quả

**- Bên liên quan:**

* Khách hàng: Người báo cáo vấn đề.
* Bộ phận quản lý (Manager): Xác minh và xử lý báo cáo.
* Nhà cung cấp dịch vụ (Service Provider): Tiếp nhận và xử lý vấn đề (nếu được chuyển tiếp).

**- Tiền điều kiện:**

* Khách hàng phải có tài khoản hợp lệ trong hệ thống.
* Thông tin loại vấn đề cần được cấu hình rõ ràng (bao gồm các vấn đề yêu cầu chứng cứ).

**- Hậu điều kiện:**

* Vấn đề được xử lý và cập nhật trạng thái (hoàn tất hoặc từ chối).
* Khách hàng nhận được thông báo kết quả.
* Nếu xử lý xong, vấn đề được lưu trữ vào lịch sử hệ thống.

**- Luồng sự kiện:**

| Actor                                              | System                                                    |
| -------------------------------------------------- | --------------------------------------------------------- |
| 1. Khách hàng chọn loại vấn đề.                    | 1.1 Hiển thị danh sách loại vấn đề.                       |
| 2. Khách hàng cung cấp thông tin vấn đề.           | 2.1 Ghi nhận thông tin chi tiết.                          |
| 3. Khách hàng đăng chứng cứ (nếu cần).             | 3.1 Cho phép tải lên chứng cứ (hình ảnh, tài liệu,...)    |
| 4. Hệ thống gửi yêu cầu đến Manager.               | 4.1 Thông báo cho Manager về vấn đề mới.                  |
| 5. Manager xem xét thông tin vấn đề.               | 5.1 Hiển thị thông tin chi tiết của vấn đề.               |
| 6. Manager xác thực thông tin.                     | 6.1 Xác nhận thông tin có hợp lệ hay không.               |
| 7. Manager quyết định chuyển tiếp hoặc xử lý.      | 7.1 Nếu cần, chuyển tiếp vấn đề cho nhà cung cấp dịch vụ. |
| 8. Nhà cung cấp dịch vụ nhận vấn đề từ Manager.    | 8.1 Hiển thị chi tiết vấn đề cần xử lý.                   |
| 9. Nhà cung cấp dịch vụ xử lý và cập nhật kết quả. | 9.1 Ghi nhận kết quả xử lý.                               |
| 10. Manager nhận kết quả từ nhà cung cấp.          | 10.1 Tổng hợp và chuẩn bị thông báo kết quả.              |
| 11. Manager thông báo kết quả cho khách hàng.      | 11.1 Gửi thông báo hoặc liên hệ trực tiếp nếu cần.        |

**- Điều kiện ngoại lệ:**

* Nếu khách hàng không đăng nhập hoặc không hợp lệ → Từ chối tiếp nhận yêu cầu.
* Nếu loại vấn đề không yêu cầu chứng cứ mà khách hàng không cung cấp → Vẫn tiếp nhận yêu cầu.
* Nếu Manager không thể xử lý → Bắt buộc chuyển tiếp cho nhà cung cấp dịch vụ.
* Nếu kết quả cần giải thích rõ ràng hoặc phức tạp → Có thể liên hệ trực tiếp khách hàng.

---

