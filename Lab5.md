
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

### **Sơ đồ Component**

![diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWf9ZQKb6Qbv9Pd9YIMP-da9mQL9nPN59QgwIGZMNWaAqJtvwPfvRVb5kB8WNd9fSMfHPKkcRc0VKN0GM2yhFIOtbgkNYGbAheAjhXwbQmKh1_U7kjPaA9Hc7j-IbAvHavYaScNYa6SZCotYuQsq15wOMi45WAu2w8mulJ5R8pSpBK2WihNoukp5FeQIej58X6QpN8JKl1UWp00000F__0m00)


