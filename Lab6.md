
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
  
