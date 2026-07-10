---
title: "AWS First Cloud AI Journey Community Day"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch “AWS First Cloud AI Journey Community Day”

### Mục Đích Của Sự Kiện

- **Khám phá giới hạn của GenAI:** Đi sâu vào bản chất kỹ thuật của các mô hình ngôn ngữ lớn (LLM), từ việc xử lý tính bất định (Non-determinism) đến cách xây dựng hệ thống đa tác nhân (Multi-Agent) cấp doanh nghiệp.
- **Làm chủ hạ tầng AWS:** Cập nhật các chiến lược tối ưu chi phí, tăng cường bảo mật từ vùng biên (Edge) đến máy chủ gốc (Origin), và cách tự động hóa kiểm toán bảo mật.
- **Tư duy xây dựng sản phẩm:** Lắng nghe bài học xương máu từ các dự án thực tế và quá trình "chạy nước rút" tại các cuộc thi Hackathon để biến ý tưởng thô thành ứng dụng hoàn chỉnh.

---

### Tóm Tắt Nội Dung Cốt Lõi

#### 1. Hệ Thống Multi-Agent Cấp Doanh Nghiệp: Bài Toán Chấm Điểm Tín Dụng Startup
- **Diễn giả:** Vy Lam - Senior Business Systems Analyst, VPBank
- **Nỗi đau thực tế:** Startup thường bị các mô hình tín dụng truyền thống "ngó lơ" vì thiếu dữ liệu tài chính lịch sử và dòng tiền chưa ổn định. 
- **Giải pháp chuyển đổi:** Dịch chuyển từ Single Agent (dễ gặp rào cản về giới hạn ngữ cảnh và thiếu kiểm tra chéo) sang kiến trúc **Multi-Agent**. Hệ thống này mô phỏng một "Hội đồng tín dụng ảo" với các vai trò độc lập: *Financial Analyst, Market Analyst, Team Evaluator, Risk Assessor* và *Compliance*.
- **Kết quả:** Đảm bảo tính minh bạch nhờ xử lý song song, giảm tới 95% cả về thời gian lẫn chi phí cho mỗi quyết định cấp vốn mà vẫn giữ vững hàng rào bảo mật.

#### 2. Giải Mã Tính "Bất Định" Của LLM
- **Diễn giả:** Duc Dao - Solution Architect, Cloud Kinetics
- **Cú lừa về Temperature = 0:** Giới kỹ sư thường mặc định set **Temperature = 0** thì AI sẽ trả về kết quả cố định. Thực tế, độ sai lệch vẫn có thể lên tới 15%.
- **Góc nhìn kỹ thuật:** Do các phép toán dấu phẩy động trên GPU xử lý song song không có tính kết hợp hoàn toàn, những sai số làm tròn cực nhỏ trong *logit* có thể làm lật lọng kết quả của hàm *argmax*.
- **Chiến lược sinh tồn:** Chấp nhận bản chất xác suất của LLM. Thay vì ép AI, hãy dùng cấu trúc đầu ra ép buộc (*JSON mode/Constrained outputs*). Cài đặt lý tưởng là **Temperature = 0.1** để giữ tính ổn định nhưng không bị rơi vào lỗi lặp từ vô tận.

#### 3. 36 Giờ Sinh Tử Tại Lotus Hacks 2026: Dự án UTMorpho
- **Diễn giả:** Team VIB
- **Hành trình:** 36 tiếng không ngủ để build UTMorpho – công cụ Sketch2App dùng Claude Vision chuyển bản phác thảo thành code React/Tailwind.
- **Khủng hoảng gặp phải:** Đụng trần giới hạn Token API của Claude, mắc kẹt trong "Scope Creep" (tham lam nhồi nhét tính năng) và ác mộng AI sinh code rác gây bug diện rộng.
- **Kinh nghiệm chốt hạ:** Trong Hackathon hay dự án thực tế, ý tưởng ngon nhất sinh ra từ bế tắc. Sự đồng bộ (Team Sync) là chìa khóa sống còn, và luật bất thành văn là: Hãy làm cho giá trị cốt lõi chạy được trước khi nghĩ đến những thứ màu mè.

#### 4. Từ Vùng Biên Đến Máy Chủ Gốc: Tối Ưu Với CloudFront
- **Diễn giả:** Nguyen Tuan Thinh - DevOps Engineer
- **Bài toán:** Nỗi ám ảnh về chi phí hạ tầng mạng phình to khi có traffic "đột biến" hoặc bị tấn công DDoS.
- **Vũ khí CloudFront:** Sở hữu hơn 700+ PoPs toàn cầu, CloudFront chặn đứng DDoS từ xa qua AWS Shield và WAF. 
- **Bí kíp tối ưu:** - Miễn phí hoàn toàn chi phí truyền tải (*DTO*) từ AWS Origins.
  - Sử dụng *Origin Access Control (OAC)* để "tàng hình" máy chủ gốc khỏi mạng public.
  - Khai thác mạnh mẽ *Mutual TLS (mTLS)* và *Lambda@Edge* để tính toán trực tiếp tại vùng biên.

#### 5. Context Is Everything: Để AI Thực Sự "Làm Việc" Cho Bạn
- **Diễn giả:** Tinh Truong - Platform Engineer, GoTymeX
- **Gốc rễ vấn đề:** AI trả lời ngớ ngẩn đa phần không phải do mô hình dở, mà do Context (Ngữ cảnh) bị nhiễu. Hội chứng "Internet Puller" – ném mọi tài liệu hầm bà lằng vào prompt – chỉ tổ làm tốn tiền token và giảm độ chính xác.
- **Tư duy thiết kế AI:** Một hệ thống tốt phải có mục tiêu rõ ràng và ràng buộc khắt khe (về format, công nghệ, tiêu chí thành công). Tương lai của AI không nằm ở những câu prompt rời rạc, mà là xây dựng "Second AI Brain" (Hệ thống ngữ cảnh có bộ nhớ) để cá nhân hóa hiệu quả dài hạn.

#### 6. Trợ Lý AI Thân Thiện Với Amazon Q
- **Diễn giả:** Pham Ng Hai Anh - G-AsiaPacific Vietnam, AWS Community Builder
- **Use Case:** Dùng Amazon Q làm PM Assistant để xử lý mớ công việc giấy tờ nhàm chán: tự tạo biên bản họp (MoM), gửi email chốt việc và lên lịch.
- **Điểm sáng Enterprise:** Sức mạnh nằm ở khả năng cắm trực tiếp vào 40+ nguồn dữ liệu doanh nghiệp, tuân thủ chặt chẽ RBAC và Guardrails. Ngoài ra, việc dùng GenAI để tự tự động hóa kiểm toán bảo mật hạ tầng (*Auto Audit*) mở ra hướng đi cực kỳ hứa hẹn cho các hệ thống Cloud.

---

### Bài Học Nhìn Nhận & Ứng Dụng Thực Tế

Hội thảo không chỉ là những bài trình bày lý thuyết mà thực sự đã cung cấp cho mình một "toolkit" (bộ công cụ) tư duy để áp dụng trực tiếp vào quá trình phát triển các dự án backend hiện tại:

1. **Chuẩn hóa đầu ra hệ thống AI:** Sẽ không còn cố chấp với việc đưa **Temperature về 0**. Thay vào đó, áp dụng triệt để *JSON mode* kết hợp với cơ chế *Retry* (thử lại) để đảm bảo dữ liệu thô trả về luôn chuẩn cấu trúc. Điều này cực kỳ quan trọng khi xử lý các luồng dữ liệu thời gian thực cho hệ thống dự báo doanh thu, giúp các hàm Lambda phía sau không bị gãy (crash) do parse lỗi.
2. **Bảo mật và tối ưu luồng dữ liệu:** Áp dụng bài học từ anh Thịnh để cấu hình *CloudFront* làm lá chắn thép. Việc dùng *OAC* ẩn đi các bucket S3 và các endpoint nhạy cảm khỏi internet công cộng sẽ giúp kiến trúc hạ tầng kín kẽ và chuyên nghiệp hơn rất nhiều.
3. **Quản trị Ngữ cảnh (Context Management):** Thay vì nạp bừa bãi dữ liệu, mình học được cách tinh lọc và chỉ truyền những tham số, lịch sử dữ liệu thực sự mang tính quyết định vào các mô hình (như Amazon Forecast hay LLMs) để tối ưu chi phí tính toán và tăng độ chính xác.
4. **Mindset "Làm sản phẩm":** Bài học từ Team VIB nhắc nhở mình về sự tập trung. Dù làm module nhỏ hay kiến trúc lớn, phải ưu tiên hoàn thiện luồng core (giá trị cốt lõi) chạy trơn tru từ A-Z trước khi nghĩ đến việc scale up hay vẽ vời tính năng phụ.

> **Tổng kết:** Sự kiện giúp mình thoát khỏi góc nhìn thuần "viết code", chuyển sang tư duy của một kỹ sư xây dựng hệ thống: kết nối các dịch vụ Cloud lại với nhau một cách an toàn, tiết kiệm chi phí, và luôn có phương án dự phòng cho sự "bất định" của các công nghệ AI thời đại mới.

#### Một số hình ảnh khi tham gia sự kiện
![](images/4-EventParticipated/4.1-Event1/event.png)