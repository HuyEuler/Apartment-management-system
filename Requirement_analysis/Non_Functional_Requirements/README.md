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
- **Cụ thể**:
    - **Thời gian phản hồi**: Các thao tác như tra cứu thông tin hộ gia đình, kiểm tra các khoản phí, thống kê số liệu cần có thời gian phản hồi dưới 3 giây.
    - **Khả năng xử lý đồng thời**: Phần mềm cần hỗ trợ ít nhất 10 người dùng đồng thời mà không giảm hiệu suất, đặc biệt là vào các đợt thu phí lớn.

---

### **Security requirements (Yêu cầu về bảo mật)**  
- **Mô tả**: Phần mềm cần bảo vệ thông tin nhạy cảm của cư dân và các khoản thu phí khỏi các truy cập trái phép.
- **Cụ thể**:
    - **Xác thực người dùng**: Sử dụng hàm băm an toàn như SHA để lưu trữ thông tin đăng nhập của người dùng. Duy trì phiên hoạt động của người dùng thông qua cookie với các trường bảo mật như http-only, same-site=strict,... Đối với các thao tác có tương tác với dữ liệu như POST, PUT, PATCH, DELETE cần sử dụng các biện pháp bảo vệ như CSRF.
    - **Mã hóa dữ liệu**: Sử dụng HTTPS để mã hóa dữ liệu trước khi truyền trên kết nối TCP.
    - **Phân quyền**: sử dụng Role Based Access Control để phân quyền người dùng.

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
    - **Mở rộng dữ liệu**: Phần mềm cần có khả năng lưu trữ và quản lý thông tin cho hàng nghìn hộ gia đình và các khoản thu phí một cách hiệu quả.
    - **Thêm tính năng**: Cần có khả năng thêm các tính năng mới trong tương lai, ví dụ như quản lý các khoản phí gửi xe hay các khoản phí từ các dịch vụ khác.

---

### **Maintainability requirements (Yêu cầu về khả năng duy trì)**  
- **Mô tả**: Phần mềm cần được thiết kế sao cho dễ bảo trì và cập nhật khi cần thiết.
- **Cụ thể**:
    - **Bảo trì và nâng cấp**: Cần có cơ chế để cập nhật và nâng cấp phần mềm mà không làm gián đoạn dịch vụ.
    - **Xử lý lỗi và sửa lỗi**: Cần có cơ chế phát hiện và khắc phục lỗi nhanh chóng, giúp phần mềm luôn hoạt động ổn định.
