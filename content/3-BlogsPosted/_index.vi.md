---
title: "Các bài blogs đã đăng"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

### [Blog 1 - Từ Cache Theo Giờ Đến Real-Time Pricing: Samsung Giải Quyết Bài Toán Đồng Bộ Giá Với AWS Lambda Response Streaming](3.1-Blog1/)
Blog này giới thiệu cách Samsung.com loại bỏ tầng cache trung gian chạy theo giờ (vốn gây ra vấn đề permutation explosion và synchronization lag) để chuyển sang mô hình lấy giá real-time trực tiếp từ Pricing Engine, nhờ kết hợp Amazon CloudFront và AWS Lambda Response Streaming. Đây là một case study hay về việc ưu tiên tính chính xác dữ liệu hơn là chỉ tối ưu hiệu năng bằng cache.

### [Blog 2 - Xây Dựng RAG Đa Phòng Ban Với Amazon Bedrock Knowledge Bases Và Fine-Grained Access Control](3.2-Blog2/)
Blog này giới thiệu cách xây dựng hệ thống RAG nội bộ doanh nghiệp trên Amazon Bedrock Knowledge Bases, cho phép nhiều phòng ban (Finance, Engineering, Executive...) cùng dùng chung một Knowledge Base nhưng vẫn đảm bảo phân quyền chi tiết tới từng tài liệu nhờ kết hợp Amazon Cognito, Lambda Authorizer và Amazon Verified Permissions.

### [Blog 3 - Amazon Cognito Có Thể Đăng Nhập Không Cần OTP SMS?](3.3-Blog3/)
Blog này giới thiệu giải pháp kết hợp Amazon Cognito CUSTOM_AUTH với các API của Vonage (Identity Insights, Silent Authentication, Fraud Defender) để giảm gian lận OTP SMS và cho phép người dùng đăng nhập gần như không cần nhập mã OTP, dựa trên đánh giá rủi ro theo thời gian thực.