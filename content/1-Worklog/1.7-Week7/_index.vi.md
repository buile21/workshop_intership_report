---
title: "Tuần 7: Các dịch vụ Trí tuệ Nhân tạo & Học máy (Amazon Textract, Amazon SageMaker)"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Mục tiêu Tuần 7:
* Khám phá tầng dịch vụ AI/ML của AWS, cho phép tích hợp trí tuệ nhân tạo và xử lý dữ liệu nâng cao vào hệ thống.
* Ứng dụng Amazon Textract để tự động hóa việc trích xuất văn bản, cấu trúc dữ liệu từ tài liệu quét.
* Khởi tạo môi trường làm việc Data Science chuyên nghiệp trên AWS (Amazon SageMaker Notebook Instances) để làm tiền đề phát triển các thuật toán dự báo chuỗi thời gian (Time-series) cho đồ án sắp tới.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - Tổng quan về AWS Machine Learning Stack:<br>&emsp; + Phân lớp dịch vụ: AI Services, ML Services (SageMaker) và ML Frameworks.<br>&emsp; + Các Use-case thực tế của AI trên đám mây. | 01/06/2026 | 01/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - Tìm hiểu dịch vụ xử lý tài liệu thông minh Amazon Textract:<br>&emsp; + Tính năng Detect Document Text và Analyze Document.<br>&emsp; + Cách trích xuất dữ liệu theo cấu trúc bảng (Tables) và biểu mẫu (Forms). | 02/06/2026 | 02/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - Nghiên cứu hệ sinh thái Amazon SageMaker:<br>&emsp; + Kiến trúc của SageMaker Notebook Instances.<br>&emsp; + Phương pháp cài đặt thư viện và xử lý dữ liệu Pandas/NumPy trên đám mây để giải quyết bài toán dự báo. | 03/06/2026 | 03/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Thực hành Amazon Textract:**<br>&emsp; + Sử dụng Textract Console để phân tích biểu mẫu tài liệu mẫu.<br>&emsp; + Quan sát kết quả trả về dưới dạng JSON (Key-Value pairs) và bounding boxes. | 04/06/2026 | 04/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Thực hành SageMaker Notebook (Chuẩn bị Đồ án):**<br>&emsp; + Cấp phép IAM Role và khởi tạo thành công máy chủ ảo **fcaj-revenue-notebook**.<br>&emsp; + Truy cập môi trường Jupyter, upload tập dữ liệu lịch sử doanh thu thương mại điện tử (CSV).<br>&emsp; + Khởi tạo dự án Data Prep bằng Python (Pandas), sẵn sàng cho bước huấn luyện mô hình. | 05/06/2026 | 05/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Nắm vững khả năng của Amazon Textract, hiểu cách bóc tách chính xác các trường dữ liệu từ tài liệu để tự động hóa khâu xử lý đầu vào.
* Vượt qua các rào cản về giới hạn tài nguyên (Quotas) của tài khoản thực tập để triển khai thành công môi trường máy học Amazon SageMaker Notebook.
* Đưa thành công dữ liệu doanh thu lên môi trường Jupyter trên đám mây, thiết lập bước đệm kỹ thuật vững chắc để code các mô hình dự báo chuỗi thời gian cho Đồ án thương mại điện tử.
* Nâng cao nhận thức về quản lý chi phí bằng thói quen tắt (Stop) các Notebook Instances ngay sau quá trình nghiên cứu.

---
![Amazon Textract Analysis](images/1-Worklog/1.7-Week7/week7-1.png)
<p align="center"><i>Hình 1: Giao diện Amazon Textract phân tích thành công một tài liệu mẫu, bóc tách chính xác các trường dữ liệu dạng Key-Value.</i></p>

![SageMaker Notebook InService](images/1-Worklog/1.7-Week7/week7-2.png)
<p align="center"><i>Hình 2: Khởi tạo thành công máy chủ ảo Amazon SageMaker Notebook (trạng thái InService) để phục vụ việc nghiên cứu mô hình Học máy.</i></p>

![SageMaker Jupyter Environment](images/1-Worklog/1.7-Week7/week7-3.png)
<p align="center"><i>Hình 3: Giao diện Jupyter Notebook trên SageMaker, chuẩn bị sẵn sàng dữ liệu chuỗi thời gian (doanh thu) bằng thư viện Pandas.</i></p>