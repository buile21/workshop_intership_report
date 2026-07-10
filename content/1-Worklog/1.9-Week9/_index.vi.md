---
title: "Tuần 9: Tích hợp Ứng dụng & Kiến trúc Hướng sự kiện (Amazon SQS, SNS, EventBridge)"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---


### Mục tiêu Tuần 9:
* Hiểu rõ triết lý của Kiến trúc Hướng sự kiện (Event-Driven Architecture - EDA) và lợi ích của việc nới lỏng liên kết (decoupling) giữa các dịch vụ trong hệ thống Serverless.
* Nắm vững cơ chế hoạt động, thông số cấu hình và use-case thực tế của hàng đợi thông điệp Amazon SQS (Simple Queue Service) và dịch vụ xuất bản/đăng ký Amazon SNS (Simple Notification Service).
* Sử dụng Amazon EventBridge để thiết lập các quy tắc định tuyến sự kiện linh hoạt, làm xương sống điều khiển luồng tài liệu cho hệ thống IDP.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tìm hiểu dịch vụ hàng đợi thông điệp Amazon SQS:<br>&emsp; + Phân biệt Standard Queue và FIFO Queue.<br>&emsp; + Các thông số: Visibility Timeout, Long Polling vs Short Polling.<br>&emsp; + Cơ chế xử lý thư rác với Dead Letter Queue (DLQ). | 15/06/2026 | 15/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - Nghiên cứu dịch vụ thông báo Amazon SNS:<br>&emsp; + Khái niệm Topics, Subscriptions (Email, SMS, HTTP, Lambda, SQS).<br>&emsp; + Kiến trúc mở rộng Fan-out pattern (SNS gửi đồng thời tới nhiều SQS). | 16/06/2026 | 16/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Tìm hiểu Amazon EventBridge (Event Bus):<br>&emsp; + Mô hình định tuyến sự kiện qua: Event source, Rules, và Targets.<br>&emsp; + Cách bắt các sự kiện thay đổi trạng thái tài nguyên từ các dịch vụ AWS khác. | 17/06/2026 | 17/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Thực hành SQS & SNS (Mô hình Fan-out):**<br>&emsp; + Tạo một SNS Standard Topic mang tên **fcaj-idp-notifications**.<br>&emsp; + Tạo một SQS Standard Queue mang tên **fcaj-idp-document-queue**.<br>&emsp; + Cấu hình Subscribe để SQS đăng ký nhận tin từ SNS Topic, thử nghiệm gửi một thông điệp (Publish message) từ SNS để kiểm tra tin nhắn tự động đổ về SQS. | 18/06/2026 | 18/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thực hành EventBridge:**<br>&emsp; + Tạo một EventBridge Rule lắng nghe sự kiện từ S3 Bucket khi có tệp tin mới được tải lên.<br>&emsp; + Định tuyến sự kiện đó để tự động kích hoạt mục tiêu (Target) là hàng đợi SQS hoặc hàm Lambda, kiểm tra dữ liệu sự kiện (event payload) được truyền đi. | 19/06/2026 | 19/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Thay đổi tư duy thiết kế hệ thống từ dạng đồng bộ (Synchronous) sang bất đồng bộ (Asynchronous), giúp hệ thống IDP tăng khả năng chịu tải và giảm thiểu rủi ro nghẽn cổ chai.
* Triển khai thành công mô hình Fan-out (SNS + SQS), hiểu cách một sự kiện đầu vào có thể kích hoạt song song nhiều tác vụ xử lý độc lập ngầm (như vừa bóc tách text, vừa gửi mail thông báo).
* Làm chủ Amazon EventBridge, biết cách quản lý và lọc các sự kiện hệ thống theo mẫu (Event Patterns) một cách chính xác.
* Nâng cao kỹ năng debug luồng dữ liệu phân tán bằng cách theo dõi các thông điệp di chuyển qua lại giữa các dịch vụ tích ứng dụng.

---
![SNS Topic and SQS Subscription](/static/images/1-Worklog/1.9-Week9/week9-1.png)
<p align="center"><i>Hình 1: Cấu hình Amazon SNS Topic kết nối thành công với hàng đợi Amazon SQS theo mô hình kiến trúc Fan-out.</i></p>

![SQS Message Polling](/static/images/1-Worklog/1.9-Week9/week9-2.png)
<p align="center"><i>Hình 2: Giao diện SQS Explore messages cho thấy các thông điệp đã được đẩy vào hàng đợi thành công và sẵn sàng để xử lý.</i></p>

![EventBridge Rule Configuration](/static/images/1-Worklog/1.9-Week9/week9-3.png)
<p align="center"><i>Hình 3: Quy tắc (Rule) trên Amazon EventBridge được thiết lập thành công để bắt sự kiện từ S3 Bucket và chuyển tiếp tới Target.</i></p>