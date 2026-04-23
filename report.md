> **Họ tên:** Phạm Hoàng Long </br>
> **MSHV:** 2A202600261

# BÁO CÁO KẾT QUẢ TRIỂN KHAI (PHƯƠNG ÁN CPU)

## Lý do sử dụng CPU:
Do tài khoản AWS đang trong chế độ Free Tier và bị giới hạn hạn mức vCPU cho các dòng máy GPU (G and VT instances) về mức 0. Mặc dù đã gửi yêu cầu nâng Quota nhưng chưa được phê duyệt kịp thời, vì vậy tôi đã chuyển sang phương án dự phòng sử dụng máy chủ CPU (t3.micro) để đảm bảo tiến độ bài lab.

## Kết quả Training:
Mô hình LightGBM được huấn luyện trên bộ dữ liệu Credit Card Fraud (284,807 dòng) hoàn thành trong 4.43 giây.

## Chất lượng mô hình: 
Chỉ số AUC-ROC đạt 0.7527 và độ chính xác (Accuracy) đạt 99.74%, cho thấy mô hình hoạt động hiệu quả trong việc phân loại giao dịch gian lận.

## Hiệu năng Inference: 
Tốc độ dự báo trung bình cực nhanh, chỉ mất khoảng 7.92 microseconds/dòng, đáp ứng tốt yêu cầu về độ trễ thấp của hệ thống API.

![alt text](<terminal.png>)

## Đánh giá:
Phương án CPU mặc dù không chạy được các mô hình Deep Learning lớn nhưng hoàn toàn đáp ứng tốt các bài toán Machine Learning truyền thống như Gradient Boosting, giúp tối ưu chi phí và vượt qua các rào cản về hạn mức tài nguyên của tài khoản mới.