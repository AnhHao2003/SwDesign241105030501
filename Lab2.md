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
       - name
  
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
        - employeeNames
  
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
      - content,
      - creationDate
* Trách nhiệm : Lưu trữ dữ liệu báo cáo được tạo dựa trên các tiêu chí đã chỉ định.</p>
> Tiêu chuẩn báo cáo

* Thuộc tính :
  
       - reportType,
       - beginDate,
       - endDate,
       - chargeNumber
    
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

**4: Biểu đồ lớp**
![Diagram](https://www.planttext.com/api/plantuml/png/X5J1IkH04BtdA_he7iOFo64HPmw2mx2BGVOwH4atn9vnfdinY8V5WmTPs3ak8Xf51Dt1sPEGPl7GG_wZlc1_OQjZfkr9ps8W4EfLTxrwhof_rSl6MFH7GXwaGPpsnsFIe_g6xpBzmCbnGF1faGDzwqH3iYD6Z2SrABmO8Pb-a6qexkMcpWTjVDS-r4WiUOB8tJ1Y9eVgwHj4GNtdEw0cRSe-kSYXpA1u4VCVeCuvxPOpYT19K1FU0dKMuTa9Jsh6X0Weye5NtDBoYn_fFEvHAARSnyH8PbyaaXQho546wfGR0kTUmHIfRWsWU8wHv7tcu9Rz8kQARMCDgLEyAcVDA0VratLGLmz8z7KM6IKGwVJ5lYjERt5gLICkGQk7n_ILpl_8LjKteNWolg7cBeSQtJQkHbGNyJ8uVfEvELdp2QefN8yiqNQPepzN7L1FNMpbJ7v6psvvL__1q6_zZTlfID7BRDdBaqMt8_sBKtiomdk6jk7vf9o1kkH91uh7bOlmcj_WRAPWsNfdcrgjZqiJ719HpieSlmIE9FaAwe85Re8vu7iI6j6cP0_K7TPjvZjfbVbUmllQXTKQaADg3og7S64P6I89dzug4KEIu7upuw0whJG9BAtrzNTx8iBWM1FhRUppFVF3-WS00F__0m00)

## III. Ca Sử dụng cho "Login"

**1. Xác định các lớp phân tích**

Từ trường hợp sử dụng "Đăng nhập", các lớp phân tích cần thiết là:

*Người dùng* - Đại diện cho tác nhân đang cố gắng đăng nhập vào hệ thống.</p>
*Hệ thống** - Quản lý quy trình đăng nhập, xác thực thông tin người dùng và cung cấp phản hồi về thành công hay thất bại.</p>
*AuthenticationService* - Xử lý việc xác thực thông tin đăng nhập của người dùng.</p>
**2. Xác định trách nhiệm và thuộc tính**

> Người sử dụng

* Thuộc tính :
  
         - username,
         - password
* Trách nhiệm : Bắt đầu quá trình đăng nhập bằng cách nhập tên người dùng và mật khẩu.</p>

> Hệ thống

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.</p>
* Trách nhiệm : Yêu cầu thông tin đăng nhập, tương tác AuthenticationServiceđể xác thực thông tin đăng nhập, đăng nhập người dùng khi thành công và hiển thị thông báo lỗi khi không thành công.</p>
> Dịch vụ xác thực

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.</p>
* Trách nhiệm : Xác minh tên người dùng và mật khẩu đã nhập và trả về phản hồi thành công hoặc thất bại cho System.</p>

**3. Biểu đồ trình tự**

![Diagram](https://www.planttext.com/api/plantuml/png/Z58_IyD05D_lKxnHGRz08TAXGwU24CGrlOHUQ7e9oKlHkOD35piv2GrIHB6W88YvmU62t-C-WL_1Tud1fYxUS1pl_VwyF_UbFlePUYdciuXv7ECKHfFFPwDkmu5-bnFmCf0-ImWHyZ3n9CBGg2jN6BLgiW8xsO5HIoxEZDgSwu9Rt0ktC7z-WOmv3fpckW0trKzIG7LTBKXb94ovJS1ncFJX-8GaeTS6KJzAg5OrJZQXkLx3Z5u8Kmeyv8pmnB8EnBEsW8ql2lrAF0mb7FmLEkge738lGd1_6IHnbq14tJAWKyktnUsPhAaNReariYc7Mkcr3VuKta46KHRisasRv_zTJRb169ko2FTTXw5H2raZb-qCnhg8hUnDWzuPjDtHbb8a128svHktHTnVie0MtwVBVerl0000__y30000)

**4.Biểu đồ lớp**

![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niO9VUcb-fajfNhf2DPS24EWgbAJckIJcfVjb91OeM2a4bnHbvgL3fN8JIxmp4ajHXHKKye1AGpBoyz93Ck5QDJIvQhcWTdYaWcMXDYWeP6IcveLaP28fXOXN92Q7P9GcOuX3rOCDSKhCzydFX4kbGDN2lO5ihqjcSaPOQGJ4LBZjK5jW3jR0vbyT3Azg0bb9-VavgObv80iGmQQhQmVte9L2oR4DnnO2MIM75oOhb3tSFJkJ2oO9KeZg8Yk5ueUxrogaFDoz52X_PEB3tSqA5I2D9HaFTszCvd98pKi1nHG0003__mC0)

# IV. Ca sử dụng cho 'Maintain Employee Information'

**1. Xác định các lớp phân tích**

Dựa trên trường hợp sử dụng, các lớp phân tích chính là:

*PayrollAdministrator* - Đại diện cho tác nhân thực hiện các thao tác trên dữ liệu nhân viên.</p>
*Hệ thống* - Quản lý tương tác và luồng chung để duy trì thông tin nhân viên.
*Nhân viên* - Biểu thị thực thể nhân viên có thông tin chi tiết cần thêm, cập nhật hoặc xóa.
*EmployeeService* - Xử lý các hoạt động thực tế (thêm, cập nhật, xóa) trên dữ liệu nhân viên.
*Cơ sở dữ liệu* - Lưu trữ hồ sơ nhân viên và xử lý việc truy xuất và xóa.</p>
**2.Xác định trách nhiệm và thuộc tính**
> Quản trị viên tiền lương

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Khởi tạo các hành động thêm, cập nhật hoặc xóa hồ sơ nhân viên.
> Hệ thống

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Quản lý tương tác của người dùng, nhắc nhở nhập liệu và truyền thông tin đến EmployeeService.
> Người lao động

* Thuộc tính :
  
        -  employeeId: String
        -  name: String
        -  employeeType: String(theo giờ, theo lương, theo hoa hồng)
        -  address: String
        -  socialSecurityNumber: String
        -  taxDeductions: String
        -  otherDeductions: String
        -  phoneNumber: String
        -  hourlyRate: Double
        -  salary: Double
        -  commissionRate: Double
        -  hourLimit: Double
* Trách nhiệm : Thể hiện hồ sơ nhân viên cá nhân với tất cả các thuộc tính có liên quan.
> Dịch vụ nhân viên

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Thực hiện các thao tác thêm, cập nhật và xóa trên hồ sơ nhân viên.
> Cơ sở dữ liệu

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Lưu trữ và truy xuất thông tin nhân viên.

**3.Biểu đồ trình tự**
![Diagram](https://www.planttext.com/api/plantuml/png/v9L1IiD058RtESMxW1SGAa9Tk111BABBD2qcOAOXcPHsAIvSk574bGkDKeI2AEYgit0nfVUO4tW5_vaepgIDPE-cMSpt__F-zrxIJ_6ncN4_vNbyula17wIqbwlP8-kaIbmSH7BAEf4IfsndyRees37v6IM-bq0H1L7YCqxRIfntGYMkojDid3d7M_09mWCb9hkXV636KdFzEDdlfqE7RI-AVINk87dPmQtdkGPxNSzhjQWJocbCneDAarOBObhRq5VIEXt9QKw1cZtbn0tB33lKhASHaE2hu3lAvX5pQDksdGC0FKdgw6_lxq2GbANMq3yO5BqkO3IsjWu0hh6Q5GCQodiwbWMZM3xMMPUr7yeY0A5cpupcLw3BnWoLk8sMr7QBjj7zCmOSmwk256kvcKaRpWbcWWTlE9h0I5WfQJ2XQfMshRaugGjYjItDnpJ2Mazuuwa07XFYNrEsA9puFEmFz9tBqqdnukZcdZQufKpWzBd1CkBjUFOnIYLkeiRhsBPRlYhIwfrS6TviaJt3lvVE8VN67Cetl-6cZ3JwtpR4pcWtKZV3IMOTBiUPN-Bp458F9UQLyM7VIhDg7aTJC_jLufel3Nv-xOp6s-opdlwR-G800F__0m00)

**4.Biểu đồ lớp**
![Diagram](https://www.planttext.com/api/plantuml/png/b5HFQnf17BtlfvXZXVe5F8G4XLeYWTPDyBfPnHdgpWQT2GsXXvA312-Hda8fPIjIQWXDQQ3W7d8OyNlC9-XNo9lDLjr_qdZmy9ltU_j-x_Tc_eOFkmFXz8NqUfRRSmO3yaRg-OJRVHsEZfYQSPlfy2DlBE-M0U-ISuj4ltTKXr-PhUU1RrCrymwe-iOZ_8jI5bBLyzkJ0uf_iHtOKh-T1EA35Skgwt1e0pZU476cPXBKtoKatFEkpNWEEuN-2svQH_y9Qwd0ZSIkJqN1ZExMmTuNJhEkniEKYQSc6zKAQOe-uztuKEJKUZuSOyKzYp5cSQgOw39zD82FUxp9E6sf2PozPca4TZAVIfE26viY4GzR0FiKXkLzOd45KuSmDLAQHdWw_E76kNe5u1S0QhuyxdN-3HXdBbKMElpJ06_TTo3zKnRG1TbdLiStUOftvNyDrhZqI8VJp2Qoo-vu9w1O5qh9IOfIWBRNxHNq9SdGvASasRQHcUeoQEAYGFhFXl5LhWJ3AFaSlQ8lprfOwhHORYd14FSjnYhWj6OMlxZ2TJ6tDK_lzYUaNDv9tEOA4V69C3awDSkpDW6c8NTX5PEoMz965J2N-iGr357SH9J_QyoSsseuiuP22hxvourUWo4drRU7jOoKX82dPoDg6vdWt9in6BTsExnjtjH70000__y30000)

## V.Ca sử dụng cho 'Maintain Purchase Order'

**1. Xác định các lớp phân tích**

Dựa trên trường hợp sử dụng, các lớp phân tích chính là:

*CommissionedEmployee* - Đại diện cho tác nhân thực hiện các thao tác trên đơn đặt hàng mua.
*Hệ thống* - Quản lý tương tác và luồng xử lý để duy trì đơn đặt hàng mua.
*PurchaseOrder* - Biểu thị thực thể đơn đặt hàng mua cần được tạo, cập nhật hoặc xóa.
*PurchaseOrderService* - Xử lý các hoạt động thực tế (tạo, cập nhật, xóa) trên dữ liệu đơn đặt hàng.
*Cơ sở dữ liệu* - Lưu trữ hồ sơ đơn đặt hàng và xử lý việc truy xuất và xóa.

**2.Xác định trách nhiệm và thuộc tính**
> Nhân viên được ủy quyền

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Khởi tạo việc tạo, cập nhật hoặc xóa đơn đặt hàng mua.
> Hệ thống

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Quản lý tương tác của người dùng, nhắc nhở nhập liệu và truyền thông tin đến PurchaseOrderService.
> Đơn đặt hàng

* Thuộc tính :
  
        -  purchaseOrderId: String
        -  customerContact: String
        -  billingAddress: String
        -  products: List<String>
        -  date: Date
        -  status: String(mở hoặc đóng)
        -  commissionedEmployeeId: String
  
* Trách nhiệm : Thể hiện hồ sơ đơn đặt hàng mua riêng lẻ với tất cả các thuộc tính có liên quan.
> Dịch vụ mua hàng

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Thực hiện các thao tác tạo, cập nhật và xóa trên đơn đặt hàng mua.
> Cơ sở dữ liệu

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Lưu trữ và truy xuất thông tin đơn đặt hàng.
**3. Biểu đồ trình tự**
  ![Diagram](https://www.planttext.com/api/plantuml/png/t9InQi9G58RtFCLvWRv08QMG3WxIHH4xncimWNeJaXlHiNJeu5AHJXrgAb8Gf8LsCaE7Axx7VOA-GizD0hqt8UhSASFvpd_k-Vz3VjBlouZP8Ok7juPDc1_2jSjVQSVZQzhmxOP8vtG0TWJ4CGBaFE85DcM0XOUsAz9PNeqcaLQ-4kcKk1sHhdQF-uGs-2Bd0h_bX2CDjVP9IwGlsF7Uz50rbbo_PnYc2MsnJNp8923NC4s3E71s8IV2ETpmTGn4RDzYO3axawmhMKCYI2AlWox_GYNcKOrMPQqO0QHNGHrTQEVxO4UxChqe8TJl8T3SV-3e4BVKAAnLPKPy0GEEp90lQpJpTtPvGe2wOhkXnVuZaJvxbJxLYGQQV8yuXZSjWp2KxPdr5ee6U0puOIScGB8MMhGS3wByIbKs6npKBVBdLnXFO1nZKkoW-GXCj4MPw_XIlH90ABPBwU9TNVBb33G_JxWjFFQDZLMHFdcdNfUbEek3vX3jawFNfkwxcw6JQa07Rqa3vJLq-QTzuXMCC_I_fgykepecjzPMK8gLTtVB5fKUdDMFn5mDBNk2SUdGlloP_m800F__0m00)

  **4.Biểu đồ lớp**
  ![Diagram](https://www.planttext.com/api/plantuml/png/b5JDQi904BxdAVPOeRw0517qOAb8gQbu3L6oItKYPbCgfQSUf7Yfz5HwgAcKKa5gQK_cqCEAxx5Fq5Ve98PeJ1IRmyBEVFFDDp-RN_SdPt6jm-rMKz6RccMHCXKlK6LY34LJAqht0GnohH3_kw3IVMQgd3ccVypl5muKnH2CWrGSafUpIRjCyUIxWJNnfKKGDqeW1lFtL0GEraHqnTX6wZTRfU8R39L10Zjbqhq5BxI_9wmc7DqN2w6NRwbHtrdOrTPgLjQWc3HfYT6QDKCglCF029nDVmhOWXEAucWYPZv0xLeUAxXJgGPKDOK3co1BpaPmYeBVM-WgCOiVBVtP002667RHLT1u8p3n3bQFVSFKR9CFLIUjIOWAAowWE9rMfViQgptUthQ93AjxAffrMzlRvd4zH1wIJPBaeKI2rYQKNpWLN4kK_L72rUZPeTZcOch_GollsDsQBMUlMwMc8WJxoangUpgTZJoK3E6BAN8OXEFQa4lfFZ5b7U0594ucWvlYJaWThNZJgKbqZu6QE2dkhzeZIaqCzJZZtKCfcFDJznzQ3qZ-xBmGan8Hi7oHVbWVJ-_f4iv0oJMWxlsa_W000F__0m00)

## VI. Ca sử dụng cho 'Run Payroll'

**1. Xác định các lớp phân tích**
Dựa trên mô tả, các lớp chính liên quan đến trường hợp sử dụng này là:

*PayrollSystem* - Quản lý toàn bộ quy trình tính lương và kích hoạt chạy bảng lương.
*Nhân viên* - Đại diện cho mỗi nhân viên được trả lương.
*TimeCard* - Lưu trữ số giờ làm việc của nhân viên theo giờ.
*PurchaseOrder* - Biểu thị lệnh mua hàng cho nhân viên hưởng lương, đóng góp vào tiền lương của họ.
*BankTransaction* - Biểu thị dữ liệu giao dịch được gửi đến Hệ thống Ngân hàng để thanh toán gửi tiền trực tiếp.
*BankSystem* - Đại diện cho hệ thống bên ngoài để xử lý các giao dịch ngân hàng.
*PayrollService* - Xử lý tính toán bảng lương và thanh toán.
*Cơ sở dữ liệu* - Lưu trữ dữ liệu nhân viên và quản lý các hoạt động truy xuất và xóa.

**2. Xác định trách nhiệm và thuộc tính**
> Hệ thống tính lương

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Kích hoạt quá trình tính lương, xử lý tiền lương cho nhân viên, quản lý các luồng thay thế.
> Người lao động

* Thuộc tính :
  
        -  employeeId: String
        -  name: String
        -  salaryType: String(theo giờ, theo lương, theo hoa hồng)
        -  salary: Decimal
        -  deductions: List<String>
        -  payMethod: String(thư, nhận tại chỗ, gửi tiền trực tiếp)
        -  status: String(đang hoạt động, được đánh dấu để xóa)
* Trách nhiệm : Đại diện cho nhân viên và lưu trữ thông tin liên quan đến bảng lương.
> Thẻ thời gian

* Thuộc tính :
  
        -  employeeId: String
        -  hoursWorked: Decimal
        -  date: Date
* Trách nhiệm : Theo dõi số giờ làm việc của nhân viên theo giờ.
> Đơn đặt hàng

* Thuộc tính :
  
        - employeeId: String
        - orderAmount: Decimal
        - date: Date
* Trách nhiệm : Đại diện cho các đơn đặt hàng đóng góp vào thu nhập của nhân viên được trả lương.
> Giao dịch ngân hàng

* Thuộc tính :
  
        - transactionId: String
        - amount: Decimal
        - accountNumber: String
        - employeeId: String
* Trách nhiệm : Thể hiện dữ liệu cần thiết cho giao dịch gửi tiền trực tiếp.
> Hệ thống Ngân hàng

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Xử lý các giao dịch gửi tiền trực tiếp.
> Dịch vụ tính lương


* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Tính lương, khấu trừ, tạo phiếu lương hoặc giao dịch ngân hàng.
> Cơ sở dữ liệu

* Thuộc tính : Không có thuộc tính cụ thể nào cho trường hợp sử dụng này.
* Trách nhiệm : Lưu trữ và truy xuất hồ sơ nhân viên, thẻ chấm công và lệnh mua hàng.
  **3. Biểu đồ tuần tự**
  ![Diagram](https://www.planttext.com/api/plantuml/png/Z5N1QXfH5DtFLzobWVO714keWQGGt2Z1xSmeli7npSHv8t5Pid3HHHkwAAMKneeKqaeIMYZCexXunVzuNz1VwBtlZMOcAgsWmhppphdtt7FrZrmU9i8TYdGGEguleY6SQ3bfCIslU0_S199nuiG82FmWThae7hS2BL_oqzNTQcgnSHbwfEKhdvrfETz6Dhl3KGbSNqsRMdx2ExUdY9wa1Eju9Ko3gS_yB50td0wxWxXq-bndCzwhCvtD1tNrmme9luJv_GOhE57NUHLHwV0uS2DRSwE7GXkO9_Ovy0YNE4wj1bJ1T0osPrWtNQivQ2KyVOOkGPMAlSLohdJs9ONpL4r13DKtpa3OQs5-hT9N2vy1Yv1JWD3odYx9zxntuCI6hkCXNMkOZk4YnTO5S789HiOcdqN0U-fwZFHepuQMaSKS-R9fu233kgmZ5qj8r1Gb2pIcBPpZXm06MhuBIXBOc2q4vu4CRIqN4AfVZninbHGeznJVmVb3Q0DGLAcCr88EvzKrunFmiKxeapKpZjzuFwKsvTUzrXJPRLp0vWLiO2fSPqiaKGkQ1Ej6q4FmnuFS8k4RFZ9oXCtzY-v_gZ2111kXaZgBNC2GlQL1vmEAzgiNQ79Lis5qmR3jcuBZXW9QZAOk8eKKvwcBZQ_kJE9--WZMsO8RM-zzcccsZ1t0b-LVvwQ5GOeWPe7f85UpE5CDHRyAB_WMf1ictQq2V9QEjRpaw-6M1Jsn4ToriGLLZqIFCP01pj6Do364cgrRyjrxR6wJARktd58sCpdCeVJo7jQwJP7CFIj86gXfTH-jYTzEzlY1dIxYSj7IbXgYgUPDzLc0yqDIV6eoQ9Hvnw4thN7JJIsez7j033jNcwne51vvg8XQE2c6whHnz7Dq2HVgkrjmtcI-ZSzAVDYVV1rGh2TOf371r7M87_G7z1S00F__0m00)

  **4. Biểu đồ lớp**
  ![Diagram](https://www.planttext.com/api/plantuml/png/b5NDQjj04BxhAUOOG_m2ffXG1nA8yIN6zAfkZ5PKMXbhPMnA3wM777ffwBdKgicXBIOfxSbBo663tqDFq5Veh2nh9Qzafxx4cPzlllbcTlnNF9w4t1xpoFSiujbX2EU9kExJHDmmf-ycuZthhk_NCNFWhGNfXz1a5SzAlgE6zSxAydjKVcC3L_vWMKOJVBaeM5jmoSSkSp8dhx1v0PPmjuLtdRdvT4XSt_OoEv4nkQ2OkM0NIF4sweyJyHF3kcx8NsmWsbdiY6v0LAFVIP_QZFO36PlanaX4XSdOBVi0YIyPhH3WfMBWT1G5loF_vCeTq254oSzGr2zTEVS7-EMQ62qoHyvdochpeIxuz0afdClv_rJQZA-G-RnIPwuTd2RY8w4z1-6DejfVNzGebRhatCs6jvjPqqlEgR2m1Yc0QIAMNVcWYHszvWXIrKXXXXlN816trM-WD7isGK1DyHYucfon1iSm2j2kDM_iA96JrVjeObVfM23UMSUNYVYA_E-wQeSYJNaSpLv5o8Phk0uDUchE-59MYtoLjqz6nxKp30_JPnfR1nnL3wbH8byDOkYq1okbPIJKiDD27qBKaLkegVnj7-vEoLvxBflDTkqQjTGObt253loFq20zNi2e8kx31Et0DqFEhjt-EkRKM-cyOPeE72Po3YHPBKTO0lzmGA3F4AvZguwXGYsrd6vypcPVMkMDG02yf04uw5Hzgmj1Q3HBn0S6RxA7ZzTM_2AgyzNZoAh4KGMg7tmB7DJKXQSRn4nV4dZomJAbCLh3fgAqzbrDj7dHdv5Kkgs5w9CXkrA_jly0003__mC0)
