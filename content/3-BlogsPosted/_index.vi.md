---
title: "Các bài Blog đã đăng"
date: 2026-07-30
weight: 3
chapter: false
pre: " <b> 3. </b> "
---


Phần này sẽ liệt kê và giới thiệu các bài blogs mà bạn đã đăng lên [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj).

### [Blog 1 - BÀI TOÁN CẠN KIỆT KẾT NỐI GIỮA AWS LAMBDA VÀ AMAZON RDS](3.1-Blog1/)
Bài viết này mổ xẻ chi tiết về "cơn ác mộng" cạn kiệt kết nối (Connection Exhaustion) khi ghép nối kiến trúc phi máy chủ (Serverless) của AWS Lambda với cơ sở dữ liệu quan hệ Amazon RDS. Qua đó, mình phân tích cách Amazon RDS Proxy đóng vai trò như một màng lọc trung gian (Multiplexing) để hóa giải triệt để nút thắt này, giúp hệ thống tha hồ mở rộng linh hoạt mà Database vẫn sống khỏe và an toàn.

### [Blog 2 - BẢO MẬT TRONG PHÁT TRIỂN PHẦN MỀM: KHÔNG CHỈ LÀ VIẾT CODE AN TOÀN](3.2-Blog2/)
Một ứng dụng chạy mượt mà chưa chắc đã an toàn một khi đã "phơi mình" ra Internet. Bài blog này là bản tóm tắt những nguyên tắc sống còn về bảo mật trên AWS: từ việc tuyệt đối không hardcode Access Key, áp dụng quyền tối thiểu (Least Privilege), quy hoạch mạng Public/Private Subnet hợp lý, cho đến cách dùng các dịch vụ như AWS WAF, Amazon GuardDuty hay Inspector để giám sát và bảo vệ hệ thống liên tục.

### [Blog 3 - QUẢN LÝ HẠ TẦNG VỚI TERRAFORM – KHÔNG CHỈ LÀ CLICK ON THE CONSOLE](3.3-Blog3/)
Bài viết chia sẻ hành trình từ bỏ thói quen click chuột thủ công (ClickOps) trên AWS Console để chuyển sang tư duy quản lý toàn bộ hạ tầng bằng mã nguồn (Infrastructure as Code) với Terraform. Mình đúc kết các giá trị cốt lõi như tính năng Plan/Apply giúp tránh rủi ro trên Production, cách quản lý file State an toàn bằng S3 kết hợp DynamoDB, cùng khả năng tái sử dụng cấu trúc linh hoạt thông qua Modules.
