## I.Ca Sử Dụng "Create Administrative Report"
***1. Các lớp phân tích cho ca sử dụng "Create Administrative***

*Employee (Nhân viên)*

* Thuộc tính:
                    - employeeId: String
                    - name: String
Nhiệm vụ:
Gửi yêu cầu tạo báo cáo.
Cung cấp thông tin cần thiết để tạo báo cáo.
Report (Báo cáo)

Thuộc tính:
reportId: String
reportType: String // "Total Hours Worked", "Total Hours Worked for a Project", "Vacation/Sick Leave", "Total Pay Year-to-Date"
beginDate: Date
endDate: Date
content: String
Nhiệm vụ:
Lưu trữ thông tin báo cáo.
Cung cấp phương thức để xuất báo cáo.
ReportGenerator (Máy tạo báo cáo)

Thuộc tính:
reportTemplate: String
Nhiệm vụ:
Tiếp nhận tiêu chí từ Employee.
Tạo báo cáo theo tiêu chí báo cáo đã nhập.
ProjectManagementDatabase (Cơ sở dữ liệu quản lý dự án)

Nhiệm vụ:
Cung cấp danh sách số charge cho báo cáo “Total Hours Worked for a Project”.
Lưu trữ và cung cấp thông tin về các dự án.
ReportService (Dịch vụ báo cáo)

Nhiệm vụ:
Quản lý quy trình tạo báo cáo, bao gồm validate thông tin đầu vào và xử lý lưu báo cáo.
ErrorHandler (Xử lý lỗi)

Nhiệm vụ:
Thông báo lỗi khi thông tin không đủ hoặc không hợp lệ.

