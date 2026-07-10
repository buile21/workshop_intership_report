---
title: "Tuần 4: Các dịch vụ Cơ sở dữ liệu (Amazon RDS, DynamoDB, ElastiCache)"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Mục tiêu Tuần 4:
* Phân biệt và nắm vững các use-case thực tế của Cơ sở dữ liệu quan hệ (Amazon RDS) và phi quan hệ NoSQL (Amazon DynamoDB).
* Đi sâu vào kiến trúc và cách thiết kế bảng trong Amazon DynamoDB - dịch vụ lưu trữ dữ liệu cốt lõi.
* Tìm hiểu cơ chế tăng tốc độ truy xuất dữ liệu, giảm tải cho Database chính bằng bộ nhớ đệm (Amazon ElastiCache).

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tìm hiểu Cơ sở dữ liệu quan hệ Amazon RDS:<br>&emsp; + Các Database Engines hỗ trợ (MySQL, PostgreSQL...).<br>&emsp; + Cơ chế tính sẵn sàng cao: Multi-AZ deployments.<br>&emsp; + Tối ưu hiệu suất đọc với Read Replicas. | 11/05/2026 | 11/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - Nghiên cứu chuyên sâu Amazon DynamoDB (NoSQL):<br>&emsp; + Khái niệm Tables, Items, Attributes.<br>&emsp; + Cách chọn Partition Key và Sort Key hợp lý.<br>&emsp; + Phân biệt On-demand capacity và Provisioned capacity (RCU/WCU). | 12/05/2026 | 12/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Tìm hiểu bộ nhớ đệm Amazon ElastiCache:<br>&emsp; + Phân biệt Redis và Memcached.<br>&emsp; + Các chiến lược Caching phổ biến (Lazy Loading, Write Through) để tối ưu truy vấn Database. | 13/05/2026 | 13/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Thực hành DynamoDB:**<br>&emsp; + Khởi tạo bảng **fcaj-idp-metadata** (lưu trữ thông tin tài liệu sau khi xử lý AI).<br>&emsp; + Thiết lập Partition Key là **document_id**.<br>&emsp; + Tạo Global Secondary Index (GSI) để hỗ trợ truy vấn theo **upload_date**. | 14/05/2026 | 14/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thực hành RDS & Thao tác dữ liệu:**<br>&emsp; + Tạo thử nghiệm một Amazon RDS MySQL (Free Tier) để quan sát thời gian provisioning.<br>&emsp; + Chèn (Insert) các Item JSON mẫu vào bảng DynamoDB qua giao diện Explore items.<br>&emsp; + So sánh tốc độ và cách tương tác giữa SQL và NoSQL trên Console. | 15/05/2026 | 15/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Nắm vững tư duy thiết kế schema NoSQL trên DynamoDB, phân biệt rõ cách hoạt động của Partition Key và Sort Key để không bị "nghẽn cổ chai" khi truy xuất dữ liệu.
* Tự tay khởi tạo thành công bảng DynamoDB **fcaj-idp-metadata** sẵn sàng tích hợp với AWS Lambda cho hệ thống IDP.
* Đã biết cách tạo Global Secondary Indexes (GSI) để giải quyết bài toán truy vấn dữ liệu linh hoạt trên DynamoDB mà không cần quét toàn bộ bảng (Scan).
* Trải nghiệm thực tế quá trình khởi tạo Amazon RDS, nhận thức rõ sự khác biệt về thời gian chờ và quản lý hạ tầng so với tính chất Serverless "dùng ngay lập tức" của DynamoDB.

---
![DynamoDB Table Creation](../../images/1-Worklog/1.4-Week4/week4-1.png)
<p align="center"><i>Hình 1: Bảng Amazon DynamoDB <b>fcaj-idp-metadata</b> được khởi tạo thành công với cấu hình Capacity mode là On-demand.</i></p>

![DynamoDB Explore Items](../../images/1-Worklog/1.4-Week4/week4-2.png)
<p align="center"><i>Hình 2: Giao diện Explore items hiển thị các bản ghi (items) định dạng JSON mẫu đã được chèn thành công vào bảng DynamoDB.</i></p>

![Amazon RDS Dashboard](../../images/1-Worklog/1.4-Week4/week4-3.png)
<p align="center"><i>Hình 3: Giao diện Amazon RDS hiển thị một database MySQL ở trạng thái Available, sẵn sàng kết nối.</i></p>