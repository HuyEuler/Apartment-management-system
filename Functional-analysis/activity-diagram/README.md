# Thư mục Sơ đồ Hoạt động (Activity Diagram)

Thư mục này lưu trữ các sơ đồ hoạt động (Activity Diagram) mô tả các quy trình nghiệp vụ quan trọng của hệ thống quản lý căn hộ. Sơ đồ hoạt động là một công cụ trực quan giúp phân tích, thiết kế và truyền đạt các bước thực hiện của từng chức năng trong hệ thống, từ đó hỗ trợ phát triển phần mềm hiệu quả và nhất quán.

---

## 1. Giới thiệu về Sơ đồ Hoạt động

Sơ đồ hoạt động (Activity Diagram) là một loại sơ đồ UML dùng để mô tả luồng công việc hoặc các bước thực hiện của một quy trình nghiệp vụ. Trong dự án này, sơ đồ hoạt động giúp:
- Minh họa trực quan các bước xử lý của từng chức năng.
- Làm rõ vai trò của người dùng và hệ thống trong từng bước.
- Hỗ trợ trao đổi giữa các thành viên phát triển, kiểm thử và khách hàng.
- Là tài liệu tham khảo khi bảo trì, mở rộng hệ thống.
- Giảm thiểu hiểu nhầm trong quá trình phát triển phần mềm.

### 1.1. Vai trò trong phát triển phần mềm
- Giúp xác định rõ các trường hợp ngoại lệ, điều kiện rẽ nhánh.
- Hỗ trợ kiểm thử viên xây dựng kịch bản kiểm thử.
- Làm tài liệu đào tạo cho thành viên mới.
- Tăng tính minh bạch và khả năng truy vết quy trình nghiệp vụ.

---

## 2. Nội dung thư mục

### 2.1. Các file sơ đồ hoạt động

- **File hình ảnh (.png, .drawio.png):**
  - `registerandlogin.drawio.png`: Sơ đồ đăng ký và đăng nhập tài khoản.
  - `bookroom.drawio.png`: Sơ đồ đặt phòng.
  - `paymetn.drawio.png`: Sơ đồ thanh toán.
  - `image.png`, `image-1.png`, `image-2.png`: Các hình minh họa quy trình nghiệp vụ khác.

> **Lưu ý:** Các file có đuôi `.drawio.png` có thể mở và chỉnh sửa bằng phần mềm [draw.io](https://app.diagrams.net/) hoặc các công cụ hỗ trợ định dạng này.

### 2.2. Thư mục con

- **activity_description/**: Dự kiến dùng để lưu các mô tả chi tiết, giải thích từng bước trong các sơ đồ hoạt động. Hiện tại chưa có nội dung, sẽ được bổ sung trong các bản cập nhật tiếp theo.

---

## 3. Mô tả chi tiết các sơ đồ hoạt động

### 3.1. Sơ đồ Đăng ký & Đăng nhập
- **Đăng ký:**
  1. Nhập tên người dùng, kiểm tra hợp lệ.
  2. Nhập mật khẩu, kiểm tra độ mạnh.
  3. Xác nhận lại mật khẩu.
  4. Nhập thông tin bổ sung (họ tên, email, SĐT).
  5. Lưu vào cơ sở dữ liệu.
  6. Khởi tạo tài khoản mới.
- **Đăng nhập:**
  1. Nhập tên đăng nhập.
  2. Nhập mật khẩu.
  3. Hệ thống xác thực thông tin.
  4. Đăng nhập thành công/thất bại.

### 3.2. Sơ đồ Đặt phòng
- Người dùng chọn phòng → kiểm tra trạng thái phòng → xác nhận đặt phòng → lưu thông tin đặt phòng.
- Hệ thống đảm bảo không có trùng lặp, phòng đã được đặt sẽ không hiển thị cho người dùng khác.

### 3.3. Sơ đồ Thanh toán
- Người dùng chọn phương thức thanh toán → nhập thông tin thanh toán → xác nhận giao dịch → hệ thống cập nhật trạng thái thanh toán.
- Hỗ trợ nhiều phương thức: chuyển khoản, tiền mặt, ví điện tử...

---

## 4. Ví dụ minh họa cách đọc sơ đồ hoạt động

Ví dụ: Sơ đồ đăng ký tài khoản
- Bắt đầu (Start)
- Nhập thông tin → Kiểm tra hợp lệ → Nếu hợp lệ: tiếp tục, nếu không: quay lại nhập lại
- Xác nhận mật khẩu → Nếu trùng khớp: tiếp tục, nếu không: nhập lại
- Nhập thông tin bổ sung → Lưu vào CSDL → Kết thúc (End)

Các ký hiệu thường gặp:
- Hình tròn đen: điểm bắt đầu
- Hình tròn viền đen: điểm kết thúc
- Hình chữ nhật bo góc: hành động
- Mũi tên: luồng chuyển tiếp
- Hình thoi: điều kiện rẽ nhánh

---

## 5. Hướng dẫn sử dụng sơ đồ và phần mềm draw.io

- Để xem sơ đồ: Mở file `.png` bằng bất kỳ phần mềm xem ảnh nào.
- Để chỉnh sửa sơ đồ: Truy cập [draw.io](https://app.diagrams.net/), chọn "File" > "Import From" > "Device" để mở file `.drawio.png`.
- Sau khi chỉnh sửa, có thể xuất lại thành `.png` hoặc lưu dưới dạng `.drawio.png` để tiếp tục chỉnh sửa lần sau.
- Nên lưu ý đặt tên file rõ ràng, có thể thêm ngày tháng hoặc phiên bản để dễ quản lý.

### 5.1. Quy tắc đặt tên file sơ đồ
- Tên file nên thể hiện rõ chức năng, ví dụ: `registerandlogin_v1.drawio.png`
- Nếu có nhiều phiên bản, thêm số phiên bản hoặc ngày cập nhật: `bookroom_v2_20240601.drawio.png`
- Tránh đặt tên chung chung như `diagram1.png`

### 5.2. Quản lý phiên bản sơ đồ
- Khi cập nhật sơ đồ, nên lưu lại bản cũ để đối chiếu khi cần thiết.
- Có thể tạo thư mục `archive/` để lưu các phiên bản cũ.

---

## 6. Định hướng phát triển tài liệu

- Bổ sung mô tả chi tiết cho từng sơ đồ trong thư mục `activity_description/`.
- Thêm các sơ đồ cho các quy trình mới khi hệ thống mở rộng.
- Định kỳ rà soát, cập nhật sơ đồ khi có thay đổi về nghiệp vụ.
- Khuyến khích các thành viên đóng góp, phản hồi để tài liệu ngày càng hoàn thiện.

---

## 7. Câu hỏi thường gặp (FAQ)

**Q1: Tôi không mở được file .drawio.png, phải làm sao?**
A1: Hãy truy cập https://app.diagrams.net/ và sử dụng chức năng "Import From Device" để mở file.

**Q2: Tôi muốn bổ sung mô tả cho một sơ đồ, làm thế nào?**
A2: Tạo file markdown mới trong thư mục `activity_description/` với tên tương ứng, ví dụ: `registerandlogin.md`.

**Q3: Có thể xuất sơ đồ sang PDF không?**
A3: Có, draw.io hỗ trợ xuất sơ đồ sang nhiều định dạng như PNG, JPEG, PDF...

**Q4: Nếu tôi phát hiện sơ đồ có lỗi thì làm gì?**
A4: Vui lòng liên hệ nhóm phát triển hoặc tạo issue trên hệ thống quản lý dự án để được hỗ trợ chỉnh sửa.

---

## 8. Liên hệ & Đóng góp ý kiến

- Nếu bạn có ý kiến đóng góp, phát hiện lỗi hoặc muốn bổ sung tài liệu, vui lòng liên hệ nhóm phát triển qua email hoặc kênh trao đổi nội bộ của dự án.
- Mọi đóng góp đều được ghi nhận và giúp tài liệu ngày càng hoàn thiện hơn.

---

## 9. Lời kết

Sơ đồ hoạt động là một phần không thể thiếu trong quá trình phân tích và phát triển hệ thống. Việc duy trì tài liệu này đầy đủ, cập nhật sẽ giúp dự án vận hành hiệu quả, giảm thiểu rủi ro và nâng cao chất lượng sản phẩm.

Nếu bạn cần bổ sung hoặc cập nhật chi tiết cho từng quy trình, vui lòng chỉnh sửa hoặc thêm vào thư mục `activity_description/`. Đừng ngần ngại liên hệ nhóm phát triển nếu cần hỗ trợ về sơ đồ hoặc tài liệu này.
