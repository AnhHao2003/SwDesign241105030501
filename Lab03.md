
### Lab 3. Identify design elements ###
Xác định các phần tử thiết kế của hệ thống “Payroll System”

# 1. Subsystem: BankSystem
* Mô tả
     - Hệ thống **BankSystem** chịu trách nhiệm xử lý các khoản thanh toán qua ngân hàng.
     - **PayrollController** sẽ sử dụng giao diện **IBankSystem** để tương tác với hệ thống, thực hiện gửi thông tin thanh toán (Paycheck) đến thông tin tài khoản ngân hàng **(BankInformation)** của nhân viên

* *Biểu đồ ngữ cảnh*
  ![digram](https://www.planttext.com/api/plantuml/png/h591JiCm4Bpx5QjUsaf4lKTHL84uv5QH5opEjhNYs97NgOY0bt7WINo1s4bf85SkbhqpdfbT--lZSyyUdUyQBRXMfaM73RGeQpnHwNjDu4XwD2TDGgpXmHhlh0QfaJc50_R3IKzLJKv4O5c7B9FZ8S_XLG3iTk0wCpX5ucOhteDyOJov8qfAeRX7KvSzUsg4kfRdrIW3K55hMVaD3fxoJBAEgUBk3eQBDjn88Qo5ELhNe5VMR5EuM5MDhcNtpAFamTcNVYHFrcC_CzSiunzw6-XJG_-IvD5uvVjnkiItOKQHmPeY7Xq7_YtRJ6_1MiCJwGZnMRKibc-J9FclmQQmgbHuzcjB3340mqNXIiofsLkIpCSrnuBiDVi2-9DQY3sPAlp2Rm000F__0m00)

 
*Giải thích các thành phần* 

*PayrollController*: Thành phần điều khiển xử lý logic chính, chịu trách nhiệm thực hiện thanh toán.</p>
*IBankSystem:* Giao diện trừu tượng để tương tác với hệ thống ngân hàng.</p>
*BankSystem:* Proxy đại diện cho hệ thống con thực sự, xử lý các yêu cầu gửi thanh toán.</p>
*Paycheck:* Thực thể đại diện cho phiếu thanh toán.</p>
*BankInformation:* Thực thể lưu trữ thông tin tài khoản ngân hàng.</p>
