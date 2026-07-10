---
title: "Tuần 1: Làm quen với AWS và các dịch vụ cơ bản"
date: 2026-04-17
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---


### Mục tiêu Tuần 1:
* Kết nối, làm quen với văn hóa và các thành viên trong chương trình First Cloud AI Journey.
* Nắm vững các khái niệm Điện toán đám mây cốt lõi và các nhóm dịch vụ cơ bản của AWS.
* Thành thạo thao tác cấu hình và tương tác với AWS thông qua giao diện web (Console) và dòng lệnh (AWS CLI).

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 6**<br>(Day 1) | - Gặp gỡ, làm quen với các thành viên và mentor FCAJ.<br>- Đọc và ghi chú các nội quy, quy trình làm việc nội bộ của chương trình Bootcamp. | 17/04/2026 | 17/04/2026 |
| **Thứ 2**<br>(Day 2) | - Tìm hiểu tổng quan về AWS và các nhóm dịch vụ cốt lõi:<br>&emsp; + Compute (Điện toán)<br>&emsp; + Storage (Lưu trữ)<br>&emsp; + Networking (Mạng)<br>&emsp; + Database (Cơ sở dữ liệu) | 20/04/2026 | 20/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 3) | - Khởi tạo tài khoản AWS Free Tier.<br>- Làm quen với giao diện AWS Management Console.<br>- Cài đặt và cấu hình AWS CLI trên môi trường local. | 21/04/2026 | 21/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 4) | - **Thực hành CLI:**<br>&emsp; + Cấu hình Access Key & Secret Key.<br>&emsp; + Thử nghiệm các câu lệnh cơ bản (**aws sts get-caller-identity**, **aws ec2 describe-regions**). | 22/04/2026 | 22/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 5) | - Tìm hiểu dịch vụ Amazon EC2 cơ bản:<br>&emsp; + Các loại Instance types.<br>&emsp; + AMI (Amazon Machine Image).<br>&emsp; + Phân biệt EBS và Instance Store.<br>&emsp; + Tìm hiểu về Elastic IP. | 23/04/2026 | 23/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 6) | - **Thực hành EC2:**<br>&emsp; + Khởi chạy 1 máy chủ EC2 Linux.<br>&emsp; + Tạo Key Pair và kết nối SSH thành công.<br>&emsp; + Gắn thêm (Attach) một phân vùng EBS volume vào EC2. | 24/04/2026 | 24/04/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Hiểu rõ kiến trúc tổng quan của AWS và phân biệt được công năng của các nhóm dịch vụ chính (Compute, Storage, Network, Database).
* Khởi tạo thành công tài khoản AWS Free Tier để phục vụ cho suốt quá trình làm đồ án thực tập.
* Cấu hình thành công môi trường làm việc local: tích hợp AWS CLI, khai báo bảo mật bằng Access/Secret Keys đúng chuẩn.
* Vận hành trơn tru máy chủ ảo đầu tiên: Tự tay deploy một bản phân phối Linux trên Amazon EC2, thiết lập Security Group cơ bản và truy cập từ xa thông qua giao thức SSH.
* Nhạy bén hơn trong việc sử dụng Document của AWS để tra cứu tài liệu khi cấu hình dịch vụ.

---
![AWS CLI Configuration](/static/images/1-Worklog/1.1-Week1/week1-1.png)
<p align="center"><i>Hình 1: Kiểm tra cấu hình AWS CLI thành công trên máy tính bằng lệnh <b>aws sts get-caller-identity</b>.</i></p>

![EC2 Dashboard](/static/images/1-Worklog/1.1-Week1/week1-2.png)
<p align="center"><i>Hình 2: Máy chủ ảo EC2 được khởi tạo thành công và đang hoạt động (trạng thái Running) trên giao diện AWS Management Console.</i></p>

![SSH Terminal](/static/images/1-Worklog/1.1-Week1/week1-3.png)
<p align="center"><i>Hình 3: Kết nối SSH thành công vào bên trong máy chủ EC2 từ terminal local.</i></p>