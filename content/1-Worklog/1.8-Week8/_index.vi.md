---
title: "Tuần 8: Cơ sở hạ tầng dưới dạng Mã (IaC) & Giám sát (AWS CloudFormation, AWS SAM, CloudWatch)"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---


### Mục tiêu Tuần 8:
* Nắm bắt triết lý Cơ sở hạ tầng dưới dạng mã (Infrastructure as Code - IaC) để tự động hóa, chuẩn hóa và quản lý phiên bản cho hạ tầng đám mây.
* Làm quen với AWS CloudFormation và AWS Serverless Application Model (SAM) - công cụ chuyên dụng để triển khai nhanh các kiến trúc Serverless.
* Thiết lập hệ thống giám sát, thu thập log và cảnh báo tự động (monitoring, logging, alerting) nhằm đảm bảo độ tin cậy của hệ thống bằng Amazon CloudWatch.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tìm hiểu dịch vụ AWS CloudFormation:<br>&emsp; + Các khái niệm cốt lõi: Templates (YAML/JSON), Stacks, Resources, Parameters.<br>&emsp; + Lợi ích của việc tự động hóa cấp phát tài nguyên (Provisioning). | 08/06/2026 | 08/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - Nghiên cứu AWS Serverless Application Model (SAM):<br>&emsp; + So sánh SAM và CloudFormation truyền thống.<br>&emsp; + Tìm hiểu cấu trúc template của SAM (**AWS::Serverless::Function**, **AWS::Serverless::Api**). | 09/06/2026 | 09/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Tìm hiểu dịch vụ giám sát Amazon CloudWatch:<br>&emsp; + Phân biệt CloudWatch Metrics (Chỉ số) và CloudWatch Logs (Nhật ký).<br>&emsp; + Cơ chế thiết lập cảnh báo tự động (CloudWatch Alarms). | 10/06/2026 | 10/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Thực hành CloudFormation:**<br>&emsp; + Viết một template YAML cơ bản.<br>&emsp; + Khởi tạo (Deploy) Stack **fcaj-week8-stack** trên giao diện CloudFormation để tự động tạo một S3 Bucket. | 11/06/2026 | 11/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thực hành CloudWatch:**<br>&emsp; + Chạy thử một hàm Lambda và truy xuất Log Groups để đọc thông báo thực thi.<br>&emsp; + Tạo một Alarm đơn giản giám sát số lượng lỗi (Errors) của hàm Lambda vượt ngưỡng. | 12/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Thay đổi hoàn toàn tư duy cấp phát tài nguyên: chuyển từ việc "click chuột thủ công" (ClickOps) sang quản lý hạ tầng bằng những dòng code (IaC) chuyên nghiệp, an toàn và dễ tái sử dụng.
* Triển khai thành công tài nguyên thông qua AWS CloudFormation Stack, hiểu rõ vòng đời khởi tạo và xóa tài nguyên tự động.
* Làm chủ Amazon CloudWatch, biết cách truy vết lỗi ứng dụng Serverless thông qua Log Groups – một kỹ năng bắt buộc phải có để debug các hệ thống phân tán.
* Nắm vững cách thiết lập chuông cảnh báo tự động (Alarms) khi hệ thống có dấu hiệu quá tải hoặc phát sinh lỗi.

---
![AWS CloudFormation Stack](../../images/1-Worklog/1.8-Week8/week8-1.png)
<p align="center"><i>Hình 1: Giao diện AWS CloudFormation triển khai thành công một Stack (CREATE_COMPLETE) tự động cấp phát tài nguyên từ template YAML.</i></p>

![Amazon CloudWatch Logs](../../images/1-Worklog/1.8-Week8/week8-2.png)
<p align="center"><i>Hình 2: Trình xem nhật ký (Log groups) trên Amazon CloudWatch hiển thị chi tiết các luồng thực thi (Log streams) của hệ thống Serverless.</i></p>

![Amazon CloudWatch Alarm](../../images/1-Worklog/1.8-Week8/week8-3.png)
<p align="center"><i>Hình 3: Thiết lập thành công chuông cảnh báo tự động (Alarm) trên CloudWatch giám sát chỉ số (Metrics) hoạt động của dịch vụ.</i></p>