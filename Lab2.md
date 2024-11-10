## I.Ca Sử Dụng "Create Administrative Report"
***1. Các lớp phân tích cho ca sử dụng "Create Administrative***
**Xác định các lớp phân tích**

Từ mô tả, các lớp phân tích chính như sau:

*PayrollAdministrator* - Đại diện cho người yêu cầu và quản lý việc tạo báo cáo.</p>
*Hệ thống* - Xử lý tương tác tổng thể để tạo báo cáo, nhắc nhở tiêu chí, tạo báo cáo và lưu báo cáo nếu cần.</p>
*Báo cáo* - Biểu thị dữ liệu báo cáo được tạo dựa trên các tiêu chí đã chỉ định.</p>
*ReportCriteria* - Ghi lại các tiêu chí để tạo báo cáo (ví dụ: loại, ngày tháng, tên nhân viên).</p>
*FileManager* - Chịu trách nhiệm lưu báo cáo vào vị trí đã chỉ định nếu được yêu cầu. </p>

**Xác định trách nhiệm và thuộc tính**

> - Quản trị viên tiền lương*

* Thuộc tính :
  
       - administratorID,
       -  name
  
* Trách nhiệm :  Yêu cầu tạo báo cáo, chỉ định tiêu chí, quyết định lưu hay hủy báo cáo.</p>
*Hệ thống*

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.</p>
* Trách nhiệm : Quản lý quy trình tạo báo cáo, xác thực thông tin, hiển thị báo cáo và lưu hoặc hủy báo cáo theo yêu cầu của Quản trị viên tiền lương.</p>
*Báo cáo*

* Thuộc tính :
  
        - reportID, 
        - type, 
        - content,
        - creationDate
* Trách nhiệm : Lưu trữ nội dung báo cáo được tạo dựa trên các tiêu chí đã chỉ định.</p>

*Tiêu chuẩn báo cáo*

* Thuộc tính :
  
        - reportType,
        - beginDate,
        - endDate,
        -  employeeNames
  
* Trách nhiệm : Lưu trữ các tiêu chí cần thiết để tạo báo cáo.</p>
*Trình quản lý tập tin*

* Thuộc tính :
  
        - filePath,
        - fileName
*Trách nhiệm : Lưu báo cáo vào đường dẫn đã chỉ định nếu được yêu cầu.

**Biểu đồ trình tự**
