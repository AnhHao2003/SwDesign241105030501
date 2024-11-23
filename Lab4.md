# Payroll System Use Case Design

## 1. Login (Đăng nhập)

### **Mô tả**
- Người dùng nhập tên đăng nhập và mật khẩu vào hệ thống.
- Hệ thống xác thực thông tin đăng nhập.
- Nếu thành công, cho phép người dùng truy cập các tính năng dựa trên vai trò.

### **Thành phần tham gia**
- **LoginForm**: Lớp giao diện nhận thông tin đăng nhập từ người dùng.
- **Employee**: Lưu thông tin nhân viên, bao gồm tên đăng nhập, mật khẩu và vai trò.
- **SecurityManager**: Thực hiện xác thực tên đăng nhập và mật khẩu.

### **Lý do thiết kế**
- Bảo mật là yêu cầu cốt lõi của hệ thống để ngăn truy cập trái phép.
- LoginForm là một lớp boundary được thiết kế để cách ly giao diện với logic xử lý.
- SecurityManager xử lý việc xác thực và đảm bảo tính độc lập của chức năng bảo mật.

![diagram](https://www.planttext.com/api/plantuml/png/R90_Ra8n38Ttdy8ZIA3kRq0iT6gdYWEOn42aF0SvTgjtDWQEr2iq6Hvj4MFYt_Vvp_Vrjgr6QZvce615SLzPuL1S8kc4R-MKvBNe2A68QSdumS4rsVHEGgSMPR7smjruoMLY1kW2N6z-qG5RflrvAmYDZ2GHBrJhLz6uMC8zsAa7_O2Vb5CauyMCh-xi4XxINJ0FCk2HBPmnACS-8-KASmtNppefcwjWQqRFn7_s8RTpTmQoLAI1rRFztwDVOS3g8N2jBqTAsPLXonBRgNy0003__mC0)

---

## 2. Maintain Timecard (Quản lý bảng chấm công)

### **Mô tả**
- Nhân viên có thể xem, chỉnh sửa, hoặc lưu bảng chấm công của họ.
- Bảng chấm công có thể được tạo mới nếu không tồn tại.

### **Thành phần tham gia**
- **TimecardForm**: Giao diện người dùng cho việc quản lý bảng chấm công.
- **TimecardController**: Điều khiển các thao tác như lấy dữ liệu bảng chấm công hiện tại, cập nhật hoặc lưu bảng chấm công.
- **ProjectManagementDatabase**: Lấy danh sách mã dự án liên quan.
- **Employee**: Lưu thông tin cá nhân của nhân viên (ví dụ: ID, ngân hàng, số giờ làm).

### **Lý do thiết kế**
- Phân tách rõ ràng giữa giao diện (TimecardForm), logic điều khiển (TimecardController), và dữ liệu (ProjectManagementDatabase) để đảm bảo tính mô-đun và dễ bảo trì.
- Hỗ trợ linh hoạt cho nhân viên trong việc quản lý giờ làm việc của họ.

---

## 3. Run Payroll (Chạy bảng lương)

### **Mô tả**
- Hệ thống kiểm tra thời điểm trả lương (payday).
- Thu thập thông tin bảng chấm công, đơn hàng (nếu có) và tính toán lương.
- Tạo phiếu lương (paycheck) và gửi đến ngân hàng hoặc in ấn tùy theo phương thức thanh toán của nhân viên.

### **Thành phần tham gia**
- **PayrollController**: Điều phối toàn bộ quá trình xử lý lương.
- **SystemClockInterface**: Xác định ngày hiện tại để kiểm tra thời điểm trả lương.
- **Timecard**: Chứa thông tin số giờ làm việc của nhân viên.
- **PurchaseOrder**: Cần thiết cho nhân viên theo hình thức hoa hồng.
- **Paycheck**: Phiếu lương được tạo sau khi tính toán.
- **BankSystem**: Hỗ trợ giao dịch ngân hàng cho việc chuyển khoản.
- **PrinterInterface**: Hỗ trợ in phiếu lương nếu nhân viên yêu cầu.

### **Lý do thiết kế**
- PayrollController đảm nhận vai trò "control" chính, phối hợp tất cả các thành phần cần thiết.
- Phân tách rõ các chức năng như giao dịch ngân hàng (BankSystem) và in ấn (PrinterInterface) giúp dễ dàng mở rộng khi tích hợp hệ thống.

---

## 4. Select Payment Method (Chọn phương thức thanh toán)

### **Mô tả**
- Nhân viên có thể chọn hoặc thay đổi phương thức nhận lương (chuyển khoản, nhận phiếu lương giấy, hoặc nhận trực tiếp).

### **Thành phần tham gia**
- **Employee**: Lưu trữ phương thức thanh toán đã chọn.
- **PayrollController**: Cập nhật phương thức thanh toán trong cơ sở dữ liệu.

### **Lý do thiết kế**
- Đáp ứng yêu cầu tùy biến cho nhân viên về cách thức nhận lương.
- Hỗ trợ tính linh hoạt của hệ thống khi các phương thức thanh toán mới được bổ sung.

---

## 5. Generate Reports (Tạo báo cáo)

### **Mô tả**
- Hệ thống tạo báo cáo thống kê về bảng lương cho quản trị viên (theo tháng, quý, năm).
- Báo cáo có thể xuất dưới định dạng PDF hoặc CSV.

### **Thành phần tham gia**
- **PayrollController**: Thu thập dữ liệu từ các lớp liên quan.
- **Employee**: Cung cấp dữ liệu về nhân viên.
- **Timecard**: Dữ liệu về giờ làm việc.
- **Paycheck**: Dữ liệu về số tiền lương đã trả.

### **Lý do thiết kế**
- Phân tách việc tạo báo cáo ra khỏi các chức năng chính để dễ bảo trì.
- Hỗ trợ quản lý dễ dàng thông qua các báo cáo thống kê.

