---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12 </b> "
---

### Mục tiêu tuần 12:
* Tổng hợp và hệ thống hóa lại toàn bộ kiến thức đã học trong 11 tuần vừa qua theo từng cụm chủ đề.
* Củng cố lại các khái niệm nền tảng, CI/CD, SNS, lưu trữ/cơ sở dữ liệu.
* Nhìn lại tổng quan lộ trình học tập và thực hành để chuẩn bị cho giai đoạn tiếp theo.
### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                    | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------- |
| 2   | - Tổng hợp lại kiến thức nền tảng: VPC, IGW, NAT, SG, NACLs, Subnet, Route table                                              | 29/06/2026   | 29/06/2026      |                   |
| 3   | - Tổng hợp lại kiến thức về CI/CD: CodeBuild, CodePipeline, CI/CD trên ECS/EKS, Serverless CI/CD                              | 30/06/2026   | 30/06/2026      |                   |
| 4   | - Tổng hợp lại kiến thức về SNS: cơ chế publish/subscribe, tích hợp thông báo với các dịch vụ khác                            | 01/07/2026   | 01/07/2026      |                   |
| 5   | - Tổng hợp lại kiến thức về lưu trữ và cơ sở dữ liệu: S3, Storage Gateway, RDS, DynamoDB, Backup                              | 02/07/2026   | 02/07/2026      |                   |
| 6   | - Tổng quan lại toàn bộ lộ trình học tập và thực hành từ tuần 1 đến tuần 11                                                   | 03/07/2026   | 03/07/2026      |                   |

### Kết quả đạt được tuần 12:
* **Kiến thức nền tảng:** Hệ thống hóa lại cách các thành phần mạng trong AWS phối hợp với nhau - VPC là ranh giới mạng riêng, IGW/NAT cung cấp kết nối Internet cho subnet công khai/riêng tư, SG và NACLs kiểm soát traffic ở tầng instance và tầng subnet.
* **CI/CD:** Củng cố quy trình CI/CD hoàn chỉnh từ source code (GitLab/GitHub) → build/test (CodeBuild) → triển khai tự động (CodePipeline) lên các nền tảng khác nhau như ECS, EKS và Lambda (Serverless).
* **SNS:** Nắm chắc vai trò của SNS như một dịch vụ nhắn tin publish/subscribe, dùng để gửi thông báo và kết nối các thành phần trong kiến trúc hướng sự kiện (event-driven).
* **Lưu trữ và cơ sở dữ liệu:** Tổng hợp lại sự khác biệt và trường hợp sử dụng của các dịch vụ lưu trữ (S3, Storage Gateway) và cơ sở dữ liệu (RDS cho quan hệ, DynamoDB cho NoSQL), cùng với chiến lược sao lưu bằng AWS Backup.
* **Tổng quan:** Nhìn lại toàn bộ hành trình 11 tuần, từ việc làm quen tài khoản AWS, hạ tầng mạng cơ bản, bảo mật (IAM, KMS), cơ sở dữ liệu, đến CI/CD và hạ tầng dưới dạng code (CDK). Xác định được các mảng kiến thức cần rèn luyện thêm để chuẩn bị cho các nội dung tiếp theo.
* ...

