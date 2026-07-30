---
title: "[FCAJ2026] Những lỗi thường gặp khi triển khai ứng dụng và cách AWS giúp xử lý"
date: 2026-07-30
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# NHỮNG LỖI THƯỜNG GẶP KHI TRIỂN KHAI ỨNG DỤNG VÀ CÁCH AWS GIÚP XỬ LÝ

[Link blog 3](https://www.facebook.com/share/p/18aas3Dc43/)

Sau khi tìm hiểu về việc triển khai ứng dụng lên AWS, nhóm mình nhận ra rằng viết được một ứng dụng chỉ là bước đầu. Thực tế, quá trình vận hành mới là nơi phát sinh nhiều vấn đề nhất. Một ứng dụng có thể chạy hoàn hảo trên máy cá nhân, nhưng khi đưa lên Cloud lại gặp rất nhiều lỗi khiến người dùng không thể truy cập. Dưới đây là một số tình huống phổ biến chúng mình tìm hiểu được trong quá trình học AWS.

Các điểm chính cần nắm:

* Không thể truy cập website: Đây là lỗi phổ biến nhất, thường xuất hiện dưới dạng thông báo "This site can't be reached" hoặc timeout. Nguyên nhân có thể do EC2 chưa khởi động, sai địa chỉ IP, hoặc Security Group cấu hình thiếu cổng (ví dụ: chỉ mở port 22 cho SSH mà quên mở port 80 HTTP hoặc 443 HTTPS).
* Lỗi HTTP 403 Forbidden: Request đã đến được server nhưng bị từ chối quyền truy cập. Trong AWS, lỗi này thường do IAM User/Role thiếu Policy, hoặc Amazon S3 Bucket chặn quyền đọc. AWS khuyến khích dùng IAM Role để cấp quyền tạm thời thay vì lưu Access Key trực tiếp trong mã nguồn.
* Lỗi HTTP 500 Internal Server Error: Trình duyệt thường chỉ báo lỗi chung chung, che giấu các nguyên nhân thực sự bên trong như code bị exception, rớt kết nối database, thiếu biến môi trường hoặc hết bộ nhớ. Việc sử dụng Amazon CloudWatch để thu thập Application Logs và System Logs là cực kỳ quan trọng để "bắt đúng bệnh" nhanh chóng.
* Server chậm khi có nhiều người truy cập: Hệ thống chạy tốt với vài người dùng nhưng sập nguồn khi hàng trăm người truy cập cùng lúc khiến CPU tăng vọt 100%. Kết hợp Amazon EC2 Auto Scaling và Elastic Load Balancer giúp hệ thống tự động sinh thêm máy chủ và phân phối đều lưu lượng tải, giữ cho ứng dụng luôn mượt mà.
* Mất dữ liệu sau khi thay server: Việc lưu trữ file, hình ảnh tải lên ngay trong thư mục cục bộ của EC2 sẽ gây mất dữ liệu vĩnh viễn nếu server gặp sự cố. Amazon S3 là giải pháp lưu trữ lý tưởng, giúp tách biệt nơi chứa dữ liệu và nơi chạy ứng dụng, từ đó giảm rủi ro và dễ dàng mở rộng.

Phần lớn các sự cố khi triển khai ứng dụng không xuất phát từ việc "code sai", mà đến từ cách hệ thống được cấu hình và vận hành. Một ứng dụng ổn định đòi hỏi việc giám sát trạng thái, ghi log đầy đủ, quản lý quyền hợp lý và có khả năng chịu lỗi. Đó cũng là lý do AWS xây dựng một hệ sinh thái hoàn chỉnh không chỉ để lưu trữ hay tính toán, mà còn hỗ trợ vận hành ứng dụng trong môi trường thực tế.

![Các lỗi triển khai phổ biến và giải pháp AWS](/images/blog3.jpg)

Tài liệu tham khảo:

* [Auto Scaling Documentation](https://docs.aws.amazon.com/autoscaling/)
* [Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
* [CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html)
* [AWS Identity and Access Management](https://docs.aws.amazon.com/iam/)