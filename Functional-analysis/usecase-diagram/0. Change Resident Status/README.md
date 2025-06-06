## ✅ **Use Case: Thay đổi trạng thái cư trú**

---

### **1. Tên Use Case:**  
**Thay đổi trạng thái cư trú của cư dân**

---

### **2. Ngữ cảnh:**  
Cư dân muốn cập nhật trạng thái cư trú (ví dụ: đang ở, tạm vắng, chuyển đi, chuyển căn) thông qua hệ thống. Quản lý sẽ xem xét và phê duyệt (hoặc từ chối) yêu cầu dựa trên minh chứng và thông tin bổ sung được cung cấp.

---

### **3. Tác nhân chính:**  
- **Cư dân (Customer)**
- **Ban quản lý (Manager)**

---

### **4. Các use case liên quan:**
- **Include:**  
  - Cung cấp thông tin  
  - Cung cấp minh chứng  
  - Xác thực thông tin  
  - Cập nhật trạng thái cư dân  
  - Cập nhật trạng thái phòng  
  - Thông báo cho cư dân  

- **Extend:**  
  - Cung cấp thông tin bổ sung (tùy trường hợp)  
  - Đồng ý (Manager chọn duyệt)  
  - Từ chối (Manager chọn từ chối)

---

### **5. Tiền điều kiện:**  
- Cư dân đã đăng nhập vào hệ thống.  
- Tài khoản và thông tin thuê phòng của cư dân đã tồn tại trong hệ thống.

---

### **6. Hậu điều kiện:**  
- Trạng thái cư trú được cập nhật (nếu yêu cầu được duyệt).  
- Cư dân được thông báo về kết quả.  
- Trạng thái phòng được cập nhật nếu liên quan.

---

### **7. Luồng sự kiện chính (Main Flow)**

| **Actor**                   | **System**                                                                 |
|----------------------------|----------------------------------------------------------------------------|
| 1. Cư dân yêu cầu thay đổi trạng thái cư trú. | 1.1 Khởi tạo yêu cầu mới.                                              |
| 2. **Include: Cung cấp thông tin** | 2.1 Nhập thông tin trạng thái cư trú mong muốn.                         |
| 3. **Include: Cung cấp minh chứng** | 2.2 Tải lên tài liệu/minh chứng.                                       |
| 4. **Extend: Cung cấp thông tin bổ sung** *(nếu có yêu cầu thêm)* | 2.3 Ghi nhận dữ liệu bổ sung.                                          |
| 5. Hệ thống gửi yêu cầu đến Manager. | 2.4 Thông báo cho ban quản lý về yêu cầu mới.                           |
| 6. Manager xem xét yêu cầu.       | 2.5 Hiển thị thông tin chi tiết và minh chứng.                         |
| 7. **Include: Xác thực thông tin** | 2.6 Kiểm tra tính hợp lệ của thông tin và minh chứng.                  |
| 8. **Extend: Đồng ý**              |                                                                         |
| → **Include: Cập nhật trạng thái cư dân** | 2.7.1 Ghi nhận trạng thái mới cho cư dân.                             |
| → **Include: Cập nhật trạng thái phòng** *(nếu cần)* | 2.7.2 Cập nhật trạng thái phòng (trống, đang ở, bảo trì…).         |
| → **Include: Thông báo cho cư dân** | 2.7.3 Gửi thông báo phê duyệt đến cư dân.                             |
| 9. **Extend: Từ chối**             |                                                                         |
| → **Include: Thông báo cho cư dân** | 2.8 Gửi thông báo từ chối với lý do cụ thể.                           |

---

### **8. Điều kiện ngoại lệ:**

- Nếu cư dân không đăng nhập → chuyển đến trang đăng nhập.
- Nếu thiếu minh chứng → từ chối và yêu cầu bổ sung.
- Nếu quản lý không thể xác thực → chuyển tiếp hoặc tạm dừng xử lý.
- Nếu thông tin bổ sung bị thiếu hoặc không rõ ràng → hệ thống yêu cầu bổ sung.
