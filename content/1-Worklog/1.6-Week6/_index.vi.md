---
title: "Tuần 6: Điện toán Không máy chủ (AWS Lambda, Amazon API Gateway, AWS Step Functions)"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Mục tiêu Tuần 6:
* Hiểu rõ triết lý kiến trúc Serverless: Không quản lý máy chủ, tự động mở rộng (auto-scaling) và tính phí theo thời gian chạy thực tế (pay-as-you-go).
* Thực hành viết và triển khai mã nguồn không máy chủ với AWS Lambda, tích hợp IAM Role để tương tác an toàn với S3 và DynamoDB.
* Xây dựng các cổng giao tiếp API RESTful bằng Amazon API Gateway để kết nối Frontend/Client với Backend Lambda.
* Nắm vững cách điều phối nhiều hàm Lambda thành một quy trình nghiệp vụ hoàn chỉnh (Workflow) bằng AWS Step Functions.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tìm hiểu dịch vụ điện toán AWS Lambda:<br>&emsp; + Cơ chế hoạt động: Triggers, Execution Environment, Cold Start / Warm Start.<br>&emsp; + Quản lý Dependency và Lambda Layers.<br>&emsp; + Cấu hình Timeout và Memory. | 25/05/2026 | 25/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - Tìm hiểu dịch vụ Amazon API Gateway:<br>&emsp; + Phân biệt REST API, HTTP API và WebSocket API.<br>&emsp; + Cơ chế tích hợp Lambda Proxy Integration.<br>&emsp; + Quản lý Stages và Deployments. | 26/05/2026 | 26/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Nghiên cứu AWS Step Functions (Orchestration):<br>&emsp; + Phân biệt Standard và Express Workflows.<br>&emsp; + Tìm hiểu ngôn ngữ Amazon States Language (ASL).<br>&emsp; + Xử lý lỗi (Error handling) và Retry mechanisms trong luồng. | 27/05/2026 | 27/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Thực hành Lambda & API Gateway:**<br>&emsp; + Viết hàm Lambda **fcaj-idp-hello-function** bằng Python/Node.js.<br>&emsp; + Cấp quyền (Execution Role) cơ bản cho hàm.<br>&emsp; + Tạo REST API trên API Gateway, định tuyến method GET gọi tới hàm Lambda vừa tạo và test thử bằng Postman/Trình duyệt. | 28/05/2026 | 28/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thực hành Step Functions:**<br>&emsp; + Sử dụng Workflow Studio để kéo thả một State Machine đơn giản mang tên **fcaj-idp-doc-workflow**.<br>&emsp; + Giả lập các bước: Pass (Bắt đầu) -> Task (Gọi Lambda) -> Choice (Phân loại thành công/thất bại).<br>&emsp; + Chạy thử (Start Execution) và quan sát biểu đồ luồng trực quan. | 29/05/2026 | 29/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Rũ bỏ tư duy quản trị máy chủ (EC2) truyền thống, chuyển đổi thành công sang tư duy triển khai mã nguồn độc lập với AWS Lambda.
* Biết cách mở luồng giao tiếp ra bên ngoài an toàn bằng cách cấu hình Amazon API Gateway kết nối trực tiếp với Lambda (Serverless Backend hoàn chỉnh).
* Làm quen với ngôn ngữ ASL và Workflow Studio, tự tay thiết kế được một bản thảo quy trình xử lý tài liệu (State Machine) bằng giao diện đồ họa.
* Hiểu cách chia nhỏ một ứng dụng nguyên khối (Monolithic) thành các hàm microservices nhỏ gọn, điều phối nhịp nhàng bằng Step Functions để tránh tình trạng Lambda bị gọi lồng nhau (Anti-pattern).

---
![AWS Lambda Function](images/1-Worklog/1.6-Week6/week6-1.png)
<p align="center"><i>Hình 1: Giao diện quản lý hàm <b>fcaj-idp-hello-function</b> trên AWS Lambda kèm theo mã nguồn (source code) sẵn sàng để thực thi.</i></p>

![API Gateway Integration](images/1-Worklog/1.6-Week6/week6-2.png)
<p align="center"><i>Hình 2: Cấu hình tích hợp thành công giữa Amazon API Gateway (phương thức GET) và AWS Lambda để tạo thành một endpoint API hoàn chỉnh.</i></p>

![Step Functions Workflow](images/1-Worklog/1.6-Week6/week6-3.png)
<p align="center"><i>Hình 3: Biểu đồ trực quan (Visual Workflow) của một State Machine mô phỏng quy trình xử lý tài liệu trên AWS Step Functions.</i></p>