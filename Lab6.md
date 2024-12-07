
# Class Design - Payroll System  
### 1.Authentication Subsystem
## Xác định Operations & Methods  

### Operations:  
- **login()**: Thực hiện xác thực thông tin đăng nhập.  
- **logout()**: Đăng xuất khỏi hệ thống.  
- **validateUser()**: Kiểm tra thông tin đăng nhập.  
- **grantAccess()**: Cấp quyền truy cập dựa trên vai trò.  

## Xác định Trạng Thái (State)  

### State:  
- **LoggedOut**: Trạng thái mặc định, chưa đăng nhập.  
- **LoggedIn**: Đã xác thực và đăng nhập thành công.  

## Thuộc Tính (Attributes)  
- **userId**: int  
- **password**: string  
- **role**: string  
- **session**: string  

## Dependencies & Associations  
- **LoginForm** phụ thuộc vào **SecurityManager**.  
- **SecurityManager** phụ thuộc vào **Role Entity** để kiểm tra và xác định vai trò của người dùng
## Sơ đồ minh họa

![diagram](https://www.planttext.com/api/plantuml/png/R95DJiD038NtSmghgxB81R90HVn8IC2YbTYxYHKi9ZFLs8CK8Kx6WYDn1PmqefF2B9_ztcTxlZ-_DgAODFSUhhA-K51kK3c6NTxB84gzSmTiNh4ZM2qxuBTb1UyEx3KUHU0XTXpkOkfdzVWu7B9U9sh70FIolfYA7wvmxgZ9YNLun62yLFWho4BflgqjHmkLfPY9hBoFqHE60lo6dbihJcFzHzsQuzOIT5W0ayb_WQFwX3tL89euT0N8ihWBOzgIShf7LLsUxrYR4DhvQ723YfFd_1AZypHd3S_pKiVfdP4s5cE_w7u0003__mC0)
  
## 2. Timecard Management Subsystem  

## Xác định Operations & Methods  

### Operations:  
- **displayTimecard()**: Hiển thị thông tin bảng chấm công.  
- **editTimecard()**: Chỉnh sửa thông tin bảng chấm công.  
- **saveTimecard()**: Lưu thông tin về cơ sở dữ liệu.  
- **fetchProjectCode()**: Lấy thông tin mã dự án từ cơ sở dữ liệu.  

## Xác định Trạng Thái (State)  

### State:  
- **ViewingTimecard**: Đang xem thông tin bảng chấm công.  
- **EditingTimecard**: Đang chỉnh sửa thông tin bảng chấm công.  
- **SavingTimecard**: Đang lưu thông tin.  

## Thuộc Tính (Attributes)  
- **timecardId**: int  
- **employeeId**: int  
- **projectCode**: string  
- **hoursWorked**: float  

## Dependencies & Associations  
- **TimecardController** phụ thuộc vào **ProjectManagementDatabase**.  
- **TimecardForm** sử dụng **TimecardController** để thao tác thông tin.

## 3.Payroll Processing Subsystem  

## Xác định Operations & Methods  

### Operations:  
- **calculatePayroll()**: Thực hiện tính lương.  
- **generatePaycheck()**: Tạo thông tin phiếu lương.  
- **processPayment()**: Thực hiện thanh toán.  
- **checkPayday()**: Kiểm tra thời điểm thanh toán.  

## Xác định Trạng Thái (State)  

### State:  
- **PayrollPending**: Trạng thái chờ xử lý bảng lương.  
- **PayrollProcessing**: Trạng thái đang xử lý bảng lương.  
- **PayrollCompleted**: Trạng thái đã hoàn thành xử lý bảng lương.  

## Thuộc Tính (Attributes)  
- **employeeId**: int  
- **salary**: float  
- **paycheckId**: string  
- **bankTransactionStatus**: string  

## Dependencies & Associations  
- **PayrollController** phụ thuộc vào **BankSystem** và **PrinterInterface**.

## 4.Reporting Subsystem  

## Xác định Operations & Methods  

### Operations:  
- **generateReport()**: Tạo báo cáo thống kê lương.  
- **integrateFinancialReport()**: Dữ liệu từ báo cáo tài chính.  

## Thuộc Tính (Attributes)  
- **reportId**: string  
- **financialData**: string  

## Dependencies & Associations  
- **FinancialReportController** phụ thuộc vào **PayrollArtifacts**.

## 5.Employee Management Subsystem  

## Xác định Operations & Methods  

### Operations:  
- **addEmployee()**: Thêm thông tin nhân viên mới vào hệ thống.  
- **updateEmployeeInfo()**: Cập nhật thông tin nhân viên.  
- **deleteEmployee()**: Xóa thông tin nhân viên khỏi hệ thống.  
- **updatePaymentMethod()**: Thay đổi phương thức thanh toán của nhân viên.  

## Xác định Trạng Thái (State)  

### State:  
- **EmployeeActive**: Thông tin nhân viên hợp lệ và đang hoạt động.  
- **EmployeeInactive**: Thông tin nhân viên nhưng không còn hoạt động.  
- **EmployeeDeleted**: Thông tin nhân viên đã bị xoá khỏi hệ thống.  

## Thuộc Tính (Attributes)  
- **employeeId**: int  
- **name**: string  
- **address**: string  
- **paymentMethod**: string  
- **position**: string  
- **isActive**: boolean  

## Dependencies & Associations  
- **EmployeeForm** phụ thuộc vào **EmployeeEntity** để thao tác thông tin nhân viên.  
- **PayrollController** phụ thuộc vào **EmployeeForm** và **EmployeeEntity** để cập nhật thông tin nhân viên và phương thức thanh toán.

## 6.Security and Access Management Subsystem  

## Xác định Operations & Methods  

### Operations:  
- **manageAccess()**: Kiểm tra và phân quyền cho từng người dùng.  
- **checkRole()**: Xác định vai trò và cấp quyền.  
- **grantPermissions()**: Cấp quyền dựa theo thông tin xác thực.  

## Xác định Trạng Thái (State)  

### State:  
- **AccessGranted**: Quyền truy cập đã được cấp.  
- **AccessDenied**: Quyền truy cập bị từ chối.  

## Thuộc Tính (Attributes)  
- **userId**: int  
- **role**: string  
- **permissions**: list  

## Dependencies & Associations  
- **SecurityManager** phụ thuộc vào **RoleEntity** để cấp quyền.  
- **EmployeeEntity** liên kết thông tin vai trò của người dùng.
