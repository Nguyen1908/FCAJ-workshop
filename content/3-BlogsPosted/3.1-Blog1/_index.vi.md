---
title: "Blog 1"
date: 2026-06-16
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

# TỪ CACHE THEO GIỜ ĐẾN REAL-TIME PRICING: SAMSUNG GIẢI QUYẾT BÀI TOÁN ĐỒNG BỘ GIÁ VỚI AWS LAMBDA RESPONSE STREAMING

Trong thương mại điện tử, giá sản phẩm luôn là dữ liệu nhạy cảm bậc nhất — chỉ cần giá trên trang sản phẩm lệch với giá lúc thanh toán, trải nghiệm khách hàng đã bị ảnh hưởng nghiêm trọng. Samsung.com, kênh bán hàng trực tiếp của Samsung, gần đây đã thay đổi hoàn toàn cách hiển thị giá bằng AWS Lambda Response Streaming kết hợp Amazon CloudFront.

Các điểm chính cần nắm:

* Kiến trúc cũ dùng một lớp Data Aggregation với Cron Job chạy mỗi giờ để tính trước toàn bộ tổ hợp giá (màu sắc, dung lượng, khuyến mãi, khu vực...) rồi lưu vào cache.
* Vấn đề "Permutation Explosion": với 30+ SKU nhân với nhiều biến thể, số tổ hợp cần tính trước tăng theo cấp số nhân, tốn tài nguyên cho dữ liệu có thể không ai truy cập.
* Vấn đề "Synchronization Lag": vì Cron Job chỉ chạy mỗi giờ, cache có thể trễ tới 60 phút so với giá thực tế — một Flash Sale bắt đầu lúc 10:05 vẫn hiển thị giá cũ tới 11:00.
* Giải pháp mới: loại bỏ hoàn toàn tầng Data Aggregation, luôn lấy dữ liệu trực tiếp từ Pricing Engine (Source of Truth) tại thời điểm người dùng yêu cầu.
* Quy trình mới: CloudFront kiểm tra Edge Cache → nếu miss thì gọi Lambda → Lambda fan-out song song nhiều request tới Pricing Engine → kết quả được stream trả về ngay khi có dữ liệu → CloudFront cache lại trong thời gian ngắn.
* Lambda Response Streaming giúp giảm Time To First Byte (TTFB) vì dữ liệu được gửi về ngay khi sẵn sàng, thay vì phải đợi xử lý xong toàn bộ rồi mới trả response.
* Các dịch vụ AWS chính: Amazon CloudFront, AWS Lambda, Lambda Response Streaming, Lambda Function URL, Provisioned Concurrency.

Bài học lớn nhất từ case study này không nằm ở công nghệ Lambda Response Streaming, mà ở tư duy kiến trúc: cache thường được xem là giải pháp cho vấn đề hiệu năng, nhưng với các hệ thống mà tính chính xác dữ liệu (như giá bán) quan trọng hơn tốc độ, cache đôi khi lại chính là nguyên nhân gây lỗi nghiệp vụ. Đôi khi một kiến trúc đơn giản hơn, bám sát Source of Truth, lại mang hiệu quả tốt hơn nhiều tầng cache trung gian.

...Hình ảnh...![alt text](/images/3-BlogsPosted/blog1_image.png)![alt text](/images/3-BlogsPosted/blog1_image-1.png)

Bài viết gốc: https://aws.amazon.com/vi/blogs/architecture/how-samsung-achieved-real-time-pricing-with-aws-lambda-response-streaming/