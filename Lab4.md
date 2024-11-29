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

### **Sơ đồ minh họa**
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

### **Sơ đồ minh họa**
![diagram](https://www.planttext.com/api/plantuml/png/V5793S903Fox2ZUG1l90aJX-I3nemDar4BH7v7MGKXiFIg854d4aY8IdxHdFU7o_tega9Dfu1sGq2gvzxMBB36LiWYLfSLzvDYHs4yM3YK4bkazp-QmT2rXIAYanxYIUsUYM0XtPSz3LQmBmtexPucjlZh7cWFfgmNWsnWvoEGghL7pXNzQ0whcpTd8yi9eJziPX5eNPl7uZ4vx7wZzdsYhLZjg1DPz8KtV69gxxbqcYBWzped3a10K7sp_s0G00__y30000)

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

### **Sơ đồ minh họa**

![diagram](https://www.planttext.com/api/plantuml/png/T591JiGm3Bpd5Vu07-W1hUXUE21MWW-OnAj6JUBASK1z6mUUn1T8jYnTA7j9OZip6O_p-VwnougY9GQ3LbdWQSvAiGziHsCvgN200yvr2_qI1X93IRtEyEmZMHHtZWz5x82P7iMjbohQ3bJfNhWaXr8pufEItBVbY9RMoXscSL5Wp8KIkBdTYkZWH0iJpWvdiwatq5bW1q8gdbu9tbX66BX8_X_oguSBdEKOVSwU4_Xqv2lWxrwhDWos15Hg-cArmc3GLczdU20TkAhQUo6hiAU9irS3souRw-fA1vcI-w6aa6d3kRZhe3-PVeNoxmWwc5gcCI_3gi-ONLtQp_W2003__mC0)

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

### **Sơ đồ minh họa**
![diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aO9hRa5EVcLgAbTIVcbUIc9HfK90OcLHVawEStvU2OXEBU9ApIl9BAb4AEM2iHHqxJ2LMoaKf-Qa9fSe52HMvWArAkIcbcJaft1XA0JfXfbafL1Qa99OaegkoI4rBmNaM000003__mC0)

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
### **Sơ đồ minh họa**
![diagram](https://www.planttext.com/api/plantuml/png/V90v3i9034NxEOLBA11z2XGKe8u4eX_D618nI-8uHSv6mP6u0jbS1QModkHd-_lx_gGDQ-BMEwKDHuAZzMLG9WQcw23NNLzSDg53KXYuv0xEldAnGnI-bHwD9YlSYwP0yr9g70Yxmt9M0eHrYmttjOh4Qj4nQB8fWGUoAG1d1gjP_rVa655uvXL5xXMbcffMZ35N0ayCI9fnpW2R_7JPPzVxLgKOxF3N7m000F__0m00)

## 6. Manage Employee Information (Quản lý thông tin nhân viên)

### **Mô tả**
- Quản trị viên có thể thêm mới, cập nhật, hoặc xóa thông tin nhân viên.
- Thông tin bao gồm: tên, địa chỉ, số điện thoại, phương thức thanh toán, thông tin ngân hàng, và vai trò.

### **Thành phần tham gia**
- **EmployeeForm**: Giao diện nhập và hiển thị thông tin nhân viên.
- **Employee Entity**: Lưu thông tin chi tiết của nhân viên.
- **SecurityManager**: Kiểm tra quyền truy cập của quản trị viên.

### **Lý do thiết kế**
- Đảm bảo tính linh hoạt khi có thay đổi nhân sự.
- Hỗ trợ quản trị viên cập nhật thông tin nhanh chóng và chính xác.

### **Sơ đồ minh họa**
![diagram](
https://www.planttext.com/api/plantuml/png/T90nRiCm34LtdO8NAB9xAD8XMOfqIGUlhAn61YmgbUa27ejS9CaOm5CpnKC7dSGdo1Kg6d4wTIB1__a-mMl_CwyP0pUkKgZP1tWgN4c0DQ0qwiqtL61eOU6sbM-DMVhWH7vFLMbF77m5QwERK7AxGiAD2QBNjv4onAdSzqKpjrwfCGGU7aTS1Yzsk7HRO1lFj05E4jbu9FWiuucKUCGxeJDuBeT-vu03maVJ3lqNgKdyW-Rne1CdaMboISAUB6Z9kNEdip9ujV7aPkkXxt2Mns_yxwAveK9Uzmi00F__0m00)

## 7. Access Management (Quản lý quyền truy cập)

### **Mô tả**
- Quản trị viên có thể cấu hình quyền truy cập cho từng loại người dùng:
  - Nhân viên chỉ có thể xem thông tin cá nhân và bảng lương.
  - Quản trị viên có toàn quyền quản lý hệ thống.
  - Kế toán viên có quyền xem và tạo báo cáo.

### **Thành phần tham gia**
- **SecurityManager**: Quản lý việc kiểm tra và phân quyền.
- **Role Entity**: Lớp mới lưu trữ vai trò và quyền hạn của từng người dùng.

### **Lý do thiết kế**
- Đảm bảo tính an toàn và bảo mật của hệ thống.
- Dễ dàng mở rộng khi hệ thống cần hỗ trợ vai trò mới.


### **Sơ đồ minh họa**
![diagram](https://www.planttext.com/api/plantuml/png/H90nIWGn58RxdE9TGEoda9K56x5n5MopcJWJcBpiPfA5AHTBpo0eOhEm86BZfh08U8-Sm2kOD-FiL7zu-Vx_Vybl-9wrZbldTSEuSCR2UQaL0c-1qu4jZSUIsmwkJIElEF9AQedkmbXDq7rM9WmwQnfOIE6jSjs0MRfl_qSiUxBqAJJFk1ndj-t0-goCzRLmSjP75t1Jnvq-NQImvx3sNGfR16Tz1o8TzYj64C5ZJm6NAeK7dPc9N_jqU2LR2e-mKN67REIdehlu8W3hd8fJKHsViGOHFx4wLj7g1SofVk0TRBZAwV43iFfvJ-59GHc_ieLGij3B2eZR5PGfl65rDB2Pn9B-_Wy00F__0m00)
