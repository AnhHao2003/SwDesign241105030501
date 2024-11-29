
# Payroll System - Subsystems Design

## **1. Authentication Subsystem**
### **Mô tả**
Hệ thống con chịu trách nhiệm xác thực người dùng và quản lý quyền truy cập.

### **Chức năng chính**
- Xác thực thông tin đăng nhập.
- Quản lý phiên làm việc (session).
- Cấp quyền truy cập dựa trên vai trò.

### **Thành phần**
- **LoginForm**: Giao diện nhập thông tin đăng nhập.
- **SecurityManager**: Xác thực thông tin người dùng và quyền truy cập.
- **Role Entity**: Quản lý vai trò của người dùng.

### **Mối quan hệ với Use Cases**
- **Login**
- **Access Management**

### **Sơ đồ minh họa**

![diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWf9ZQKb6Qbv9Pd9YIMP-da9mQL9nPN59QgwIGZMNWaAqJtvwPfvRVb5kB8WNd9fSMfHPKkcRc0VKN0GM2yhFIOtbgkNYGbAheAjhXwbQmKh1_U7kjPaA9Hc7j-IbAvHavYaScNYa6SZCotYuQsq15wOMi45WAu2w8mulJ5R8pSpBK2WihNoukp5FeQIej58X6QpN8JKl1UWp00000F__0m00)


## **2. Timecard Management Subsystem**  

### **Mô tả**  
Hệ thống con quản lý bảng chấm công, hỗ trợ nhân viên ghi lại giờ làm việc và thông tin dự án liên quan.  

### **Chức năng chính**  
- Hiển thị, chỉnh sửa và lưu bảng chấm công.  
- Truy xuất mã dự án từ cơ sở dữ liệu quản lý dự án.  

### **Thành phần**  
- **TimecardForm**: Giao diện quản lý bảng chấm công.  
- **TimecardController**: Điều khiển các thao tác với bảng chấm công.  
- **ProjectManagementDatabase**: Lưu và truy xuất thông tin mã dự án.  

### **Mối quan hệ với Use Cases**  
- **Maintain Timecard**

### **Sơ đồ minh họa**

![diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWb98PcvgSc9HYe9lOXvG83SrhqGXk3IfkBAu93LNIQ6QIq4X6gR6BRyeDnPPm3a_hwGeFoSdjGWi752KdvMQN88moIMn934fiJWrbgkMYmlL60LTNJki1YbOARW_tBqsKw7oyAfIXUI7kvO3oOo7kplpCXIAWHA9N5XrWOt3xG2WgI55fPKA5QKFToqjKSWzl5WXvU7kZGg75-PnEQJcfO3210000F__0m00)

## **3. Payroll Processing Subsystem**  

### **Mô tả**  
Hệ thống con xử lý toàn bộ quy trình tính toán lương và thực hiện thanh toán.  

### **Chức năng chính**  
- Tính toán lương và tạo phiếu lương.  
- Xử lý giao dịch ngân hàng hoặc in phiếu lương.  
- Kiểm tra thời điểm trả lương (payday).  

### **Thành phần**  
- **PayrollController**: Điều phối toàn bộ quy trình xử lý lương.  
- **SystemClockInterface**: Xác định thời điểm trả lương.  
- **Paycheck**: Lưu trữ thông tin phiếu lương.  
- **BankSystem**: Xử lý giao dịch ngân hàng.  
- **PrinterInterface**: Hỗ trợ in phiếu lương.  

### **Mối quan hệ với Use Cases**  
- **Run Payroll**  
- **Select Payment Method**

### **Sơ đồ minh họa**

![diagram](https://www.planttext.com/api/plantuml/png/X56zQiCm4Dxr54Vsl4274fgXb2w1T2iPhgfg2SjIa4w32Pdw71bCXa2WqA6JFMGmv3tq17s5oea9eIJj94xt_TtTTxCRUK97eT1iZZp7JC1WWgMpMiF4MIwyLoQ3QNZnfITH363109vxoDWQwbxXPjtlz00PQylp1qF2lI4NinxEfU3veRX3an-HnvvJ7VQCi6JiWW4CXxTNBE067bLitWiWXq0oDYi5cKAJwbYlGUy_zvN9hgkUyYMbfrXN5kPInNeN_gUUJPF8zx7vK2b1-vMMHYe5a6Waa6qhyuVzxnMSbCfs6u37UXCWYVMXs4YOr-vYFm000F__0m00)

## **4. Reporting Subsystem**  

### **Mô tả**  
Hệ thống con hỗ trợ tạo và xuất báo cáo liên quan đến lương, phục vụ các bên liên quan.  

### **Chức năng chính**  
- Tạo báo cáo thống kê lương.  
- Tích hợp dữ liệu tài chính để xuất báo cáo tài chính.  

### **Thành phần**  
- **ReportForm**: Giao diện nhập yêu cầu báo cáo.  
- **FinancialReportController**: Tổng hợp dữ liệu và tạo báo cáo.  
- **PayrollArtifacts**: Cung cấp dữ liệu liên quan đến lương.  

### **Mối quan hệ với Use Cases**  
- **Generate Reports**  
- **Integrate Financial Reports**

### **Sơ đồ minh họa**

![diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWb9GQa5-KKbcNhf2S6bISMLnIMgkaa8rbu92D4J6BRyeDnR4TSlCIynBpapCWOWxv-UL5ENdvAGMWMK34Yj1F4UWKMc9oIN5iLorN5p8HYZewjhXCqJ1Ii7zuUwrcGgLXrULAYG_tBMyLA7auQw5-Gf9Xu54Cf3WmgSTR3o6Au2c-ZpSjRHI8UNXxlKAEPaFTxUNAkGSst1iOLuwbqDgNWeeB000003__mC0)

---  

## **5. Employee Management Subsystem**  

### **Mô tả**  
Hệ thống con quản lý thông tin nhân viên, hỗ trợ thêm mới, chỉnh sửa và xóa thông tin.  

### **Chức năng chính**  
- Thêm mới, cập nhật và xóa thông tin nhân viên.  
- Cập nhật phương thức thanh toán của nhân viên.  

### **Thành phần**  
- **EmployeeForm**: Giao diện nhập và quản lý thông tin nhân viên.  
- **Employee Entity**: Lưu trữ thông tin chi tiết của nhân viên.  
- **PayrollController**: Cập nhật phương thức thanh toán của nhân viên.  

### **Mối quan hệ với Use Cases**  
- **Manage Employee Information**  
- **Select Payment Method**

### **Sơ đồ minh họa**

![diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWf9hRa5EVcLgge9lOXvG83SrhqGXk3IfkBAu93LNIQ6QIq4X6gR6BRyeDnPP0Cm9IAmioi_9SSxFAm7HgKMnNBLSNAYQ57HrxP2qALWf19O-tBKuJo7dy5w5aep3M_BI5KeoynJoCWulobCeopoyAeyBYy6OnZW_tBMs0AWDI9Ke56GSst1i8SYeZ8UxLoO3gSIy38MI_CCByxWSKlDIG1u70000__y30000)

---  

## **6. Security and Access Management Subsystem**  

### **Mô tả**  
Hệ thống con đảm bảo an toàn và kiểm soát quyền truy cập vào các chức năng của hệ thống.  

### **Chức năng chính**  
- Quản lý quyền truy cập.  
- Kiểm tra và phân quyền theo vai trò.  

### **Thành phần**  
- **SecurityManager**: Quản lý việc kiểm tra và phân quyền.  
- **Role Entity**: Quản lý vai trò và quyền hạn của người dùng.  
- **Employee Entity**: Liên kết thông tin vai trò của người dùng.  

### **Mối quan hệ với Use Cases**  
- **Access Management**

  ### **Sơ đồ minh họa**

![diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWb9mQd9fKMP9fK9YNeg2Ot9oQd6nWczY7b0kDpMlH26uDAcuihWaDLT9ePfBGI4QfXoYf2WM91QKdvCAPhZc5kJaLwO2ERLSN1XA5NHrxQ2A5QmKl3CVxcxELIWfIbGeBArykBin3yWkhLH8VhXhRG4NL1bO1znKeAx0qeUx5kSfv1pU2zUL_73tyaI5l8p3Y_8KoZ8FhyhZSaZDIm7v4G000F__0m00)


### **Minh họa các hệ thống con và mối quan hệ**
![diagram](https://www.planttext.com/api/plantuml/png/V9DBReCm48RtdCBAFbUeGj96gjHAKUYkOZ4nK-9YR6GF2rJrP5tqIBr20VD-BJryy__puk_dzs093EMfz3BW2SJ8TdvETrGaE93GYWNvpHQMCDsnBu-nznST2tNM9WshLu0yDuAALr1bigbZLoqnzBwzNl9DfCZ1HCnXQIa_qssPJheDdBGYewLir2z6VoAdNkaH26vW9vONAAeaLk8ShHKgdZaso4G_g96Jr3nvLeJc0pY63Sxlo9FwSGILEB8fIbJi865OonKpRMYf1FUbQ_ai52WkGBhuj7DNhrzAbHvanoPFQIPrWRWruvRf3Dj0k3AFeK6xQWOgOZwlfhhbjNuP8z_ION1IRBz_M4WT7uU3bivZeOL6SN6fgtY_wbLaU03hEhEps5XnPprPydXhZkhdDnkM0zoa3wYYwj_-1m00__y30000)



