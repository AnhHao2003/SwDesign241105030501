## I.Ca Sử Dụng "Create Administrative Report"
***1. Các lớp phân tích cho ca sử dụng "Create Administrative***

**1.1 Employee (Nhân viên)**

* Thuộc tính:
  
          -employeeId: String
          -name: String
  
 Nhiệm vụ:
  
- Gửi yêu cầu tạo báo cáo.

- Cung cấp thông tin cần thiết để tạo báo cáo.

**1.2 Report (Báo cáo)**

* Thuộc tính:
  
          -reportId: String
          -reportType: String // "Total Hours Worked", "Total Hours Worked for a Project", "Vacation/Sick Leave", "Total Pay Year-to-Date"
          -beginDate: Date
          -endDate: Date
          -content: String
  
 Nhiệm vụ:
- Lưu trữ thông tin báo cáo.</p>
- Cung cấp phương thức để xuất báo cáo.</p>

**1.3 Report3Generator (Máy tạo báo cáo)**

* Thuộc tính:
  
            -reportTemplate: String </p>
 Nhiệm vụ:
  
- Tiếp nhận tiêu chí từ Employee.</p>
- Tạo báo cáo theo tiêu chí báo cáo đã nhập.</p>

**1.4 ProjectManagementDatabase (Cơ sở dữ liệu quản lý dự án)**

 Nhiệm vụ:
  
- Cung cấp danh sách số charge cho báo cáo “Total Hours Worked for a Project”.</p>
- Lưu trữ và cung cấp thông tin về các dự án.

**1.5 ReportService (Dịch vụ báo cáo)**

  Nhiệm vụ:
  - Quản lý quy trình tạo báo cáo, bao gồm validate thông tin đầu vào và xử lý lưu báo cáo.

**1.6 ErrorHandler (Xử lý lỗi)**

Nhiệm vụ:

- Thông báo lỗi khi thông tin không đủ hoặc không hợp lệ.

