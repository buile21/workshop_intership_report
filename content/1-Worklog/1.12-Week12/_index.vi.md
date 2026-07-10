---
title: "Tuần 12: Hoàn thiện Đồ án - Tích hợp API, Lưu trữ Dữ liệu (DynamoDB), Tối ưu hóa & Báo cáo Tổng kết"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu Tuần 12:
* Khởi tạo bộ khung cơ sở dữ liệu phi quan hệ (NoSQL) hoàn chỉnh với Amazon DynamoDB nhằm xử lý tốc độ cao các nghiệp vụ liên quan đến hóa đơn.
* Xây dựng hệ sinh thái API (API Gateway kết hợp cụm AWS Lambda) chịu trách nhiệm giao tiếp an toàn giữa Backend và ứng dụng ReactJS Frontend.
* Áp dụng tiêu chuẩn xác thực danh tính (Amazon Cognito), bảo mật mức ứng dụng (AWS WAF) và tự động hóa dọn dẹp dung lượng thừa (S3 Lifecycle).

### Các công việc thực hiện trong tuần:

| Ngày | Công việc thực hiện | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo (Link AWS Study Group) |
| :--- | :--- | :--- | :--- | :--- |
| **Thứ 2**<br>(Day 1) | - **Thiết lập cơ sở hạ tầng NoSQL DynamoDB:**<br>&emsp; + Khởi tạo 4 bảng dữ liệu với Read/write capacity settings là On-demand để tối ưu chi phí: `InvoicesData`, `InvoicesPayments`, `UserCategories`, và `UserBudgets`.<br>&emsp; + Xác định Partition keys chuẩn xác cho từng bảng (VD: `documentId` cho bảng InvoicesData, `userEmail` cho các bảng liên quan đến User). | 06/07/2026 | 06/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 3**<br>(Day 2) | - **Phát triển Cụm Lambda APIs (Backend):**<br>&emsp; + Viết hàm `idp-api-presign` cấp phép URL tải lên (`Content-Type` chuẩn) trực tiếp vào S3 `idp-ingest-bucket-1` giải quyết lỗi CORS 403.<br>&emsp; + Xây dựng các hàm Get API: `idp-api-get-invoices` (xử lý Data Masking che đi mã số thuế), `idp-api-get-stats` (xử lý biểu đồ doanh thu), `idp-api-categories` (phân loại chi phí Cloud/Vận hành), và `idp-api-payments` (theo dõi hóa đơn UNPAID). | 07/07/2026 | 07/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 4**<br>(Day 3) | - **Xây dựng API Gateway & Cognito Auth:**<br>&emsp; + Triển khai REST API tên `idp-rest-api` (Regional).<br>&emsp; + Gắn kết các endpoints (`/get-upload-url`, `/invoices`, `/stats`, v.v.) vào các hàm Lambda theo chế độ Lambda proxy integration và kích hoạt CORS.<br>&emsp; + Tạo Cognito User Pool `idp-react-app` (loại SPA), tắt tính năng Self-registration (không cho phép đăng ký tự do) và khởi tạo Cognito Authorizer trên API Gateway bảo vệ phương thức GET. | 08/07/2026 | 08/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 5**<br>(Day 4) | - **Cấu hình Phân phối CDN & Tường lửa WAF:**<br>&emsp; + Cấu hình AWS WAF với Rate-based rule tên `BlockSpamIP` tự động block kết nối nếu IP vượt ngưỡng 100 requests / 5 phút, liên kết trực tiếp vào API Gateway stage `dev`. | 09/07/2026 | 09/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thứ 6**<br>(Day 5) | - **Tối ưu hóa Chi phí & Nghiệm thu luồng E2E:**<br>&emsp; + Thiết lập luật S3 Lifecycle mang tên `Auto-Delete-Raw-Invoices` giới hạn xóa file tạm tự động sau 1 ngày tại tiền tố `uploads/` nhằm giải phóng dung lượng.<br>&emsp; + Kiểm thử toàn diện luồng nghiệp vụ từ Frontend đến Backend. Tổng hợp tài liệu kiến trúc, viết báo cáo tổng kết và chuẩn bị demo Đồ án tốt nghiệp khóa Bootcamp. | 10/07/2026 | 10/07/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được:
* Hệ thống cơ sở dữ liệu trên DynamoDB vận hành ổn định, cấu trúc tổ chức key chuẩn xác phục vụ tốc độ truy xuất siêu tốc (miliseconds) cho các bảng phân tích dữ liệu.
* Giao diện Backend API Gateway hoạt động an toàn tuyệt đối trước các cuộc tấn công DDoS nhỏ lẻ nhờ WAF bảo vệ, đồng thời chặn hoàn toàn các truy cập ẩn danh (chỉ cho phép user chứng thực với Cognito Token đi qua).
* Tối ưu hóa thành công quy trình dọn rác lưu trữ (S3 Lifecycle) và tối đa hóa hiệu năng phân phối tài sản web tĩnh. Đồ án khép lại thành công với hệ thống IDP Serverless hoàn chỉnh.

---
![DynamoDB Tables](/images/1-Worklog/1.12-Week12/week12-1.png)
<p align="center"><i>Hình 1: Cấu trúc 4 bảng dữ liệu được tạo thành công trên dịch vụ cơ sở dữ liệu NoSQL Amazon DynamoDB với Capacity mode On-demand giúp tối ưu chi phí.</i></p>

![API Gateway Methods](/images/1-Worklog/1.12-Week12/week12-2.png)
<p align="center"><i>Hình 2: Triển khai các resources và cấu hình phương thức GET trên Amazon API Gateway tích hợp trực tiếp với các hàm xử lý dữ liệu AWS Lambda.</i></p>

![AWS WAF Rule](/images/1-Worklog/1.12-Week12/week12-3.png)
<p align="center"><i>Hình 3: Thiết lập rào chắn AWS WAF với quy tắc Rate-limiting (BlockSpamIP) nhằm bảo vệ hạ tầng API trước tình trạng spam lượt truy cập ồ ạt từ các địa chỉ IP xấu.</i></p>

![AWS WAF Rule](/images/1-Worklog/1.12-Week12/week12-4.png)
<p align="center"><i>Hình 4: Thiết lập rào chắn AWS WAF với quy tắc Rate-limiting (BlockSpamIP) nhằm bảo vệ hạ tầng API trước tình trạng spam lượt truy cập ồ ạt từ các địa chỉ IP xấu.</i></p>

![Cognito Configuration](/images/1-Worklog/1.12-Week12/week12-5.png)
<p align="center"><i>Hình 5: Thiết lập bộ xác thực Amazon Cognito User Pool Authorizer để chặn các request trái phép, bắt buộc người dùng gửi Authorization Token trước khi gọi API.</i></p>

![Cognito Configuration](/images/1-Worklog/1.12-Week12/week12-6.png)
<p align="center"><i>Hình 6: Thiết lập bộ xác thực Amazon Cognito User Pool Authorizer để chặn các request trái phép, bắt buộc người dùng gửi Authorization Token trước khi gọi API.</i></p>