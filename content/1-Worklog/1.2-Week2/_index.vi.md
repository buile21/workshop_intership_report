---
title: "Tuần 2: Tìm hiểu chuyên sâu về Lưu trữ & Quản lý Truy cập (Amazon S3, IAM)"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu Tuần 2:
* Hiểu rõ và thực hành chuyên sâu dịch vụ lưu trữ Amazon S3.
* Nắm vững cơ chế quản lý định danh và phân quyền an toàn với AWS IAM theo nguyên tắc quyền hạn tối thiểu.
* Tương tác thành thạo với S3 thông qua AWS CLI và thiết lập Resource Tags để quản lý tài nguyên.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tìm hiểu dịch vụ Amazon S3:<br>&emsp; + Các khái niệm: Buckets, Objects, Keys.<br>&emsp; + Phân biệt các Storage Classes (Standard, Infrequent Access, Glacier...).<br>&emsp; + Tính năng Versioning và Object Lock. | 27/04/2026 | 27/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - **Thực hành S3 & CLI:**<br>&emsp; + Tạo S3 Bucket đảm bảo tính duy nhất (Global Unique Name).<br>&emsp; + Dùng AWS CLI upload/download file (**aws s3 cp**, **aws s3 sync**).<br>&emsp; + Viết Bucket Policy chặn quyền truy cập public. | 28/04/2026 | 28/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Tìm hiểu chuyên sâu AWS IAM:<br>&emsp; + Phân biệt Users, Groups, Roles và Policies.<br>&emsp; + Hiểu cấu trúc của một JSON IAM Policy (Effect, Action, Resource).<br>&emsp; + Tại sao nên dùng Role cho dịch vụ (Service Role) thay vì dùng Access Key. | 29/04/2026 | 29/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Thực hành IAM (Tự học/Nghiên cứu):**<br>&emsp; + Tạo IAM Role với quyền **AmazonS3ReadOnlyAccess**.<br>&emsp; + Gắn Role này vào máy chủ EC2 (đã tạo ở tuần 1) để EC2 có thể đọc file từ S3 mà không cần lưu hardcode Access Key. | 30/04/2026 | 30/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - Tìm hiểu và thực hành AWS Resource Tags:<br>&emsp; + Đặt Tag (Project: IDP, Environment: Dev) cho S3 Bucket và EC2.<br>&emsp; + Tổng kết, dọn dẹp tài nguyên để tránh phát sinh chi phí. | 01/05/2026 | 01/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Khởi tạo và cấu hình thành công Amazon S3 Bucket với các chính sách bảo mật chặt chẽ (chặn Public Access).
* Vận dụng thành thạo các câu lệnh AWS CLI để đồng bộ và chuyển dữ liệu tài liệu lên không gian lưu trữ S3.
* Xây dựng được nền tảng bảo mật vững chắc cho dự án: thiết lập thành công IAM Role và gắn vào tài nguyên thay vì quản lý thủ công bằng khóa bảo mật (Access Key).
* Đọc hiểu và tự viết được các đoạn JSON IAM Policies cơ bản để cấp quyền chính xác cho các dịch vụ.
* Hình thành thói quen gắn thẻ tài nguyên một cách có hệ thống, giúp ích lớn cho việc quản lý chi phí AWS sau này.

---
![S3 Bucket Creation](/images/1-Worklog/1.2-Week2/week2-1.png)
<p align="center"><i>Hình 1: Amazon S3 Bucket được tạo thành công với tính năng Block all public access được kích hoạt.</i></p>

![CLI S3 Copy](/images/1-Worklog/1.2-Week2/week2-2.png)
<p align="center"><i>Hình 2: Sử dụng lệnh <b>aws s3 cp</b> để upload thành công tài liệu mẫu từ máy tính local lên S3 Bucket.</i></p>

![IAM Role Creation](/images/1-Worklog/1.2-Week2/week2-3.png)
<p align="center"><i>Hình 3: Giao diện IAM hiển thị Role mới được tạo với quyền truy cập S3 và gắn thành công vào máy chủ EC2.</i></p>