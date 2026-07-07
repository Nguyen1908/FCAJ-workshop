---
title: "Blog 2"
date: 2026-06-20
weight : 1
chapter : false
pre : " <b> 3.2 </b> "
---

# AMAZON COGNITO CÓ THỂ ĐĂNG NHẬP KHÔNG CẦN OTP SMS?

Rất nhiều hệ thống vẫn dùng mô hình đăng nhập: nhập số điện thoại → nhận OTP → nhập OTP → đăng nhập. Nhưng mô hình này tồn tại nhiều rủi ro như SIM Swap Attack, SMS Interception, Social Engineering, SMS Pumping Fraud, cùng với việc người dùng nhập sai hoặc không nhận được OTP. Amazon Cognito kết hợp với Vonage đưa ra một hướng giải quyết khác: xác thực gần như không cần người dùng nhập mã OTP.

Các điểm chính cần nắm:

* Theo số liệu được AWS trích dẫn, khoảng 20% người dùng bỏ cuộc ngay tại bước xác thực OTP, trong khi tấn công chiếm đoạt tài khoản (Account Takeover) đang tăng mạnh.
* Giải pháp dùng Amazon Cognito CUSTOM_AUTH kết hợp API của Vonage, với kiến trúc gồm Amazon CloudFront, AWS WAF, Amazon API Gateway, Amazon Cognito, AWS Lambda, Vonage Identity Insights, Vonage Verify và Mobile Network Operator.
* Ba lớp bảo vệ chính:
  1. **Identity Insights**: kiểm tra SIM vừa đổi gần đây, số điện thoại có hợp lệ không, có dấu hiệu giả mạo không — nếu rủi ro cao sẽ block hoặc yêu cầu xác thực bổ sung.
  2. **Silent Authentication**: thay vì gửi OTP để người dùng nhập, hệ thống xác minh trực tiếp với nhà mạng, hoàn thành trong vài giây mà người dùng không cần đọc, sao chép hay nhập mã.
  3. **Fraud Defender**: chống SMS Pumping và gian lận OTP quy mô lớn, giúp giảm chi phí gửi SMS không cần thiết.
* Luồng đăng nhập thực tế: người dùng nhập số điện thoại → Cognito kích hoạt CUSTOM_AUTH → Lambda gọi Vonage Identity Insights → hệ thống đánh giá rủi ro → nếu an toàn thì Silent Authentication được kích hoạt → nhà mạng xác minh SIM → Cognito phát hành JWT → đăng nhập thành công, toàn bộ có thể hoàn tất trong dưới 5 giây.
* Bài học kiến trúc quan trọng nhất không nằm ở Vonage mà ở cách Amazon Cognito được mở rộng: thông qua CUSTOM_AUTH và Lambda Trigger, Cognito có thể hỗ trợ Passwordless Login, Risk-Based Authentication, Adaptive Authentication, MFA tùy chỉnh và tích hợp dịch vụ xác thực bên thứ ba — biến Cognito thành một nền tảng CIAM mạnh hơn nhiều so với dịch vụ đăng nhập thông thường.

Đây là một hướng tiếp cận đáng tham khảo: thay vì bắt mọi người nhập OTP cho mọi phiên đăng nhập, hệ thống đánh giá rủi ro theo thời gian thực và chỉ yêu cầu xác thực bổ sung khi thực sự cần thiết — đặc biệt phù hợp với các ứng dụng tài chính, thương mại điện tử và nền tảng mobile-first trên AWS.

...Hình ảnh...![alt text](/images/3-BlogsPosted/blog2_image.png)![alt text](/images/3-BlogsPosted/blog2_image-1.png)

Bài viết gốc: https://aws.amazon.com/vi/blogs/architecture/reducing-sms-otp-fraud-with-vonage-network-powered-solutions-and-amazon-cognito/