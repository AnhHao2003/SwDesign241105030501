
### Lab 3. Identify design elements ###
Xác định các phần tử thiết kế của hệ thống “Payroll System”

# 1. Subsystem: 

***Subsystem:BankSystem***
* Mô tả
     - Hệ thống **BankSystem** chịu trách nhiệm xử lý các khoản thanh toán qua ngân hàng.
     - **PayrollController** sẽ sử dụng giao diện **IBankSystem** để tương tác với hệ thống, thực hiện gửi thông tin thanh toán (Paycheck) đến thông tin tài khoản ngân hàng **(BankInformation)** của nhân viên

* *Biểu đồ ngữ cảnh*
  ![digram](https://www.planttext.com/api/plantuml/png/h591JiCm4Bpx5QjUsaf4lKTHL84uv5QH5opEjhNYs97NgOY0bt7WINo1s4bf85SkbhqpdfbT--lZSyyUdUyQBRXMfaM73RGeQpnHwNjDu4XwD2TDGgpXmHhlh0QfaJc50_R3IKzLJKv4O5c7B9FZ8S_XLG3iTk0wCpX5ucOhteDyOJov8qfAeRX7KvSzUsg4kfRdrIW3K55hMVaD3fxoJBAEgUBk3eQBDjn88Qo5ELhNe5VMR5EuM5MDhcNtpAFamTcNVYHFrcC_CzSiunzw6-XJG_-IvD5uvVjnkiItOKQHmPeY7Xq7_YtRJ6_1MiCJwGZnMRKibc-J9FclmQQmgbHuzcjB3340mqNXIiofsLkIpCSrnuBiDVi2-9DQY3sPAlp2Rm000F__0m00)


 
**Giải thích các thành phần**

* *PayrollController*: Thành phần điều khiển xử lý logic chính, chịu trách nhiệm thực hiện thanh toán.</p>
* *IBankSystem:* Giao diện trừu tượng để tương tác với hệ thống ngân hàng.</p>
* *BankSystem:* Proxy đại diện cho hệ thống con thực sự, xử lý các yêu cầu gửi thanh toán.</p>
* *Paycheck:* Thực thể đại diện cho phiếu thanh toán.</p>
* *BankInformation:* Thực thể lưu trữ thông tin tài khoản ngân hàng.</p>


***Subsystem: PrintService***
* Mô tả
     - Hệ thống **PrintService** chịu trách nhiệm tạo và in phiếu lương giấy cho nhân viên.
     - **PayrollController** sử dụng giao diện IPrintService để tạo phiếu lương từ dữ liệu và gửi yêu cầu in.

 * *Biểu đồ ngữ cảnh*
   ![Diagram](https://www.planttext.com/api/plantuml/png/Z9B1JiCm38RlUGfh5xP3jNjLLPCGXzqg-WGXCrlKD8bYTw82dem3ZyGhaAGThEp2BRP_VxzjvUlZSqSi0m-z4THfwsMGFNYfEdd4baU3452nj4U3Gjp1lRCSd05b9549ZHnZPEQimI1ouJOFLQMceAxXLG1ijn066vsoSBqHxmc_jupXMIeiOTy4RRd5SDOAXRuKblcC0l0fjPRHLPrGTNck_DgKS7RwCC7RuOb6OkoX2UvbZAfhXtdmQtXLqK-BJotpxFyrVB2iUPnkzNkOh8jipDMCpEf7D9AritJIdiJj1OkY_hDy2Ij2Uw1qnKmbOBSIIr7rLXJBJPVrXBrC9SGkyj9V-0O00F__0m00)

   **Giải thích các thành phần**

* *PayrollController:* Thành phần xử lý việc gửi phiếu lương để in.
* *IPrintService:* Giao diện trừu tượng cho các dịch vụ in ấn.
* *PrintService:* Proxy đại diện cho hệ thống thực hiện in phiếu lương.
* *Paycheck:* Phiếu lương cần được in.
