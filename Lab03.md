
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


***Subsystem: ProjectManagementDatabase***
* Mô tả
     - Subsystem này cho phép PayrollController truy vấn thông tin về dự án từ cơ sở dữ liệu quản lý dự án.
     - PayrollController sử dụng giao diện IProjectManagementDB để gửi truy vấn và nhận thông tin.

 * *Biểu đồ ngữ cảnh*

![Diagram](https://www.planttext.com/api/plantuml/png/f591JiCm4Bpx5QjUW4FKUnH55PH33w2Al63ZRXDJnmds1X41B-F0a_W2TfAMLWrSE7fdTcPdrryVdml7QBcjj70xPHgqM463SeS5PTnf0akIqHIQXBY0czgmhJL8ZSx5iCREl_HOrMH53vpN8Kday4XJU1K0ypbiYMK9ZQqVlGDia56y1u-LOR9Rb1J3QZsWTsZyF1KPNbuBjSSduLuTuAabsutmqajVoX9jGVTjbPED8MEhJ77b4_nG1lUipLtdcAe0lNG7nf67v-ReQ9_rDzndTWUn9eYDsVyntQrXnTsm_bF_mF6Er1DwexxXWJIogeqhLUF4-LsYA9rUOmopCAKYTt8YU5Ou4vCToLiK_R6joPvWVnnIBCXimcVy1W00__y30000)

  **Giải thích các thành phần**

* *PayrollController:* Thành phần xử lý yêu cầu truy vấn thông tin dự án.
* *IProjectManagementDB:* Giao diện trừu tượng để tương tác với cơ sở dữ liệu quản lý dự án.
* *ProjectManagementDatabase:* Proxy đại diện cho cơ sở dữ liệu thực sự.
* *ProjectData:* Thực thể đại diện cho dữ liệu dự án được truy xuất.


# 2. Analysis Class to Design Element Map



| **Analysis Class**         | **Design Element**                                   | **Mô tả**                                                                                                                                       |
|-----------------------------|-----------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Employee**               | Employee Entity Class                               | Lớp lưu thông tin của nhân viên như ID, tên, địa chỉ, phương thức thanh toán.                                                                   |
| **Timecard**               | Timecard Entity Class                               | Lớp đại diện cho bảng chấm công của nhân viên, bao gồm ngày làm việc, số giờ làm, số charge.                                                   |
| **PaymentMethod**          | PaymentMethod Interface                             | Giao diện trừu tượng cho các phương thức thanh toán như chuyển khoản (Direct Deposit), nhận tiền mặt, nhận qua phiếu lương giấy.                |
| **Paycheck**               | Paycheck Entity Class                               | Lớp đại diện cho phiếu thanh toán, bao gồm số tiền lương, thuế, và chi tiết thanh toán.                                                         |
| **PayrollAdministrator**   | PayrollAdministrator Control Class                  | Lớp điều khiển xử lý các thao tác quản trị như thêm, xóa, sửa thông tin nhân viên, và quản lý các phương thức thanh toán.                       |
| **BankService**            | BankSystem Subsystem Proxy                          | Thành phần xử lý kết nối đến hệ thống ngân hàng để thực hiện các giao dịch thanh toán.                                                         |
| **PrintService**           | PrintService Subsystem Proxy                        | Thành phần kết nối đến hệ thống in ấn để in phiếu lương cho nhân viên.                                                                          |
| **ProjectManagementQuery** | ProjectManagementDatabase Subsystem Proxy           | Thành phần truy vấn cơ sở dữ liệu quản lý dự án, lấy dữ liệu số charge và thông tin dự án.                                                      |
| **PayrollController**      | PayrollController Class                             | Lớp điều khiển chính của hệ thống, chịu trách nhiệm điều phối hoạt động từ việc nhận dữ liệu đầu vào đến xử lý thanh toán và xuất báo cáo.      |
| **CommissionCalculator**   | CommissionCalculator Strategy Implementation Class  | Thành phần tính toán hoa hồng cho nhân viên hưởng lương theo doanh số.                                                                          |
| **OvertimeCalculator**     | OvertimeCalculator Strategy Implementation Class    | Thành phần tính toán lương làm thêm giờ cho nhân viên làm việc vượt giờ.                                                                        |
| **EmployeeReport**         | EmployeeReport Boundary Class                       | Lớp chịu trách nhiệm tạo báo cáo cho nhân viên, bao gồm số giờ làm việc, số charge, tổng lương nhận, và thời gian nghỉ còn lại.                 |

---

# 3.	Design element to owning package map

  | **Design Element**                | **Owning Package**        | **Mô tả**                                                                                  |
|-----------------------------------|---------------------------|--------------------------------------------------------------------------------------------|
| **Employee**                      | `entities`                | Lớp thực thể lưu trữ thông tin của nhân viên như ID, tên, địa chỉ, và phương thức thanh toán.|
| **Timecard**                      | `entities`                | Lớp thực thể lưu trữ thông tin về bảng chấm công của nhân viên.                            |
| **Paycheck**                      | `entities`                | Lớp thực thể đại diện cho phiếu thanh toán.                                                |
| **PaymentMethod**                 | `interfaces`              | Giao diện trừu tượng cho các phương thức thanh toán.                                       |
| **DirectDepositPayment**          | `implementations`         | Hiện thực phương thức thanh toán qua chuyển khoản.                                         |
| **PaycheckPrinter**               | `implementations`         | Hiện thực phương thức in phiếu lương.                                                     |
| **BankService**                   | `subsystems.bank`         | Proxy đại diện cho hệ thống ngân hàng để thực hiện các giao dịch thanh toán.              |
| **PrintService**                  | `subsystems.print`        | Proxy đại diện cho hệ thống in ấn để in phiếu lương giấy.                                  |
| **ProjectManagementQuery**        | `subsystems.database`     | Proxy đại diện cho hệ thống cơ sở dữ liệu quản lý dự án để truy vấn thông tin.             |
| **PayrollController**             | `controllers`             | Lớp điều khiển chính của hệ thống, điều phối hoạt động xử lý thanh toán và báo cáo.        |
| **PayrollAdministrator**          | `controllers`             | Lớp điều khiển quản lý các tác vụ của người quản trị nhân sự.                              |
| **CommissionCalculator**          | `strategies.calculators`  | Hiện thực chiến lược tính toán hoa hồng.                                                   |
| **OvertimeCalculator**            | `strategies.calculators`  | Hiện thực chiến lược tính toán lương làm thêm giờ.                                          |
| **EmployeeReport**                | `boundaries.reports`      | Lớp tạo báo cáo cho nhân viên.                                                             |

---

# 4.	Architectural layers and their dependencies


![diagram](https://www.planttext.com/api/plantuml/png/X5NBZXCn4BpFLrZXm2a2SKIhQ3TPX90M4H4u8CIXrzERc7ZimUr9626-Z0EVn2_GdlSpEKNZhkxggfHd_ltvUqiUdCyI7T5HcHGS94BQ9BK6ZT_vNADmA3sOlSOE90LvX3tE0-W0iJqhinVUPTs2iJ5k8Ov3wTNBA7ekjWw9oS0hQyG3vEYYQhnOZ6iByUn1xGz-hJCKlo8XlducTEATyUYUGE8tSNFJ25YjHFGxSDobgLPoac9KgXdUEaHJKcmXTrRhZJK-_A8BB3g0cQ6YM6Ua31A97RgJaaX3eXb0JVS5jRRd7by5x9Dn-KsIQfiZJjQBPUvj0ceajNlQgeIy9AsdXd7idVBvQbKj8myeZyFpJof12IuUdcziaYWYzdC3McOQl2tyedBR4lJXXCxpW3b8gG8yY3ifWsb3ASDIhMUhpB7K4o2FG1CkXUeQp76NayUa8CuUgNWGgRC_Q-5EyHreksT0zZld_pqOtYjX7shQwOv2rqVKHTxee5AAHW5UyiqnozLax5wBXGf8a9x4MVd38fg23KSqAhXVWjPqfMsKiBOl6irSTZiAQ5AuqI7fOzj4CNQFXkNuUNIRi-kJfxDNBbyyygsJ3MPkobGu-pDiXGXsZBowvCSqk6T80vxPRfHhxY7U4Uc5G-yKddZ1c44p_t6OqKr_Q4SJ4x_Kyn1W4jvUQEtVYgRvoJeEEPVunNwnU_QwyAWV6VB-56vBG5Kgeh7aiSLGl0iAZwVHFO-ledkXQz7HBOiDNyl_0000__y30000)

# Giải Thích

## 1. Presentation Layer:
### - **User Interface**:
- Là nơi người dùng tương tác với hệ thống.
- Người dùng sẽ nhập thông tin và yêu cầu hệ thống xử lý qua `PayrollController`.

## 2. Application Layer:
### - **PayrollController**:
- Nhận yêu cầu từ giao diện người dùng và gọi các dịch vụ trong **Business Services Layer** để xử lý.

## 3. Business Services Layer:
### - **PayrollService** và **EmployeeService**:
- **PayrollService** và **EmployeeService** chịu trách nhiệm quản lý các yêu cầu liên quan đến lương, nhân viên và các dịch vụ nghiệp vụ như tính toán hoa hồng, làm thêm giờ.
- **PayrollService** sẽ làm việc với các đối tượng như `Employee`, `Paycheck`, và `Timecard`.

## 4. Domain Layer:
### - Các đối tượng trong Domain:
- **Employee**: Đại diện cho thông tin của nhân viên trong hệ thống.
- **Paycheck**: Đại diện cho phiếu lương của nhân viên.
- **Timecard**: Đại diện cho bảng chấm công của nhân viên.
  
### - **CommissionCalculator** và **OvertimeCalculator**:
- **CommissionCalculator** và **OvertimeCalculator** là các dịch vụ xử lý các tính toán liên quan đến hoa hồng và giờ làm thêm của nhân viên.

## 5. Data Access Layer:
### - **DatabaseService**:
- Chịu trách nhiệm kết nối và thao tác với cơ sở dữ liệu, lưu trữ và truy xuất thông tin về nhân viên, bảng chấm công và phiếu lương.

### - Các hệ thống con (subsystems):
- **BankSystem**: Chịu trách nhiệm xử lý các giao dịch thanh toán cho nhân viên (ví dụ: chuyển khoản lương).
- **PrintService**: Chịu trách nhiệm in ấn các phiếu lương hoặc báo cáo liên quan đến lương.
- **ProjectManagementDatabase**: Chịu trách nhiệm quản lý và truy vấn dữ liệu về các dự án và mã số công việc từ hệ thống quản lý dự án.

