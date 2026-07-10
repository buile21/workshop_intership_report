---
title: "Tuần 5: Bảo mật & Quản lý Định danh (AWS KMS, Amazon Cognito, IAM Policies)"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---


### Mục tiêu Tuần 5:
* Nắm vững cơ chế mã hóa dữ liệu ở trạng thái nghỉ (Data at rest) và đang truyền tải (Data in transit) bằng dịch vụ AWS KMS.
* Tìm hiểu giải pháp quản lý người dùng, xác thực (Authentication) và phân quyền (Authorization) toàn diện với Amazon Cognito.
* Nâng cao kỹ năng viết IAM Policies (đặc biệt là Policy Conditions và PassRole) để cấp quyền thực thi (Execution Role) an toàn cho các dịch vụ Serverless.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tìm hiểu dịch vụ quản lý khóa AWS KMS:<br>&emsp; + Phân biệt Customer Managed Keys (CMK) và AWS Managed Keys.<br>&emsp; + Các khái niệm: Symmetric/Asymmetric keys, Key Rotation.<br>&emsp; + Cơ chế Envelope Encryption. | 18/05/2026 | 18/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - Tìm hiểu dịch vụ quản lý người dùng Amazon Cognito:<br>&emsp; + Phân biệt Cognito User Pools (Xác thực) và Identity Pools (Phân quyền).<br>&emsp; + Hiểu cơ chế hoạt động của chuẩn OAuth 2.0 và JWT (JSON Web Tokens). | 19/05/2026 | 19/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Nghiên cứu chuyên sâu về AWS IAM Policies:<br>&emsp; + Sử dụng Policy Conditions để giới hạn quyền truy cập theo IP hoặc thời gian.<br>&emsp; + Khái niệm **iam:PassRole** khi cấu hình cho các dịch vụ tự động hóa. | 20/05/2026 | 20/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Thực hành KMS & S3:**<br>&emsp; + Tạo một khóa mã hóa tự quản lý (Customer Managed Key) với tên **fcaj-idp-kms-key**.<br>&emsp; + Cấu hình S3 Bucket (**fcaj-idp-docs...**) tự động mã hóa mọi file upload lên bằng khóa KMS này. | 21/05/2026 | 21/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thực hành Cognito:**<br>&emsp; + Khởi tạo **fcaj-idp-user-pool** để quản lý tài khoản người dùng đăng nhập hệ thống.<br>&emsp; + Cấu hình App Client và kích hoạt Cognito Hosted UI.<br>&emsp; + Thử nghiệm luồng Đăng ký (Sign-up) và Đăng nhập (Sign-in) trên giao diện web có sẵn. | 22/05/2026 | 22/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Hiểu rõ tầm quan trọng của việc mã hóa dữ liệu nhạy cảm và tự tay cấu hình thành công AWS KMS để bảo vệ các tài liệu lưu trữ trên Amazon S3.
* Xây dựng được nền tảng xác thực người dùng vững chắc bằng Amazon Cognito User Pool, sẵn sàng cho việc bảo vệ các endpoint API (API Gateway) của đồ án sau này.
* Có khả năng kiểm tra trực quan luồng đăng nhập thông qua Cognito Hosted UI mà không cần phải viết code Frontend phức tạp.
* Rèn luyện tư duy bảo mật khắt khe (Zero Trust) thông qua việc áp dụng các điều kiện Policy nâng cao trong AWS IAM.

---
![AWS KMS Key Creation](../../images/1-Worklog/1.5-Week5/week5-1.png)
<p align="center"><i>Hình 1: Khóa mã hóa bảo mật Customer Managed Key (CMK) <b>fcaj-idp-kms-key</b> được tạo thành công trên giao diện AWS KMS.</i></p>

![S3 Default Encryption](../../images/1-Worklog/1.5-Week5/week5-2.png)
<p align="center"><i>Hình 2: Cấu hình Default Encryption của S3 Bucket được thiết lập thành công, bắt buộc sử dụng khóa KMS vừa tạo để mã hóa tài liệu.</i></p>

![Cognito Hosted UI Login](../../images/1-Worklog/1.5-Week5/week5-3.png)
<p align="center"><i>Hình 3: Giao diện đăng nhập web (Hosted UI) do Amazon Cognito tự động sinh ra phục vụ cho việc xác thực người dùng của User Pool.</i></p>