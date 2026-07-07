---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Báo cáo trải nghiệm tại AWS Community Day 2026

## Mục tiêu của chương trình

AWS Community Day 2026 là ngày hội cộng đồng công nghệ, quy tụ các lập trình viên, kiến trúc sư hệ thống, sinh viên và những ai đam mê Cloud & AI. Sự kiện mang đến không gian để các chuyên gia trong ngành trao đổi những bài học thực chiến xoay quanh phát triển ứng dụng, AI tạo sinh, Machine Learning, kiến trúc Cloud và DevOps.

Người tham dự nhận được:

- Góc nhìn cập nhật về các xu hướng AI và AWS Cloud mới nhất.
- Bài học triển khai thực tế được đúc kết từ chính các diễn giả.
- Cơ hội kết nối, mở rộng mạng lưới trong cộng đồng AWS tại Việt Nam.
- Nền tảng kiến thức để vận dụng vào công việc và các dự án riêng.

---

# Tổng hợp các phiên trình bày

## Phiên 1 - Context Is Everything: Making AI Actually Work for You

**Diễn giả:** Anh Tịnh - Platform Engineer, GoTymeX

### Điểm nhấn nội dung

- AI dù mạnh nhưng vẫn dễ "trật hướng" nếu thiếu **ngữ cảnh (context)**.
- Ý tưởng xây dựng "Bộ não thứ hai" giúp AI lưu giữ thông tin lâu dài thay vì phải nhập lại prompt mỗi lần.
- Vai trò của việc quản lý tri thức trong việc nâng hiệu quả hỗ trợ của AI.
- Những trải nghiệm thực tế khi ứng dụng AI trong môi trường công ty.

### Bài học rút ra

- Prompt chỉ là điểm khởi đầu, **context mới thực sự quyết định chất lượng câu trả lời**.
- Cách sắp xếp, tổ chức dữ liệu để AI phản hồi chính xác hơn.
- Xây dựng quy trình làm việc song hành cùng AI, không chỉ dừng ở hỏi - đáp đơn thuần.

---

## Phiên 2 - Friendly AI Assistant with Amazon Q

**Diễn giả:** Hải Anh - AWS Community Builder

### Điểm nhấn nội dung

- Tổng quan về công cụ Amazon Q.
- Trình diễn trực tiếp trợ lý AI hỗ trợ quá trình viết code.
- Cách lồng ghép AI vào chu trình phát triển phần mềm.
- Những ví dụ ứng dụng thực tế trong doanh nghiệp.

### Bài học rút ra

- Amazon Q có thể đảm nhiệm:
  - Tạo mã nguồn.
  - Diễn giải logic của code.
  - Tái cấu trúc (refactor) code.
  - Rà soát, đánh giá code.
  - Soạn tài liệu kỹ thuật.
- Nhận thấy rõ hơn cách AI góp phần tăng tốc độ và năng suất lập trình.

---

## Phiên 3 - From Edge To Origin: CloudFront as Your Foundation

**Diễn giả:** Nguyễn Tuấn Thịnh

### Điểm nhấn nội dung

- Cấu trúc tổng thể của CloudFront.
- Nguyên lý vận hành của mạng CDN.
- Các chiến lược cache dữ liệu.
- Khái niệm Origin Shield.
- Cơ chế bảo mật tích hợp trong CloudFront.
- Những kinh nghiệm nên áp dụng khi triển khai thực tế.

### Bài học rút ra

- Nắm được bản chất hoạt động của CDN.
- Biết cách cải thiện tốc độ truy cập website.
- Tối ưu được chi phí băng thông truyền tải dữ liệu.
- Củng cố thêm lớp bảo mật cho hệ thống.

---

## Phiên 4 - 36 Hours with LotusHacks: Building UTMorpho from Idea to Reality

**Diễn giả:** Đội VIB

### Điểm nhấn nội dung

- Câu chuyện tham gia cuộc thi Hackathon.
- Chặng đường từ ý tưởng ban đầu đến sản phẩm hoàn thiện.
- Cách tổ chức làm việc nhóm trong khung thời gian 36 giờ.
- Phần trình diễn sản phẩm UTMorpho.
- Những trở ngại gặp phải trong lúc xây dựng sản phẩm.

### Bài học rút ra

- Kỹ năng phân bổ thời gian hợp lý khi tham gia Hackathon.
- Duy trì tinh thần đồng đội dưới áp lực lớn.
- Biến ý tưởng thô thành sản phẩm khả thi.
- Kinh nghiệm thuyết trình, pitching trước ban giám khảo.

---

## Phiên 5 - Deep Dive: How LLM Actually Works

**Diễn giả:** Đào Đức - Solution Architect

### Điểm nhấn nội dung

- Cơ chế vận hành bên trong của các mô hình ngôn ngữ lớn (LLM).
- Lý do khiến kết quả của LLM mang tính không ổn định.
- Tham số Temperature.
- Tham số Top-k.
- Tham số Top-p.
- Kỹ thuật Sampling.
- Các cách tiếp cận để giảm thiểu sai lệch trong kết quả sinh ra.

### Bài học rút ra

- Hiểu quy trình sinh từng token của LLM.
- Lý giải được vì sao một prompt giống nhau có thể cho ra nhiều đáp án khác nhau.
- Biết cách điều chỉnh tham số để kết quả AI ổn định hơn.

---

## Phiên 6 - Enterprise-Grade Multi-Agent System

**Diễn giả:** Vy Lâm - Senior Business Systems Analyst, VPBank

### Điểm nhấn nội dung

- Kiến trúc hệ thống đa tác nhân (Multi-Agent).
- Vai trò của AI Agent trong bối cảnh doanh nghiệp.
- Các cơ chế Guardrails.
- Yếu tố tuân thủ (Compliance).
- Vấn đề bảo mật.
- Bài toán ROI khi đưa AI vào vận hành.
- Case Study về hệ thống chấm điểm tín dụng cho Startup.

### Bài học rút ra

- Phân biệt rõ giữa mô hình Single Agent và Multi-Agent.
- Cách thiết kế hệ thống AI có khả năng mở rộng linh hoạt.
- Ứng dụng Guardrails để đảm bảo an toàn khi vận hành.
- Tư duy xây dựng giải pháp AI phục vụ quy mô doanh nghiệp.

---

# Đúc kết sau sự kiện

Sau khi tham dự AWS Community Day 2026, em đã tiếp thu thêm nhiều kiến thức mới xoay quanh Cloud Computing và AI tạo sinh. Mỗi phiên chia sẻ đều mang lại góc nhìn thực tiễn từ những người đang trực tiếp làm việc trong ngành, giúp em hình dung rõ hơn cách các công nghệ hiện đại được đưa vào quy trình phát triển phần mềm thực tế.

Một số điểm kiến thức đáng chú ý em tích lũy được:

- Nhận thức rõ vai trò then chốt của **context** khi làm việc cùng AI.
- Biết cách tận dụng Amazon Q để hỗ trợ công việc lập trình.
- Hiểu sâu hơn về kiến trúc CDN và dịch vụ CloudFront.
- Có thêm trải nghiệm về quy trình xây dựng sản phẩm trong môi trường Hackathon.
- Nắm được nguyên lý vận hành của các mô hình ngôn ngữ lớn.
- Hiểu được kiến trúc Multi-Agent áp dụng cho hệ thống AI quy mô lớn.
- Tích lũy nhiều kinh nghiệm quý từ diễn giả và cộng đồng AWS.

---

# Kế hoạch áp dụng vào dự án cá nhân

Từ những gì thu nhận được, em dự định áp dụng vào đồ án và các dự án riêng theo các hướng sau:

- Vận dụng CloudFront khi đưa website lên triển khai trên nền tảng AWS.
- Kết hợp kỹ thuật Prompt Engineering cùng việc quản lý context để xây dựng chatbot.

---