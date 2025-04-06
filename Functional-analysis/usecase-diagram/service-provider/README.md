### ✅ **Bảng Use Case đầy đủ:**

| STT | Tên Use Case                | Mô tả ngắn gọn                                                                                                         |
| --- | --------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| 1   | Cung cấp dữ liệu thanh toán | Cung cấp dữ liệu sử dụng dịch vụ (điện, nước, internet, gửi xe,…) theo từng cư dân hoặc từng phòng để phục vụ thu phí. |

## 👀 Use case chi tiết:
Dưới đây là một use case chi tiết điển hình của actor **Nhà cung cấp dịch vụ**:

**Use Case Name:** Cung cấp dữ liệu thanh toán

**Scenario:** Cung cấp dữ liệu sử dụng dịch vụ phục vụ cho việc thu phí của chung cư

**Triggering Event:** Chung cư yêu cầu cung cấp dữ liệu sử dụng dịch vụ (điện, nước, internet, gửi xe, …) để phục vụ lập hóa đơn thu phí cư dân.

**Brief Description:** Khi đến kỳ thu phí, chung cư yêu cầu nhà cung cấp dịch vụ cung cấp dữ liệu chi tiết về lượng sử dụng dịch vụ của từng cư dân hoặc từng phòng. Nhà cung cấp dịch vụ tổng hợp, xác nhận và gửi dữ liệu đến ban quản lý chung cư.

**Actors:** Nhà cung cấp dịch vụ

**Related Use Cases:** Tạo và quản lý khoản phí, Theo dõi và cập nhật thanh toán

**Stakeholders:**

- Nhà cung cấp dịch vụ: Cung cấp dữ liệu chính xác và kịp thời.
- Ban quản lý chung cư: Nhận dữ liệu để tính toán, thu phí cư dân.

**Preconditions:**

- Nhà cung cấp dịch vụ phải có hệ thống theo dõi và ghi nhận đầy đủ dữ liệu sử dụng dịch vụ.
- Có thỏa thuận hợp tác, trao đổi dữ liệu giữa chung cư và nhà cung cấp dịch vụ.

**Postconditions:**

- Chung cư nhận được dữ liệu đầy đủ, chính xác về việc sử dụng dịch vụ của từng cư dân hoặc từng phòng.
- Chung cư sử dụng dữ liệu này để tạo hóa đơn và thu phí.

**Flow of Activities:**

| Actor                                                                                     | System                                                                          |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| 1. Nhà cung cấp dịch vụ nhận yêu cầu cung cấp dữ liệu thanh toán từ chung cư.             | 1.1 Gửi yêu cầu cung cấp dữ liệu đến hệ thống của nhà cung cấp dịch vụ.         |
| 2. Nhà cung cấp dịch vụ tổng hợp dữ liệu sử dụng dịch vụ theo cư dân hoặc phòng.          | 2.1 Hệ thống tổng hợp và phân loại dữ liệu sử dụng dịch vụ.                     |
| 3. Nhà cung cấp dịch vụ kiểm tra và xác thực dữ liệu đảm bảo tính chính xác.              | 3.1 Hệ thống kiểm tra tính hợp lệ và chính xác của dữ liệu.                     |
| 4. Nhà cung cấp dịch vụ gửi dữ liệu thanh toán đến chung cư theo định dạng đã thỏa thuận. | 4.1 Gửi dữ liệu đến hệ thống quản lý của chung cư theo định dạng đã thống nhất. |

**Exception Conditions:**

- Nếu dữ liệu không đầy đủ hoặc có sai sót, nhà cung cấp dịch vụ phải kiểm tra, điều chỉnh và gửi lại dữ liệu chính xác cho chung cư.
- Nếu hệ thống gặp sự cố hoặc chậm trễ, nhà cung cấp dịch vụ cần thông báo kịp thời với ban quản lý chung cư để có biện pháp xử lý phù hợp.
