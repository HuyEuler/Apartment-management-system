# Non-functional requirements (FURPS)

### **Usability requirements (Yêu cầu về tính dễ sử dụng)**

- **Mô tả**: Giao diện phần mềm dễ sử dụng và thân thiện với người dùng Ban quản trị, đặc biệt là với các nhân viên không có nhiều kinh nghiệm về công nghệ.
- **Cụ thể**:
  - **Giao diện người dùng**: Các tính năng như quản lý thông tin phí, quản lý hộ gia đình, nhân khẩu bố trí ở vị trí thanh Menu cho dễ dàng tìm kiếm và sử dụng
  - **Tính năng tìm kiếm và tra cứu**: Phần mềm cung cấp khả năng tìm kiếm nhanh chóng và chính xác các khoản phí, thông tin hộ gia đình, hoặc các khoản đóng góp đồng thời cung cấp tính năng lọc theo một số tiêu chí cho dễ dàng tổng kết
  - **Đào tạo và hướng dẫn sử dụng**: Cung cấp hướng dẫn chi tiết và trợ giúp trực tuyến trong phần mềm để nhân viên Ban quản trị có thể tự học cách sử dụng bằng cách hiển thị hướng dẫn đối với người dùng lần đầu truy cập

---

### **Reliability requirements (Yêu cầu về độ tin cậy)**

- **Mô tả**: Phần mềm cần đảm bảo hoạt động ổn định, không bị gián đoạn khi xử lý các khoản thu và thông tin liên quan.
- **Cụ thể**:
  - **Tần suất sự cố**: Phần mềm đảm bảo tần suất xảy ra lỗi thấp, đặc biệt là ở các chức năng quan trọng như thu phí.
  - **Khả năng khôi phục và lưu trữ**: Phần mềm có khả năng lưu lại các sự cố, các phiên bản trước khi lỗi xảy ra để đảm bảo cho việc khôi phục nhanh chóng và an toàn.

---

### **Performance requirements (Yêu cầu về hiệu suất)**

- **Mô tả**: Phần mềm cần đáp ứng yêu cầu về tốc độ xử lý và thời gian phản hồi của các chức năng cơ bản.
- **Cụ thể**: - Đối với màn hình input: tối đa 30 trường dữ liệu, không tính toán dữ liệu phức tạp, không tương tác với hệ thống ngoài, có thể lưu trữ dữ liệu trực tiếp ngay xuống DB, và không lưu trữ các tệp nội dung lớn như: hình ảnh, video, tệp tin quá 3MB. - Đối với màn hình output: dữ liệu được query trực tiếp từ DB, hạn chế những query phức tạp, những query từ hệ thống ngoài.
  Hiển thị tối đa 50 dòng dữ liệu, mỗi dòng tối đa 10 cột, và mỗi dữ liệu có độ dài nhỏ hơn 100 ký tự. - Điều kiện tải bình thường: 30 CCU (concurrent user – người dùng đồng thời) khi không dùng cân bằng tải. - Điều kiện server tối thiểu: Intel Core i5, 4GB RAM, 500GB hard disk.

---

### **Security requirements (Yêu cầu về bảo mật)**

- **Mô tả**: Phần mềm cần bảo vệ thông tin nhạy cảm của cư dân và các khoản thu phí khỏi các truy cập trái phép.
- **Cụ thể**:
  - Password của người dùng phải được hash bằng MD5.
  - Hệ thống sẽ deactivate 30 phút nếu người dùng nhập password sai 5 lần liên tiếp.
  - Tất cả những data “nhạy cảm” của người dùng như: password, SĐT, CMND, email phải được mã hóa bằng 1024bit SSL.
  - Khi user quên mật khẩu, link tạo mật khẩu mới phải được gửi về duy nhất địa chỉ email đăng ký đầu tiên.
  - Hoặc khi user thực hiện thanh toán online, hệ thống không được phép lưu trữ thông tin thẻ credit/ debit của user.

---

### **Technical requirements (Yêu cầu về kỹ thuật)**

- **Mô tả**: Phần mềm phải hoạt động tốt trên các nền tảng khác nhau và dễ dàng tích hợp với các hệ thống bên ngoài như các công ty cung cấp điện, nước.
- **Cụ thể**:
  - **Hệ điều hành và nền tảng**: Phần mềm cần chạy mượt mà trên các hệ điều hành phổ biến như Windows, MacOS, hoặc trên các thiết bị di động.
  - **Tính khả dụng và bảo mật của hệ thống**: Hệ thống cần có khả năng sao lưu và khôi phục trong trường hợp gặp sự cố, và đảm bảo an toàn cho dữ liệu khi truyền tải qua mạng.
  - **Khả năng tích hợp với các hệ thống bên ngoài**: Phần mềm phải có khả năng tích hợp với các hệ thống thanh toán, công ty cung cấp dịch vụ như điện, nước, internet để tự động cập nhật thông tin chi tiết và thu phí.

---

### **Scalability requirements (Yêu cầu về khả năng mở rộng)**

- **Mô tả**: Phần mềm cần có khả năng mở rộng khi số lượng cư dân tăng lên hoặc khi có thêm các khoản thu phí mới.
- **Cụ thể**:
  - Server có khả năng upgrade cấu hình.
  - Có khả năng tách DB trên một server riêng và backend trên một server riêng.
  - Có khả năng áp dụng load balancer chạy bằng HA Proxy.
  - Có khả năng chia nhỏ DB master thành các DB con và đồng bộ ngược trở lại.

---

### **Maintainability requirements (Yêu cầu về khả năng duy trì)**

- **Mô tả**: Phần mềm cần được thiết kế sao cho dễ bảo trì và cập nhật khi cần thiết.
- **Cụ thể**:
  - Với mỗi lần nâng cấp hệ thống định kỳ hàng quý sẽ không kéo dài quá 30 phút.
  - Toàn bộ code Javascript và .NET phải được viết theo coding convention.
  - Document và code phải được review nội bộ qua 2 cấp.
