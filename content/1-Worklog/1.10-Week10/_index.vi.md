---
title: "Tuần 10: Khởi tạo Đồ án - Thiết kế Kiến trúc IDP Serverless & Tiếp nhận Tài liệu đầu vào"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu Tuần 10:
* Khởi tạo lớp lưu trữ (Storage Layer) an toàn trên đám mây để tiếp nhận tài liệu đầu vào và phục vụ cho Frontend.
* Ứng dụng kiến trúc hướng sự kiện, thiết lập luồng giao tiếp tự động giữa dịch vụ lưu trữ (Amazon S3) và dịch vụ hàng đợi (Amazon SQS).
* Chuẩn bị sẵn sàng hệ thống phân quyền bảo mật (IAM Role) chặt chẽ cho các tác vụ phân tích AI cốt lõi trong các tuần tiếp theo.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - **Thiết lập S3 Bucket tiếp nhận tài liệu:**<br>&emsp; + Tạo bucket `idp-ingest-bucket-1` tại us-east-1.<br>&emsp; + Vô hiệu hóa ACLs và chặn hoàn toàn quyền truy cập công khai (Block all public access) để đảm bảo bảo mật tài liệu.<br>&emsp; + Cấu hình CORS cho phép các method PUT, POST, GET để Frontend có thể giao tiếp trực tiếp. | 22/06/2026 | 22/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - **Thiết lập S3 Bucket phục vụ Frontend:**<br>&emsp; + Tạo bucket `idp-frontend-bucket-01` tại us-east-1.<br>&emsp; + Bỏ tích "Block all public access" nhằm cho phép phục vụ nội dung tĩnh cho ứng dụng web một cách công khai. | 23/06/2026 | 23/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - **Khởi tạo Amazon SQS điều phối tác vụ:**<br>&emsp; + Tạo hàng đợi Standard mang tên `idp-document-queue`.<br>&emsp; + Thiết lập Visibility timeout là 2 phút để chừa đủ thời gian cho AI xử lý tài liệu lớn.<br>&emsp; + Định nghĩa Access policy (Advanced) cấp quyền `sqs:SendMessage` chỉ định đích danh từ nguồn là bucket ingest. | 24/06/2026 | 24/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Cấu hình Sự kiện (Event Notification):**<br>&emsp; + Thiết lập Event notification mang tên `SendToSQS` trên bucket Ingest.<br>&emsp; + Bắt tất cả sự kiện tạo mới object (`All object create events`) và định tuyến thẳng đến đích là SQS Queue vừa tạo. | 25/06/2026 | 25/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thiết lập phân quyền bảo mật IAM Role:**<br>&emsp; + Tạo role `idp-lambda-ai-role` dành riêng cho AWS Lambda với Trusted entity là Lambda.<br>&emsp; + Cấp phát chính xác 5 quyền cần thiết: `AWSLambdaSQSQueueExecutionRole`, `AmazonS3ReadOnlyAccess`, `AmazonDynamoDBFullAccess`, `AmazonTextractFullAccess`, và `AmazonBedrockFullAccess`. | 26/06/2026 | 26/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Xây dựng thành công vùng hạ cánh (Landing zone) an toàn cho tài liệu hóa đơn thông qua dịch vụ lưu trữ Amazon S3.
* Hoàn thiện luồng thông điệp tự động: Mỗi khi có một hóa đơn tải lên S3, một sự kiện sẽ lập tức được gửi vào hàng đợi SQS để điều tiết xử lý, ngăn chặn hoàn toàn việc quá tải hệ thống.
* Đảm bảo nguyên tắc bảo mật đặc quyền tối thiểu (Least Privilege) với IAM Role, hạ tầng đã hoàn toàn sẵn sàng để tích hợp với động cơ AI ở tuần kế tiếp.

---
![Block Public Access S3](/images/1-Worklog/1.10-Week10/week10-1.png)
<p align="center"><i>Hình 1: Cấu hình chặn toàn bộ truy cập công khai (Block all public access) trên S3 Bucket để đảm bảo an toàn tuyệt đối cho tài liệu hóa đơn đầu vào.</i></p>

![Block Public Access S3](/images/1-Worklog/1.10-Week10/week10-2.png)
<p align="center"><i>Hình 2: Cấu hình chặn toàn bộ truy cập công khai (Block all public access) trên S3 Bucket để đảm bảo an toàn tuyệt đối cho tài liệu hóa đơn đầu vào.</i></p>

![SQS Access Policy](/images/1-Worklog/1.10-Week10/week10-3.png)
<p align="center"><i>Hình 3: Phân quyền Access policy cho phép Amazon SQS tiếp nhận thông điệp kích hoạt (trigger) trực tiếp từ Amazon S3.</i></p>

![SQS Access Policy](/images/1-Worklog/1.10-Week10/week10-4.png)
<p align="center"><i>Hình 4: Phân quyền Access policy cho phép Amazon SQS tiếp nhận thông điệp kích hoạt (trigger) trực tiếp từ Amazon S3.</i></p>

![S3 Event Notification](/images/1-Worklog/1.10-Week10/week10-5.png)
<p align="center"><i>Hình 5: Thiết lập Event Notification (SendToSQS) để tự động bắt sự kiện tải file và định tuyến tới hàng đợi SQS.</i></p>

![S3 Event Notification](/images/1-Worklog/1.10-Week10/week10-6.png)
<p align="center"><i>Hình 6: Thiết lập Event Notification (SendToSQS) để tự động bắt sự kiện tải file và định tuyến tới hàng đợi SQS.</i></p>

![IAM Role Permissions](/images/1-Worklog/1.10-Week10/week10-7.png)
<p align="center"><i>Hình 7: Khởi tạo IAM Role với các nhóm quyền chuyên biệt (S3, DynamoDB, Textract, SQS) chuẩn bị cho động cơ xử lý tài liệu AI.</i></p>

![IAM Role Permissions](/images/1-Worklog/1.10-Week10/week10-8.png)
<p align="center"><i>Hình 8: Khởi tạo IAM Role với các nhóm quyền chuyên biệt (S3, DynamoDB, Textract, SQS) chuẩn bị cho động cơ xử lý tài liệu AI.</i></p>