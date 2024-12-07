
# Authentication Subsystem  

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
