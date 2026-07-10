---
title: "Tuần 3: Kiến thức cốt lõi về Mạng (VPC, Route 53, CloudFront)"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---


### Mục tiêu Tuần 3:
* Hiểu rõ kiến trúc mạng riêng ảo trên đám mây (Amazon VPC) và cách điều hướng luồng dữ liệu (Routing, Internet Gateway).
* Cấu hình các lớp màng lọc bảo mật mạng khắt khe với Security Groups và Network ACLs.
* Tìm hiểu dịch vụ phân phối nội dung (CloudFront) và quản lý tên miền (Route 53) để chuẩn bị cho việc tối ưu tốc độ truyền tải tài liệu hệ thống sau này.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tìm hiểu kiến thức nền tảng về Amazon VPC:<br>&emsp; + VPC, CIDR block, IPv4 cơ bản.<br>&emsp; + Phân biệt Public Subnet và Private Subnet.<br>&emsp; + Route Tables và Internet Gateway (IGW). | 04/05/2026 | 04/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - Tìm hiểu các cơ chế bảo mật mạng:<br>&emsp; + Phân biệt Security Groups (Stateful) và Network ACLs (Stateless).<br>&emsp; + Cơ chế hoạt động của NAT Gateway dành cho Private Subnet. | 05/05/2026 | 05/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Tìm hiểu dịch vụ quản lý phân giải tên miền Amazon Route 53:<br>&emsp; + Các khái niệm: DNS, Hosted Zones, Records (A, CNAME, Alias).<br>&emsp; + Các chiến lược định tuyến (Routing Policies). | 06/05/2026 | 06/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - Tìm hiểu dịch vụ Mạng phân phối nội dung (CDN) - Amazon CloudFront:<br>&emsp; + Cơ chế Caching và Edge Locations.<br>&emsp; + Tích hợp CloudFront với S3 để bảo mật bucket (Origin Access Control - OAC). | 07/05/2026 | 07/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thực hành Mạng (Tổng hợp):**<br>&emsp; + Tự thiết kế và tạo một Custom VPC hoàn chỉnh (**fcaj-idp-vpc**).<br>&emsp; + Cấu hình Security Group chỉ cho phép SSH từ IP máy cá nhân.<br>&emsp; + Thiết lập Route Table điều hướng luồng mạng ra Internet Gateway. | 08/05/2026 | 08/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Tự tay thiết kế và triển khai thành công một môi trường mạng riêng ảo (Custom VPC) cô lập và an toàn, đảm bảo nắm vững luồng đi của dữ liệu.
* Thiết lập chặt chẽ các quy tắc tường lửa thông qua Security Group, tuân thủ nguyên tắc chỉ mở các cổng mạng (ports) thực sự cần thiết.
* Nắm vững cơ chế định tuyến (Routing) bằng cách cấu hình Route Table kết nối chính xác với Internet Gateway.
* Hiểu rõ phương thức hoạt động của CloudFront kết hợp OAC để bọc bảo mật cho kho tài liệu S3.

---
![Custom VPC Resource Map](images/1-Worklog/1.3-Week3/week3-1.png)
<p align="center"><i>Hình 1: Bản đồ tài nguyên mạng (Resource map) hiển thị Custom VPC vừa tạo với Public/Private Subnets và cách điều hướng luồng mạng.</i></p>

![Security Group Inbound Rules](images/1-Worklog/1.3-Week3/week3-2.png)
<p align="center"><i>Hình 2: Cấu hình Inbound rules của Security Group được thiết lập nghiêm ngặt, chỉ cho phép cổng SSH (22) từ địa chỉ IP cá nhân.</i></p>

![VPC Route Table](images/1-Worklog/1.3-Week3/week3-3.png)
<p align="center"><i>Hình 3: Cấu hình Route Table cho Public Subnet, điều hướng luồng traffic ra Internet thành công thông qua Internet Gateway (IGW).</i></p>