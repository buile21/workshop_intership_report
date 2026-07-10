---
title: "Game Show: Cloud Architect"
date: 2026-06-20
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch Event: “Cloud Architect Game Show”

### Mục Đích Của Sự Kiện

- **Kiểm tra kiến thức "thực chiến":** Đưa những lý thuyết khô khan về Cloud và thiết kế kiến trúc hệ thống (Architecture Design) vào một môi trường áp lực cao, đòi hỏi người chơi phải nảy số nhanh và chính xác.
- **Rèn luyện kỹ năng ra quyết định (Decision Making):** Thông qua việc sử dụng các "quyền trợ giúp" chiến thuật, thực tập sinh học cách đánh giá rủi ro (Risk Assessment) trong các tình huống không chắc chắn.
- **Gắn kết và phá vỡ rào cản (Networking):** Tạo cơ hội giao lưu chéo bằng cách ghép đội ngẫu nhiên giữa các nhóm thực tập sinh khác nhau, rèn luyện kỹ năng làm việc nhóm nhanh (Agile Teamwork).

---

### Tóm Tắt Thể Thức & Luật Chơi

Không giống như các buổi hội thảo một chiều, sự kiện lần này là một đấu trường trí tuệ đối kháng trực tiếp cực kỳ gay cấn:

#### 1. Quy Mô & Thể Thức Đối Kháng
- **Đội hình:** Tổng cộng có 8 đội tham gia, mỗi đội gồm đúng 5 thành viên (khuyến khích ghép đội đa dạng, không giới hạn trong cùng một dự án nội bộ và đặc biệt là "cấm cửa" các chuyên gia gạo cội để đảm bảo tính công bằng).
- **Vòng đấu:** Hai đội đối đầu trực tiếp (1vs1), lần lượt giải quyết bộ đề từ dễ đến khó. Đội có điểm số cao hơn sẽ giành vé đi tiếp vào vòng trong.

#### 2. Luật Tie-break (Bàn Thắng Vàng)
- Trong trường hợp bất phân thắng bại sau các câu hỏi chính thức, hai đội sẽ bước vào **câu hỏi sinh tử số 11**. 
- Luật chơi chuyển sang dạng "Fastest Finger" – đội nào chốt đáp án nhanh và chính xác hơn sẽ lập tức giành chiến thắng chung cuộc.

#### 3. Cơ Chế Chiến Thuật (Power-ups)
Điểm nhấn của Game Show nằm ở việc quản trị rủi ro thông qua 2 kỹ năng đặc biệt (mỗi đội chỉ được dùng 1 lần duy nhất):
- **Rủi ro tối thiểu (Phòng ngự):** Kích hoạt khi team gặp câu hỏi "khoai" và không tự tin. Nếu trả lời sai, đội được bảo toàn điểm số. Nếu đúng, đội chỉ nhận 50% số điểm. Đây là bài toán đánh đổi an toàn.
- **Ngôi sao hi vọng (Tấn công):** Kích hoạt ở câu hỏi tủ. Trả lời đúng nhận điểm nhân đôi (x2), nhưng nếu sai sẽ bị trừ gấp đôi số điểm. Một nước đi "Được ăn cả, ngã về không".

---

### Bài Học Nhìn Nhận & Ứng Dụng Thực Tế

Trải nghiệm "não nảy số" dưới áp lực thời gian của Game Show mang lại những góc nhìn rất tương đồng với công việc thực tế của một Backend Developer khi xử lý hệ thống:

1. **Tư duy quản trị rủi ro (Risk Management):** Việc sử dụng *Ngôi sao hi vọng* hay *Rủi ro tối thiểu* giống hệt với việc đưa ra quyết định khi vận hành hệ thống thực tế. Khi thiết kế kiến trúc Backend cho bài toán dự báo, nếu không nắm chắc tải của hệ thống, ta phải chọn phương án an toàn (phân bổ tài nguyên hợp lý) thay vì "all-in" gây lãng phí chi phí Cloud hoặc sập server.
2. **Kỹ năng xử lý sự cố (Incident Response):** Việc 5 cái đầu phải thảo luận tốc độ cao, thống nhất đáp án trong vài chục giây rất giống với cảm giác cùng team "chữa cháy" (debug/hotfix) khi hệ thống gặp lỗi trên môi trường Production. Giao tiếp phải cực kỳ gãy gọn và tin tưởng vào chuyên môn của đồng đội.
3. **Lấp đầy lỗ hổng kiến thức:** Những câu hỏi từ khó đến cực khó về Cloud Architecture đã phơi bày những lỗ hổng lý thuyết mà mình chưa nắm vững. Nhờ đó, mình biết chính xác cần phải đọc thêm Document nào của AWS để tối ưu hóa trực tiếp cho hạ tầng của dự án hiện tại.
4. **Sức mạnh của Team đa nhiệm:** Việc ghép team với các bạn ở những mảng khác nhau giúp mình nhận ra một hệ thống hoàn hảo cần góc nhìn đa chiều (từ Network, Security, đến Database optimization), chứ không chỉ thuần túy là viết logic code.

> **Tổng kết:** "Cloud Architect" không chỉ là một sân chơi giải trí sau những giờ code căng thẳng, mà còn là một bài test thực tế về kiến thức nền tảng và bản lĩnh tâm lý. Sự kiện đã giúp mình gắn kết thêm với các anh em thực tập sinh khác và thu về một danh sách dài những kiến thức Cloud cần phải đào sâu hơn nữa.

#### Một số hình ảnh khi tham gia sự kiện
![](/images/4-EventParticipated/4.2-Event2/event.png)