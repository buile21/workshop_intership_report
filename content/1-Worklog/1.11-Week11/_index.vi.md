---
title: "Tuần 11: Triển khai Đồ án - Xây dựng Động cơ Xử lý Cốt lõi (Amazon Textract, AWS Lambda)"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu Tuần 11:
* Xây dựng và cấu hình môi trường tính toán phi máy chủ với AWS Lambda đáp ứng tải xử lý dữ liệu lớn.
* Tích hợp Amazon Textract bằng Python (thư viện `boto3`) để trích xuất tự động các trường dữ liệu quan trọng từ hóa đơn thông qua các truy vấn ngôn ngữ tự nhiên.
* Kết nối luồng dữ liệu từ hệ thống Amazon SQS để xử lý sự kiện bất đồng bộ và lưu trữ kết quả có cấu trúc vào cơ sở dữ liệu.

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - **Khởi tạo hàm AWS Lambda chuyên trách AI:**<br>&emsp; + Tạo hàm `idp-ai-worker` bằng tùy chọn Author from scratch với môi trường Runtime Python 3.12.<br>&emsp; + Cấu hình mục Permissions, chọn Custom execution role là `idp-lambda-ai-role` đã được thiết lập đầy đủ các chính sách bảo mật từ tuần trước. | 29/06/2026 | 29/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - **Tối ưu hóa tài nguyên & Cấu hình bộ kích hoạt (Trigger):**<br>&emsp; + Truy cập General configuration, nâng cấp cấu hình bộ nhớ bộ đệm (Memory) từ 128 MB lên 256 MB và thời gian chờ tối đa (Timeout) lên 1 min 0 sec nhằm tối ưu tác vụ chạy mô hình bóc tách dữ liệu AI.<br>&emsp; + Cấu hình Add trigger từ nguồn Amazon SQS, trỏ đích danh đến hàng đợi `idp-document-queue` với Batch size tiêu chuẩn là 10. | 30/06/2026 | 30/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - **Lập trình Logic tiếp nhận thông điệp (Phần 1):**<br>&emsp; + Viết mã nguồn Python sử dụng thư viện `boto3` để khởi tạo client kết nối với dịch vụ Amazon Textract và Amazon DynamoDB.<br>&emsp; + Triển khai hàm `lambda_handler` lặp qua danh sách sự kiện bất đồng bộ `Records` đẩy sang từ SQS, giải mã JSON payload để lấy ra chính xác thông tin `bucket_name` và `object_key` (được làm sạch bằng `urllib.parse.unquote_plus`). | 01/07/2026 | 01/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Lập trình tích hợp Trí tuệ nhân tạo Amazon Textract (Phần 2):**<br>&emsp; + Sử dụng phương thức `analyze_document` với cấu hình tham số `FeatureTypes=["QUERIES"]`.<br>&emsp; + Thiết lập cấu hình `QueriesConfig` để đặt 4 câu hỏi trích xuất tự nhiên: Số hóa đơn (`invoice_number`), Ngày tháng (`date`), Tổng số tiền (`total_amount`), và Tên nhà cung cấp (`vendor_name`).<br>&emsp; + Viết hàm duyệt qua các `Blocks` để ánh xạ chính xác mối quan hệ (`Relationships`) giữa câu hỏi (`QUERY`) và câu trả lời (`ANSWER`) thành cấu trúc JSON rõ ràng. | 02/07/2026 | 02/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Lưu trữ dữ liệu vào CSDL NoSQL & Kiểm thử luồng:**<br>&emsp; + Kết nối với bảng `InvoicesData` trên DynamoDB.<br>&emsp; + Tạo cấu trúc tài liệu lưu trữ gồm khóa chính `documentId` (sinh ngẫu nhiên bằng `uuid.uuid4()`), tên tệp gốc, thời gian tải lên hệ thống (`datetime.now().isoformat()`), và cụm dữ liệu AI vừa trích xuất.<br>&emsp; + Thực hiện lệnh `table.put_item()`, Deploy mã nguồn và tiến hành tải thử nghiệm hóa đơn lên S3 để kiểm tra luồng xử lý tự động từ đầu đến cuối (E2E). | 03/07/2026 | 03/07/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Động cơ tính toán Lambda vận hành ổn định, tự động co giãn (scale) số lượng thực thi dựa trên số lượng thông điệp thực tế được đẩy về từ hàng đợi SQS.
* Ứng dụng thành công tính năng Amazon Textract Queries giúp bóc tách các trường dữ liệu phi cấu trúc phức tạp trên hóa đơn thành cấu trúc JSON một cách chính xác mà không cần định nghĩa biểu mẫu cố định (Template-less).
* Luồng xử lý bất đồng bộ khép kín hoàn hảo: Tệp tin đẩy lên S3 -> SQS nhận sự kiện -> Kích hoạt Lambda xử lý AI -> Lưu trữ trực tiếp kết quả sạch xuống DynamoDB thành công, chuẩn bị sẵn sàng dữ liệu cho lớp ứng dụng Frontend.

---
![Khởi tạo Lambda](/workshop_intership_report/images/1-Worklog/1.11-Week11/week11-1.png)
<p align="center"><i>Hình 1: Giao diện khởi tạo thành công hàm Lambda idp-ai-worker sử dụng môi trường chạy Python 3.12 và cấu hình Execution role chuyên biệt.</i></p>

![Lambda Memory Config](/workshop_intership_report/images/1-Worklog/1.11-Week11/week11-2.png)
<p align="center"><i>Hình 2: Cấu hình điều chỉnh nâng thông số tài nguyên RAM (256 MB) và giới hạn Timeout (1 phút) phục vụ tốt cho tác vụ phân tích tài liệu AI nặng.</i></p>

![SQS Trigger Config](/workshop_intership_report/images/1-Worklog/1.11-Week11/week11-3.png)
<p align="center"><i>Hình 3: Cấu hình liên kết hàng đợi Amazon SQS (idp-document-queue) làm trigger kích hoạt tự động cho hàm Lambda với kiến trúc xử lý mẻ Batch size bằng 10.</i></p>