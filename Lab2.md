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

>  Quản trị viên tiền lương

* Thuộc tính :
  
       - administratorID,
       -  name
  
* Trách nhiệm :  Yêu cầu tạo báo cáo, chỉ định tiêu chí, quyết định lưu hay hủy báo cáo.</p>
>  Hệ thống

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.</p>
* Trách nhiệm : Quản lý quy trình tạo báo cáo, xác thực thông tin, hiển thị báo cáo và lưu hoặc hủy báo cáo theo yêu cầu của Quản trị viên tiền lương.</p>
>  Báo cáo

* Thuộc tính :
  
        - reportID, 
        - type, 
        - content,
        - creationDate
* Trách nhiệm : Lưu trữ nội dung báo cáo được tạo dựa trên các tiêu chí đã chỉ định.</p>

>  Tiêu chuẩn báo cáo

* Thuộc tính :
  
        - reportType,
        - beginDate,
        - endDate,
        -  employeeNames
  
* Trách nhiệm : Lưu trữ các tiêu chí cần thiết để tạo báo cáo.</p>
> Trình quản lý tập tin

* Thuộc tính :
  
        - filePath,
        - fileName
* Trách nhiệm : Lưu báo cáo vào đường dẫn đã chỉ định nếu được yêu cầu.

**Biểu đồ trình tự**

![Diagram](https://www.planttext.com/api/plantuml/png/X9FFIiD04CRlUOevAjGN42BLWdXGyKyFUbotQRAGRC9cKyZPenTxzDPOf50ir6jow65BtsEVm5TmDj6cAItcC8ITttpxpHVoNIpQiIH29e5l4If30JSa5Q7ld_O2nbai1J6798Q8M162ZBA8S0dtQIoTm3JYD6vqxfme5B8Zc7G48uOGT0TGDYBPw9mptxaYdBXEUMK_i2pRXjj4PT0LwfDxqDLv5iAPmj8nnRPH08vEZ0iuXaSrJO3gV9A0BCad0r4ibW6GGxg9iVBTKxCDjf8K5D5Embs3VaGxKJZmGxo8rISjuAuQfI0zbN6t1L9DEN1FlNCOe00_j51tRVXQ5s-xbVyCOqR8TPlRG4yNNmIaCEBrT6F92wQBP-nwkdZPc5mErRWAvpVSLESB2SjNn33WozKyCQaINrRlwwmjm6TFsBuXQ-k6t9UtSTp7xmm3DOA1yOPRp4g5ZHlwmLRs_utXmDhOWyeeHgxp6TzUV3bSpNKnfjMWuySENEXYacwjsSYnxDVBERndjR6ON-O7003__mC0)

**Biểu đồ lớp** 

 ![Diagram](https://www.planttext.com/api/plantuml/png/V5DDI-j05DtdLzobBkeFA2BL5X7KuaTu-v26P22Tw6GY1d7bKeJdKkJ1onCHV9JNdJ2pS36b_-F-0l-2TsmQOzDdO3PpxjnxxZadR_graqfFo6mOEtxifIaSUBb8udXpC6ISfL9uCX5muG1zBHYQXyCCrGDt1Uhh7ymySsZ3iHICXsM9RDm1vEOvww9wohPCaNJfhAoMY9_na9374vVPciYCAkWqor6zoibFciIZlUau8-ZIAMaUvwaCXYKn08cgI1hTgxdDxkUcyFiHgX5lOX53VSNTY0OtMiR4OoT1zUBle7xAQtX5xIWuIOIiQpQlMjGgfaO5MxpbgEzOZuHf0A7vdRjsKq9wdWpgo_VdhvQjqQJN5Km6WdaLpHcN_p7z6Bs5wf_rWmIj4oZHNUkM6ndbVmLj8FgH-SFdSTcZMAtFkc-KL2UtfAYiEr7HtMPniEznBmm-OpYvdOvH_-9X3zNVfGcqhnPJQAtxwjVIhBTQ6_DqjK5EnzE2d90K5pX3VS-S4hDb2rAs8KKzWW7gHnhQgBFjh5DrfBvT6qBKDyoAeQy-s3hbmxMrxsU1jCg1Jz8vdO0FxD_y3W00__y30000)

## II.Ca Sử Dụng "Create Employee Report"

**1: Xác định các lớp phân tích**

*Nhân viên* - Đại diện cho tác nhân yêu cầu và quản lý việc tạo ra nhiều báo cáo khác nhau.</p>
*Hệ thống* - Quản lý quy trình tạo báo cáo, nhắc nhở nhập tiêu chí, lấy số hiệu phí nếu cần, tạo báo cáo và lưu báo cáo nếu được yêu cầu.</p>
*Báo cáo* - Biểu thị dữ liệu báo cáo được tạo dựa trên các tiêu chí cụ thể.</p>
*ReportCriteria* - Lưu trữ các tiêu chí (loại báo cáo, ngày tháng và tùy chọn là số phí) để tạo báo cáo.</p>
*ProjectManagementDatabase* - Cung cấp số liệu tính phí khả dụng cho báo cáo "Tổng số giờ làm việc cho một dự án".</p>
*FileManager* - Xử lý việc lưu báo cáo vào một vị trí cụ thể nếu Nhân viên yêu cầu.</p>
**2: Xác định trách nhiệm và thuộc tính**

> Người lao động

* Thuộc tính : 

      - employeeID,
      - name
* Trách nhiệm : Yêu cầu tạo báo cáo, chỉ định tiêu chí, chọn số phí (nếu cần) và quyết định lưu hay hủy báo cáo.
> Hệ thống

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.</p>
* Trách nhiệm : Quản lý việc tạo báo cáo, nhắc nhở về tiêu chí báo cáo, lấy số hiệu chi phí (nếu cần), tạo báo cáo, hiển thị cho Nhân viên và xử lý việc lưu hoặc hủy bỏ dựa trên quyết định của Nhân viên.</P>
> Báo cáo

* Thuộc tính :
  
      - reportID,
      - type,
      -  content,
      -  creationDate
* Trách nhiệm : Lưu trữ dữ liệu báo cáo được tạo dựa trên các tiêu chí đã chỉ định.
> Tiêu chuẩn báo cáo

* Thuộc tính :
  
  -  reportType,
  -  beginDate,
  -  endDate,
  -  chargeNumber
* Trách nhiệm : Lưu trữ các tiêu chí cần thiết để tạo báo cáo, bao gồm các tiêu chí tùy chọn chargeNumbercho báo cáo cụ thể của dự án.
> Cơ sở dữ liệu quản lý dự án

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.


* Trách nhiệm : Cung cấp danh sách số chi phí cho các báo cáo theo dự án.</p>
> Trình quản lý tập tin

* Thuộc tính :  

      - filePath,
      - fileName
* Trách nhiệm : Lưu báo cáo vào một vị trí cụ thể nếu Nhân viên yêu cầu.
  
**3: Biểu đồ trình tự**

![Diagram](https://www.planttext.com/api/plantuml/png/X9J1Qjj048Rl-nH3JYsqBn1m2LMXEOX2g0ZjKLdBba1Q2sbbgcFeeOTIg0yzbjer8L1gcb9waGWvhF5xx1Fq5VgFxDgIar23XTZvPkUVVyR-KzySvThFT974mfTwbD6Bq7nLfv7vfiZFAKXIaI8UoIZrbQPZMx_pGbjFr933UPbtmXxo2YSqYwTcDdBmPIYJ7QOJIdKdvgncBstzvPcjVxWHIXKdXQtcoZNNEFffpXjDQT8_wrRDp7SLRb4FYIc3WqI8NezE2ZFRCEJP2fLP0ZKQUZs15kdn4sw53karz9EqrML1ka7Fc99u20R0CTxbekOTJRVWpQMP1EiKC0liHNedIm_Y4Kf5kvD7f8PcMf8EpKmD7mhXnvhSDRIJ7fif7Q3NJxWTfateEHpxJAwP9dJAvabomX6nSGJd3WJXisc2BOGoBojAUWFVBZGNbfJpFJACA6M9qlp2IVLRDQbDpjOeBuFRDBRr-HsPxL9hluuXwAr2HxP-Vrz2npE07zGU5AY--3S6R0whwCw8-cZM9vtnzkwy5lTBsQKk9sQ-dlbcQKfRtMXQVWI6nN5NLmLlIpCAVjyEegtzrXB5ZExMufOlxJrYqOCe3cYCoOvP7HfPD5UqQmoIlPtwNnuIjj9UiVKgjDL2xVU-dAokR3sNwyGWpWF-jL-MUvrslMo0rjfZGaTuyD_9Nm000F__0m00)

**Bước 4: Biểu đồ lớp**
![Diagram](https://www.planttext.com/api/plantuml/png/X5J1IkH04BtdA_he7iOFo64HPmw2mx2BGVOwH4atn9vnfdinY8V5WmTPs3ak8Xf51Dt1sPEGPl7GG_wZlc1_OQjZfkr9ps8W4EfLTxrwhof_rSl6MFH7GXwaGPpsnsFIe_g6xpBzmCbnGF1faGDzwqH3iYD6Z2SrABmO8Pb-a6qexkMcpWTjVDS-r4WiUOB8tJ1Y9eVgwHj4GNtdEw0cRSe-kSYXpA1u4VCVeCuvxPOpYT19K1FU0dKMuTa9Jsh6X0Weye5NtDBoYn_fFEvHAARSnyH8PbyaaXQho546wfGR0kTUmHIfRWsWU8wHv7tcu9Rz8kQARMCDgLEyAcVDA0VratLGLmz8z7KM6IKGwVJ5lYjERt5gLICkGQk7n_ILpl_8LjKteNWolg7cBeSQtJQkHbGNyJ8uVfEvELdp2QefN8yiqNQPepzN7L1FNMpbJ7v6psvvL__1q6_zZTlfID7BRDdBaqMt8_sBKtiomdk6jk7vf9o1kkH91uh7bOlmcj_WRAPWsNfdcrgjZqiJ719HpieSlmIE9FaAwe85Re8vu7iI6j6cP0_K7TPjvZjfbVbUmllQXTKQaADg3og7S64P6I89dzug4KEIu7upuw0whJG9BAtrzNTx8iBWM1FhRUppFVF3-WS00F__0m00)
