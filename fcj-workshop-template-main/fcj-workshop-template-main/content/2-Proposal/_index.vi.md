title: "Bản đề xuất"
date: "2025-09-11"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Online Ebook Store Platform  
## Giải pháp bán & đọc sách trực tuyến trên nền tảng Java + AWS  

### 1. Tóm tắt điều hành  
Online Ebook Store được thiết kế dành cho nhóm sinh viên IT (5 thành viên) trong khuôn khổ dự án thực tập. Nền tảng cho phép người dùng **mua và đọc sách trực tuyến (ebook, PDF/epub)** thông qua trình đọc tích hợp (PDF.js). Giải pháp phân quyền ba vai trò: **Admin (quản lý sách & hệ thống), Staff (hỗ trợ & duyệt review), User (mua và đọc sách)**.  
Nền tảng tận dụng **AWS RDS, S3, CloudFront, Elastic Beanstalk và IAM** để triển khai hệ thống có khả năng mở rộng, chi phí thấp và an toàn.  

### 2. Tuyên bố vấn đề  
*Vấn đề hiện tại*  
Các thư viện ebook miễn phí như **nhasachmienphi.com** chỉ cung cấp đọc/tải về nhưng thiếu tính năng quản lý người dùng, phân quyền, theo dõi đơn hàng, báo cáo doanh thu. Ngoài ra, nhiều nền tảng sách online phức tạp hoặc chi phí cao để vận hành.  

*Giải pháp*  
Hệ thống ebook store sẽ:  
- Lưu trữ và phân phối sách số qua **AWS S3 + CloudFront (signed URL)**.  
- Quản lý người dùng, sách, đơn hàng và review trên **AWS RDS (MySQL)**.  
- Deploy backend Java Spring Boot qua **Elastic Beanstalk**, frontend qua **S3/CloudFront**.  
- Phân quyền theo role (Admin, Staff, User).  
- Tích hợp bảo mật bằng **IAM role** và **JWT Authentication**.  

*Lợi ích & ROI*  
- Hệ thống demo hoàn chỉnh, có thể trình bày như một sản phẩm thương mại.  
- Tiết kiệm chi phí vận hành nhờ Free Tier AWS.  
- Dễ mở rộng (từ vài chục đến hàng nghìn user).  
- ROI về mặt học thuật: nhóm học được **phát triển full-stack + triển khai cloud thực tế**.  

### 3. Kiến trúc giải pháp  
Nền tảng áp dụng kiến trúc **3 lớp + dịch vụ AWS**:  
- **Frontend**: ReactJS hoặc Thymeleaf, hiển thị UI + PDF Viewer.  
- **Backend**: Spring Boot REST API (Auth, Books, Orders, Reviews).  
- **Database**: RDS MySQL.  
- **Storage**: S3 (cover + file sách), CloudFront (phân phối signed URL).  
- **Deploy**: Elastic Beanstalk (Java).  

*Dịch vụ AWS sử dụng*  
- **AWS RDS**: Lưu dữ liệu người dùng, sách, orders, reviews.  
- **AWS S3**: Lưu file ebook & ảnh bìa.  
- **AWS CloudFront**: CDN + signed URL bảo mật.  
- **AWS Elastic Beanstalk**: Deploy backend Spring Boot.  
- **AWS IAM**: Quản lý quyền dịch vụ.  

### 4. Triển khai kỹ thuật  
*Các giai đoạn triển khai*  
1. **Thiết kế & xây dựng local**: NetBeans + MySQL local (1–2 tuần).  
2. **Phát triển API & Frontend**: CRUD sách, auth, order, review (2–3 tuần).  
3. **Kiểm thử & tích hợp**: Test phân quyền, flow mua → đọc → review (1 tuần).  
4. **Triển khai AWS**: RDS, S3, CloudFront, Elastic Beanstalk (1–2 tuần).  

*Yêu cầu kỹ thuật*  
- Java 17 + Spring Boot.  
- MySQL (local → RDS).  
- ReactJS hoặc Thymeleaf + PDF.js.  
- AWS SDK for Java (tích hợp S3).  
- Postman cho test API.  

### 5. Lộ trình & Mốc triển khai  
- **Tháng 1**: Cài môi trường, dựng DB local.  
- **Tháng 2**: Viết API backend + UI cơ bản.  
- **Tháng 3**: Tích hợp AWS + kiểm thử + demo.  

### 6. Ước tính ngân sách  
Theo AWS Pricing Calculator (Free Tier + $100 credit AWS):  
- **RDS MySQL**: 0,00 USD/tháng (Free Tier 750h).  
- **S3**: 0,10–0,20 USD/tháng (5–10GB ebook).  
- **CloudFront**: 0,05 USD/tháng (1GB traffic).  
- **Elastic Beanstalk**: 0,00 USD/tháng (EC2 Free Tier).  
- **IAM + CloudWatch**: miễn phí.  

*Tổng*: ~0,3 USD/tháng (thực tế = 0 do Free Tier + credit).  

### 7. Đánh giá rủi ro  
- **Mất kết nối AWS** → ảnh hưởng demo (nguy cơ thấp).  
- **Rò rỉ file PDF** → hạn chế bằng signed URL.  
- **Vượt Free Tier** → chi phí tăng, cần giám sát bằng Billing Alarm.  

*Giải pháp dự phòng*  
- Có bản chạy local (NetBeans + MySQL) để demo offline.  
- Bật Billing Alarm AWS để giám sát chi phí.  

### 8. Kết quả kỳ vọng  
- **Kỹ thuật**: Có hệ thống bán & đọc sách số online full-stack.  
- **Học thuật**: Cả nhóm thành thạo Spring Boot + ReactJS + AWS cơ bản.  
- **Thực tế**: Mô hình có thể mở rộng thành nền tảng thương mại thật.  
