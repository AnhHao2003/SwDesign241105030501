
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

## Sơ đồ minh họa

![diagram](https://www.planttext.com/api/plantuml/png/V95D2i8m48NtESNWIXUzG1SYA0KNYg0UO4n7hJP9oKmL4K_cmYDv1IkjsletotbVtdj9hkTBZmMzv2Q5MM98euz7Q755XgnCymKVMCWebQ7U5bjeFIXuOV3aMd1KK8nEaVbfs7TMl4jJyfLS3iM9F91sfoOmxkXDEAallf7pfk78QxV_Tt3YtOQql9eFK721J3MN0BAI6iOX95O-XJ4Q2e759tPL2r-Iw7MLCBHBropmvIs2eDkuIWXp9lv7_-mVGdHF9uRxHXMPFR9nyQdg1W00__y30000)

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

## Sơ đồ minh họa

![diagram](https://www.planttext.com/api/plantuml/png/V98zRiCm38LtdOB8r0o-W8SYI08KtG8OFG0hCwvXMJ94UH2Adgn3ZzGhb8dbH47SS16Wz_ZnH_hz_jbmG1_6ti01etV67BpJnDpQfXhVENAWNga1TOSDmIgPuEg2Ysq5dmeaj47c6RTpDfnEyacTOfZoa-bfdKaDMV8OIBJAj4FIlbJ6hixrTiRfxjK6yaVKbE4B633M64lO2oT3wm_IdN3t69UmefmTDoX6WrvGH-CmPFUreEyAjCmZBQ6tQBkfwt_Mq9CDjudt2ooAvyNHItXZuWT9ys0blAJbFd9VUotdTnQ_TBKXMyjFKNy0003__mC0)

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

## Sơ đồ minh họa

![diagram](https://www.planttext.com/api/plantuml/png/T94z3i8m38Ntd2Bg14Clq061G9NO48W3cDIKYZGjiJiWnCaOE19N86bHbGBrw6T_pp-lntDE39QRKiijrfNbmkIxva1NOYo5g46T8KSPzQBirKZUX7IXD11zkjFAbfzq5nOl3H9twcJQAdSHzAM50QCAq5t9iZ9iAwtH3Z0v6hJ0EE1qKHZ6t6izQGKC_wmsSFNeXTlZ28efS8ZTe9wypX8F3FAPWoMIsBhT0zSZiZhz6WLNYEFP-7A9gsmFGstR-14yvNlkHEu9IJZBEPhClKwy0G00__y30000)
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
## Sơ đồ minh họa

![diagram](https://www.planttext.com/api/plantuml/png/n9F1QiCm38RlVWhHqtR82-GmEaO7FHGAOm-WnbfdPil1KWfXxCbss2Fj5UQmf4t057QQZlf-ITQF_FtvjHR5f5tmi0cjZptH3XcF58ZrgJj8Bqh1c1QRjvo5rQI2YmpEkXMy6yZHU1GfD7o8h2bwJsaK3b41ZSAjhS6npWXZe1f4a-FZB8tM9X8fa1RxOT2Ez3NQ4e_Yr4Kk82VtZRfJddU8qHFocS4mSDhcvdQMxrgBIXFQyajSO4kUBhXGkPy_T-GVfk3XOqnXvbbkxQJrs0_vQtKRLgVzmcttZou329weuD5oXwkNKrLt2rjgU1QIlzNzsbAFHomcprqJs_mDp0y0003__mC0)
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
## Sơ đồ minh họa

![diagram](https://www.planttext.com/api/plantuml/png/d9AnJiD038RtUmgh4mnvWGXLxT012If49VRZugPMSqvqTeQeuiaOU2HUWGj9oxMaGiAZ_z_sTpv_ldyiH6tGrbUmGTS6qcx9nT8v5DcqhzA9eZUciMvlIuJPqGIM2nXiy6WvQXvPuLGoWuE16AwoqN6i6fnXrFh8e1KCzqKEn9faGrrX3gA1k4pI3GPF8bIpvF10edU3PNxo0FZl8GFRpMqYk1sw_NDiV9OjWsLz-kaxYcycuU-BLgpzkmyNaDFeQ-l_Yn_dKSb_0AryKzKTJa7HBo2UXfbSCS0MrUskZh_yoIoR9zl9uGK3RGdbglcSF1-FHqpilq0kuY6QBm000F__0m00)
