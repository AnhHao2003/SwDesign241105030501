## I.Ca Sử Dụng "Create Administrative Report"
***1. Các lớp phân tích cho ca sử dụng "Create Administrative Report":***
  
BáoCáo (Report):

* Mô tả: Đại diện cho báo cáo hành chính, chứa các thông tin chi tiết liên quan đến báo cáo, như loại báo cáo và thời gian.
  
* Thuộc tính:

      -  mãBáoCáo: String
      -  loạiBáoCáo: String
      - thờiGianBắtĐầu: Date
      - thờiGianKếtThúc: Date
      -  tênNhânViên: String
      
* Phương thức:
  
      - thiếtLậpTiêuChí(): Nhận thông tin tiêu chí cho báo cáo từ Payroll Administrator.
      - hiểnThị(): Hiển thị báo cáo theo các tiêu chí đã chỉ định.
  
QuảnLýBáoCáo (ReportManager):

Mô tả: Chịu trách nhiệm tạo, lưu trữ và quản lý báo cáo trong hệ thống.
Thuộc tính:
danhSáchBáoCáo: List<BáoCáo>
Phương thức:
tạoBáoCáo(): Tạo báo cáo dựa trên các tiêu chí được chỉ định.
lưuBáoCáo(): Lưu báo cáo vào vị trí và tên được chỉ định.
QuảnTrịViên (Payroll Administrator):

Mô tả: Người sử dụng hệ thống để tạo và quản lý báo cáo.
Phương thức:
yêuCầuBáoCáo(): Yêu cầu tạo báo cáo và cung cấp thông tin tiêu chí.
lưuBáoCáo(): Lưu báo cáo vào vị trí đã chỉ định.
Biểu Đồ Tuần Tự (Sequence Diagram)
