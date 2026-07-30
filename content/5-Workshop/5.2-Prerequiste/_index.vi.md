---
title: "Tổng quan (Overview)"
date: 2026-07-27
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Tổng quan Workshop: Nền tảng MLOps Dự đoán Khách hàng Rời mạng (Telco Customer Churn)

## Giới thiệu bài toán
Trong lĩnh vực viễn thông (Telco), việc thu hút một khách hàng mới thường đòi hỏi mức chi phí cao gấp 5 đến 25 lần so với việc duy trì một khách hàng hiện hữu. Do đó, khả năng dự báo sớm rủi ro khách hàng rời bỏ dịch vụ (Churn) sẽ hỗ trợ đắc lực cho bộ phận chăm sóc khách hàng trong việc chủ động thiết lập các chính sách ưu đãi và biện pháp hỗ trợ kịp thời.

Tuy nhiên, trong thực tiễn vận hành, các mô hình Học máy (Machine Learning) thường đối mặt với hiện tượng **Data Drift / Model Drift** — sự suy giảm độ chính xác của dự đoán theo thời gian khi hành vi người dùng thay đổi. Thêm vào đó, quy trình huấn luyện và đưa mô hình từ môi trường thử nghiệm (Jupyter Notebook) lên môi trường thực tế (Production) bằng phương pháp thủ công thường tiêu tốn rất nhiều thời gian và tiềm ẩn nhiều rủi ro lỗi vận hành.

Để giải quyết triệt để những thách thức này, workshop sẽ hướng dẫn xây dựng một **Hệ thống MLOps Tự động hóa Khép kín (End-to-End Automated MLOps Platform)** dựa trên hạ tầng **AWS Cloud**.

---

## Mục tiêu Workshop
Kết thúc bài thực hành này, bạn sẽ làm chủ và có khả năng triển khai các hạng mục sau:
1. **Dự đoán theo thời gian thực (Real-time Inference):** Ứng dụng và tích hợp Amazon API Gateway, AWS Lambda cùng AWS SageMaker Serverless Endpoint nhằm xử lý yêu cầu và trả về kết quả dự báo xác suất rời mạng ngay lập tức, đồng thời tối ưu hóa chi phí (không phát sinh phí khi không có lưu lượng truy cập).
2. **Cơ chế kích hoạt tự động (Event-Driven Trigger):** Hệ thống sẽ tự động nhận diện thời điểm Quản trị viên (Admin) đẩy dữ liệu mới lên kho lưu trữ Amazon S3, tiến hành kiểm tra mức độ Data Drift và tự động kích hoạt chu trình tái huấn luyện (Retrain).
3. **Quy trình MLOps tự động (SageMaker Pipeline - 4 bước):**
   - TelcoChurnProcessStep: Xử lý dữ liệu thô và phân chia thành các tập Huấn luyện (Train), Xác thực (Validation) và Kiểm thử (Test) thông qua tính năng SKLearnProcessor.
   - TelcoChurnHpoStep: Tự động hóa quá trình huấn luyện và tinh chỉnh siêu tham số cho mô hình XGBoost thông qua HyperparameterTuner.
   - TelcoChurnEvalStep: Tiến hành đo lường, đánh giá chất lượng mô hình trên tập dữ liệu kiểm thử bằng ScriptProcessor.
   - ConditionStep: Đối chiếu kết quả với ngưỡng chất lượng tiêu chuẩn ($AUC \ge 0.80$). Nếu mô hình thỏa mãn điều kiện, hệ thống sẽ tự động đăng ký mô hình đó vào SageMaker Model Registry dưới trạng thái Approved (Đã phê duyệt).
4. **Triển khai liên tục (Continuous Deployment - CD):** Ứng dụng Amazon EventBridge để theo dõi trạng thái Approved từ Model Registry, qua đó kích hoạt AWS Lambda Deployer nhằm cập nhật Serverless Endpoint tự động mà không làm gián đoạn dịch vụ đang hoạt động (Zero-Downtime Deployment).
5. **Theo dõi & Cảnh báo (Monitoring & Alerting):** Tập trung hóa công tác quản lý log thông qua CloudWatch Logs, thiết lập hệ thống cảnh báo CloudWatch Alarm và tự động hóa việc gửi email thông báo sự cố qua dịch vụ Amazon SNS.

---

## Sơ đồ Kiến trúc Hệ thống (Architecture Diagram)

![Sơ đồ Kiến trúc MLOps AWS](/images/telco-churn-role.png)

### Vai trò của các Dịch vụ AWS:
- **Amazon S3:** Đóng vai trò là nơi lưu trữ tập trung dữ liệu thô, dữ liệu đã qua tiền xử lý và các tệp trọng số của mô hình (Model Artifacts).
- **Amazon API Gateway & AWS Lambda:** Cung cấp điểm cuối REST API, chịu trách nhiệm tiếp nhận và tiền xử lý các luồng dữ liệu yêu cầu theo thời gian thực.
- **AWS SageMaker Serverless Endpoint:** Phục vụ công tác triển khai mô hình XGBoost dưới kiến trúc Serverless, cung cấp khả năng tự động co giãn tài nguyên linh hoạt.
- **AWS SageMaker Pipelines:** Đảm nhận vai trò điều phối và quản lý toàn bộ chu trình làm việc Machine Learning 4 bước hoàn toàn tự động.
- **AWS SageMaker Model Registry:** Cung cấp giải pháp lưu trữ và quản lý tập trung các phiên bản của mô hình.
- **Amazon EventBridge:** Chịu trách nhiệm giám sát và bắt các sự kiện chuyển đổi trạng thái phát sinh từ hệ thống Pipeline và Model Registry.
- **Amazon SNS:** Đảm bảo việc gửi Email thông báo kết quả của chu trình Retrain cũng như tự động phát đi các cảnh báo sự cố.
- **Amazon CloudWatch:** Thực hiện chức năng ghi nhận log hệ thống, theo dõi các chỉ số hoạt động (metrics) cốt lõi và kích hoạt cảnh báo khi phát hiện lỗi.

---

## Thời gian & Chi phí ước tính
- **Thời gian thực hiện:** ~60 - 90 phút.
- **Chi phí hạ tầng:** ~$0.50 - $1.00 USD (Nếu dọn dẹp tài nguyên đúng theo bước Clean-up ở cuối bài lab, hầu hết các dịch vụ đều nằm trong AWS Free Tier).
