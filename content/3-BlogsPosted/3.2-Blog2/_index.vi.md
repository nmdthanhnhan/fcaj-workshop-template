---
title: "Blog 2"
date: 2026-07-30
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# Bảo mật trong phát triển phần mềm – Không chỉ là viết code an toàn 
 
 
[Link blog 2](https://www.facebook.com/share/p/18aas3Dc43/)


Trong quá trình học AWS, cả nhóm nhận ra một điều khá thú vị. Khi mới làm project, hầu hết chúng ta chỉ tập trung vào việc "làm sao cho ứng dụng chạy được". Nhưng một khi ứng dụng được đưa lên Internet, câu hỏi quan trọng hơn nhiều lại là: làm sao để ứng dụng vẫn an toàn? Một ứng dụng có thể chạy rất mượt về mặt chức năng, nhưng chỉ cần một cấu hình sai hoặc một lỗ hổng nhỏ, dữ liệu có thể bị lộ hoặc hệ thống bị tấn công bất cứ lúc nào. AWS không chỉ cho mình hạ tầng để triển khai ứng dụng, mà còn có cả một loạt dịch vụ giúp xây dựng kiến trúc bảo mật ngay từ đầu, chứ không phải chờ đến khi có sự cố mới đi vá.

Các điểm chính cần nắm:

* Không nên lưu Access Key trong mã nguồn: Tránh để lộ thông tin xác thực lên GitHub để không bị lợi dụng tài nguyên hay phát sinh chi phí lớn; thay vào đó nên dùng IAM Role, Environment Variables, AWS Secrets Manager hoặc AWS Systems Manager Parameter Store.
* Nguyên tắc "Least Privilege" (Cấp quyền tối thiểu): Chỉ cấp đúng quyền cần thiết cho dịch vụ (ví dụ EC2 chỉ cần `s3:GetObject` cho đúng bucket thay vì quyền FullAccess) để giảm thiểu thiệt hại khi bị xâm nhập.
* Không phải tài nguyên nào cũng nên mở ra Internet: Tránh đặt mọi dịch vụ vào Public Subnet; thay vào đó, kiến trúc an toàn nên đi qua Load Balancer, đặt Backend ở Public/Private phù hợp và Database nằm ở Private Subnet.
* Bảo vệ ứng dụng khỏi các cuộc tấn công Web: Sử dụng AWS WAF (Web Application Firewall) để lọc các request độc hại như SQL Injection, XSS, DDoS ở tầng ứng dụng hoặc giới hạn request từ các IP đáng ngờ.
* Giám sát hệ thống liên tục với các công cụ chuyên dụng:
  * Amazon GuardDuty: Tự động phát hiện hành vi bất thường dựa trên CloudTrail, VPC Flow Logs và DNS Logs.
  * Amazon Inspector: Quét lỗ hổng bên trong EC2 Instance, Container Image và các thư viện phần mềm.
  * Amazon Security Hub: Tổng hợp kết quả từ các dịch vụ bảo mật lên một bảng điều khiển duy nhất.
* Giải quyết bài toán mở rộng và lưu trữ thực tế: Kết hợp Amazon EC2 Auto Scaling với Elastic Load Balancer để chống quá tải khi lượng truy cập tăng đột biến, đồng thời dùng Amazon S3 để tách biệt nơi lưu trữ dữ liệu với nơi chạy ứng dụng nhằm tránh mất dữ liệu khi đổi server.

Việc tích hợp tư duy bảo mật và vận hành ngay từ đầu giúp biến một kiến trúc tiềm ẩn rủi ro thành một hệ thống an toàn, linh hoạt và chuyên nghiệp khi bước vào các dự án thực tế.

![Kiến trúc bảo mật và vận hành trên AWS](/images/blog2.jpg)

Tài liệu tham khảo:

* [IAM best practices (AWS docs)](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
* [Well-Architected – IAM](https://docs.aws.amazon.com/wellarchitected/latest/framework/sec-iam.html)
* [AWS WAF](https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html)
* [Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html)
* [Amazon Inspector](https://aws.amazon.com/inspector/)
