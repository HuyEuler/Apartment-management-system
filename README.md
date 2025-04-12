
# TÀI LIỆU THIẾT KẾ HỆ THỐNG PHẦN MỀM QUẢN LÝ CHUNG CƯ

## 1. Mục đích tài liệu

Tài liệu này mô tả mục tiêu và phạm vi của hệ thống phần mềm quản lý chung cư, nhằm hỗ trợ Ban Quản Trị trong việc quản lý thu phí, thông tin cư dân và phương tiện một cách hiệu quả. Tài liệu cung cấp chi tiết về các chức năng, kiến trúc, các thành phần chính của hệ thống và hướng dẫn.

**Mục tiêu:**

- Tự động hóa việc thu phí và quản lý cư dân.
- Nâng cao hiệu quả vận hành của Ban Quản Trị.
- Cung cấp thông tin minh bạch về tình trạng cư trú và thanh toán.

**Đối tượng sử dụng tài liệu:**

- Nhóm phát triển phần mềm.
- Ban Quản Trị chung cư.
- Các bên liên quan trong quá trình xây dựng và triển khai hệ thống.

## 2. Tài liệu tham khảo

- Tài liệu yêu cầu hệ thống.
- Các tài liệu hướng dẫn kỹ thuật liên quan đến công nghệ sử dụng (React, Node.js, v.v.).
- Tiêu chuẩn bảo mật dữ liệu.

## 3. Định nghĩa và từ viết tắt

- UC: Use Case - Trường hợp sử dụng.
- Ban Quản Trị: Ban Quản Trị chung cư.
- Cư dân: Người sinh sống tại chung cư.
- Phí dịch vụ: Khoản phí bắt buộc hàng tháng dựa trên diện tích căn hộ.
- Phí quản lý: Chi phí vận hành chung cư, thu theo m2.
- Phí gửi xe: Phí đăng ký xe máy, ô tô hàng tháng.

---

# Instruction - Hướng dẫn đọc và sử dụng dự án Apartment Management

## Giới thiệu
Đây là project phân tích và thiết kế hệ thống quản lý chung cư (Apartment Management).  
Mục tiêu: mô tả đầy đủ quy trình phân tích, thiết kế từ yêu cầu → chức năng → luồng hoạt động → cơ sở dữ liệu.

---

## Cấu trúc thư mục của dự án

```
APARTMENT-MANAGEMENT/
│
├── Database/                     # Phân tích CSDL
│   ├── Apartment-management.png  # Sơ đồ ERD
│   ├── db-design.txt             # Thiết kế chi tiết CSDL
│   └── README.md
│
├── Functional-analysis/          # Phân tích chức năng
│   ├── activity-diagram/         # Activity Diagram
│   ├── usecase-diagram/          # Usecase Diagram (Client, Manager, Service-provider)
│   ├── image.png
│   ├── quanlidanccu.png
│   ├── quanlycanho.png
│   └── README.md
│
├── Instruction/                  # Hướng dẫn đọc dự án (file này)
│
├── Interactive-analysis/         # Sequence Diagram
│   └── sequence-diagram/
│   └── README.md
│
├── Meeting-notes/                # Ghi chú quá trình làm việc
│   └── 30-3.md
│
├── Requirement-analysis/         # Phân tích yêu cầu
│   ├── Functional_Requirements/  # Yêu cầu chức năng
│   ├── Non_Functional_Requirements/ # Yêu cầu phi chức năng
│   └── README.md
│
└── README.md                     # Giới thiệu tổng quan project
```

---

## Hướng dẫn đọc project cho người mới

| Thứ tự | Vị trí | Nội dung cần xem |
|--------|--------|-----------------|
|1|README.md (root)|Tổng quan nội dung project|
|2|Requirement-analysis/|Toàn bộ yêu cầu hệ thống|
|3|Functional-analysis/|Phân tích chức năng, sơ đồ Usecase, Activity|
|4|Interactive-analysis/|Phân tích luồng hoạt động qua sequence diagram|
|5|Database/|Thiết kế CSDL|
|6|Meeting-notes/|Theo dõi quá trình họp và thống nhất nhóm|

---

## Đối tượng sử dụng
- Thành viên mới tham gia project
- Người muốn hiểu nhanh project
- Reviewer / Teacher / Khách đọc file

---

## Lưu ý khi làm việc:
- Thêm mới tài liệu → cập nhật đúng folder
- Thêm sơ đồ → lưu dưới dạng .png hoặc .drawio kèm source
- Thay đổi file → commit message rõ ràng, dễ hiểu
- Cấu trúc folder đã được chuẩn hóa, không tự ý đổi vị trí

---

## Liên hệ hỗ trợ
Nếu có bất kỳ thắc mắc nào trong quá trình đọc hoặc sử dụng tài liệu, vui lòng liên hệ leader hoặc thành viên nhóm để được hỗ trợ.

---
