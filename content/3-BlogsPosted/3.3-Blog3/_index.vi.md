---
title: "Blog 3"
date: 2026-06-23
weight : 1
chapter : false
pre : " <b> 3.3 </b> "
---

# XÂY DỰNG RAG ĐA PHÒNG BAN VỚI AMAZON BEDROCK KNOWLEDGE BASES VÀ FINE-GRAINED ACCESS CONTROL

Khi triển khai AI Assistant nội bộ bằng RAG (Retrieval-Augmented Generation) cho doanh nghiệp có nhiều phòng ban (Finance, Engineering, Executive...), một bài toán lớn xuất hiện: làm sao để AI trả lời đúng thông tin nhưng không làm lộ dữ liệu giữa các phòng ban, khi mỗi bộ phận có tài liệu nhạy cảm riêng như báo cáo tài chính, tài liệu kiến trúc hệ thống hay kế hoạch M&A.

Các điểm chính cần nắm:

* Ingestion Pipeline theo hướng event-driven: tài liệu upload lên Amazon S3 → phát sự kiện qua Amazon EventBridge → đẩy vào Amazon SQS → AWS Lambda xử lý và gắn metadata → EventBridge Schedule kích hoạt Lambda Ingest định kỳ đưa dữ liệu vào Amazon Bedrock Knowledge Bases, với embedding lưu trong Amazon S3 Vectors.
* Toàn bộ pipeline ingestion được thiết kế serverless, giúp giảm chi phí vận hành so với việc duy trì hạ tầng cố định.
* Kiến trúc truy vấn: người dùng qua Amazon CloudFront → xác thực bằng Amazon Cognito → được bảo vệ bởi AWS WAF → request vào Amazon API Gateway → Lambda Authorizer kiểm tra quyền → Amazon Verified Permissions đánh giá chính sách phân quyền → Lambda Middleware xử lý nghiệp vụ → Amazon Bedrock Knowledge Bases thực hiện truy vấn và trả kết quả.
* Điểm nổi bật nhất là Fine-Grained Access Control: kết hợp Amazon Cognito, Lambda Authorizer và Amazon Verified Permissions để kiểm tra không chỉ "user có đăng nhập không" mà còn "user thuộc phòng ban nào", "có được xem tài liệu này không", "có được truy vấn dữ liệu này không".
* Bài học chính: khi xây GenAI cho doanh nghiệp, phần khó nhất không phải là LLM hay prompt engineering, mà là quản lý dữ liệu, metadata, phân quyền truy cập và bảo mật thông tin nội bộ.

Đây là một case study đáng tham khảo cho các tổ chức muốn triển khai RAG production-ready ở quy mô nhiều phòng ban, đặc biệt là cách kết hợp Amazon Bedrock Knowledge Bases với Amazon Verified Permissions để vừa mở rộng tốt vừa đảm bảo bảo mật dữ liệu chặt chẽ.

...Hình ảnh...![alt text](blog3_image.png)![alt text](blog3_image-1.png)![alt text](blog3_image-2.png)

Bài viết gốc: https://aws.amazon.com/vi/blogs/architecture/secure-multi-tenant-rag-with-amazon-bedrock-and-verified-permissions/
