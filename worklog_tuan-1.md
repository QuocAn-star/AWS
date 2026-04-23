# WORKLOG TUẦN 1

| **Thông tin** | **Chi tiết** |
|---------------|---------------|
| Thời gian | Tuần 1 (Ngày 20/4/2026 - 26/4/2026) |
| Chủ đề | Getting Started with AWS Cloud |
| Người thực hiện | [Phạm Quốc An] |
| Vị trí | AWS Internship |

---

## 1. Tổng quan & mục tiêu tuần

- **Hoàn thành 5 nhiệm vụ**  
  Nhận credit AWS để sử dụng các dịch vụ trong quá trình thực tập  

- **Làm quen AWS Console**  
  Thao tác thành thạo với giao diện quản lý AWS  

- **Thiết lập theo dõi chi phí**  
  Cấu hình Billing alerts & Budgets để tránh phát sinh chi phí ngoài ý muốn  

- **Tạo EC2 instance**  
  Tạo và quản lý máy chủ ảo đầu tiên trên AWS  

- **Deploy web server**  
  Triển khai một web server đơn giản chạy trên EC2  


---

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Làm quen với các thành viên FCJ <br> - Đọc và ghi nhớ nội quy, quy định tại đơn vị thực tập | 20/04/2026 | 20/04/2026 | |
| 3 | - Tìm hiểu AWS và các nhóm dịch vụ cơ bản: <br> &emsp; + Compute <br> &emsp; + Storage <br> &emsp; + Networking <br> &emsp; + Database | 21/04/2026 | 21/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - **Hoàn thành 5 nhiệm vụ nhận credit AWS** <br> - **Làm quen AWS Console** <br> - Tạo AWS Free Tier account <br> - Tìm hiểu AWS Console & AWS CLI <br> - **Thực hành:** <br> &emsp; + Tạo AWS account <br> &emsp; + Cài AWS CLI & cấu hình <br> &emsp; + Sử dụng các lệnh AWS CLI cơ bản | 22/04/2026 | 22/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - **Thiết lập theo dõi chi phí** <br> &emsp; + Cấu hình Billing alerts & Budgets <br> - Tìm hiểu EC2 cơ bản: <br> &emsp; + Instance types <br> &emsp; + AMI <br> &emsp; + EBS <br> &emsp; + Elastic IP <br> - Các cách remote SSH vào EC2 | 23/04/2026 | 23/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - **Tạo EC2 instance** <br> - **Deploy web server đơn giản chạy trên EC2** <br> - **Thực hành:** <br> &emsp; + Tạo EC2 instance <br> &emsp; + Kết nối SSH vào EC2 <br> &emsp; + Gắn EBS volume | 24/04/2026 | 24/04/2026 | https://cloudjourney.awsstudygroup.com/ |


---

## 2. Kiến thức AWS cơ bản được học

| Nhóm dịch vụ | Dịch vụ | Công dụng chính | Ví dụ thực tế |
|--------------|---------|------------------|----------------|
| Compute | EC2 | Máy chủ ảo, tùy chỉnh cấu hình | Host web, chạy ứng dụng backend |
| Compute | Lambda | Chạy code không cần server | Xử lý sự kiện, API serverless |
| Storage | S3 | Lưu trữ object, file tĩnh | Lưu ảnh, video, backup dữ liệu |
| Storage | EBS | Ổ đĩa ảo gắn với EC2 | Lưu dữ liệu hệ thống và ứng dụng |
| Storage | EFS | Hệ thống file chia sẻ dùng chung | NFS cho nhiều EC2 cùng truy cập |
| Networking | VPC | Mạng ảo riêng biệt | Cách ly tài nguyên, bảo mật |
| Networking | Security Group | Tường lửa ảo cho instance | Kiểm soát inbound/outbound traffic |
| Database | RDS | Cơ sở dữ liệu quan hệ quản lý sẵn | MySQL, PostgreSQL, Aurora |
| Database | Aurora | DB hiệu năng cao, tương thích MySQL/PostgreSQL | Ứng dụng doanh nghiệp |
| Security | IAM | Quản lý người dùng và quyền truy cập | Phân quyền chi tiết đến từng tài nguyên |

---

## 3. Tài khoản & AWS Console

| Hạng mục | Hành động cụ thể | Ghi chú |
|----------|------------------|----------|
| Tạo tài khoản | Đăng ký AWS Free Tier bằng email và thẻ tín dụng | Đã xác thực thành công |
| Đăng nhập | Truy cập AWS Management Console | Dùng IAM user để bảo mật |
| Làm quen giao diện | Khám phá các dịch vụ trên thanh menu và dashboard | Có thể tùy chỉnh favorite services |
| Tìm kiếm nhanh | Sử dụng thanh Search để truy cập EC2, S3, Lambda, RDS | Tiết kiệm thời gian |
| Chọn Region | Chọn **ap-southeast-1 (Singapore)** | Độ trễ thấp, chi phí tối ưu cho khu vực Châu Á |

---

## 4. Thực hành chi tiết các task chính

### Task 1: EC2

| Bước | Hành động | Chi tiết thao tác | Kết quả |
|------|-----------|-------------------|----------|
| 1 | Tạo EC2 instance | Chọn AMI: Amazon Linux 2, t2.micro (Free Tier) | Instance chạy OK |
| 2 | Tạo key pair | Loại RSA, định dạng .pem, lưu an toàn | Dùng để SSH vào instance |
| 3 | Cấu hình Security Group | Mở port 22 (SSH) và port 80 (HTTP) | Truy cập được web server |
| 4 | Launch instance | Nhấn Launch và chờ trạng thái Running | Instance hoạt động ổn định |
| 5 | Terminate instance | Xóa instance sau khi test để tránh phát sinh chi phí | Không còn instance chạy |

### Task 2: Amazon Bedrock

| Bước | Hành động | Chi tiết | Kết quả / Vấn đề |
|------|-----------|----------|------------------|
| 1 | Chọn model | Chọn Claude 3 Haiku | Chưa được cấp quyền ngay |
| 2 | Nhập use case | "Test AI integration for web app" | Gửi yêu cầu thành công |
| 3 | Xử lý lỗi | Gửi support request lên AWS | AWS đã cấp quyền sau 2 giờ |
| 4 | Test prompt | Nhập prompt "Explain AWS Lambda in simple terms" | Model trả lời chính xác |

### Task 3: AWS Budgets

| Bước | Hành động | Chi tiết | Ghi chú |
|------|-----------|----------|----------|
| 1 | Tạo budget | Budget name: "Monthly-AWS-Cost" | Số tiền: 10 USD/tháng |
| 2 | Cấu hình email cảnh báo | Gửi alert khi chi phí vượt 50%, 80%, 100% | Nhập đúng email nhận thông báo |
| 3 | Kiểm tra | Xem lại budget trong AWS Budgets dashboard | Hoạt động tốt |

### Task 4: AWS Lambda

| Bước | Hành động | Chi tiết | Kết quả |
|------|-----------|----------|----------|
| 1 | Tạo web app serverless | Dùng blueprint "hello-world-python" | Function được tạo |
| 2 | Deploy function HTTP | Tạo API Gateway trigger | Nhận được endpoint URL |
| 3 | Test function | Gửi GET request qua trình duyệt hoặc curl | Trả về "Hello from Lambda" |
| 4 | Xóa function | Xóa Lambda function và API Gateway | Tránh phát sinh chi phí |

### Task 5: AWS RDS

| Bước | Hành động | Chi tiết | Kết quả |
|------|-----------|----------|----------|
| 1 | Tạo database | Chọn Aurora PostgreSQL, Free Tier template | DB cluster đang tạo |
| 2 | Theo dõi trạng thái | Chờ đến khi status là "Available" | Mất khoảng 5-7 phút |
| 3 | Kết nối thử | Lấy endpoint và test kết nối (tuỳ chọn) | Kết nối thành công |
| 4 | Xóa database | Xóa DB cluster và snapshot nếu có | Dọn dẹp sạch sẽ |

---

## 5. Kết quả đạt được sau tuần 1

| STT | Kết quả | Mô tả chi tiết |
|-----|---------|------------------|
| 1 | Hoàn thành 5 task | Nhận được credit AWS, có thể dùng cho tuần 2 |
| 2 | Hiểu cách tạo và quản lý tài nguyên | Tạo, cấu hình, test, xoá thành thạo EC2, Lambda, RDS |
| 3 | Làm quen workflow cloud | Biết quy trình: Launch → Config → Test → Cleanup |
| 4 | Kiểm soát chi phí | Thiết lập budget và alert để không bị overrun |
| 5 | Tự tin với AWS Console | Có thể tự tìm kiếm và sử dụng các dịch vụ cơ bản |

---

## 6. Khó khăn & cách khắc phục

| Khó khăn | Cách khắc phục |
|----------|----------------|
| Chưa được cấp quyền Bedrock ngay | Gửi support request, đợi khoảng 2 giờ thì được duyệt |
| Quên terminate instance EC2 | Tạo budget và alert để nhắc nhở, kiểm tra hàng ngày |
| Chưa quen với IAM policy | Đọc tài liệu AWS IAM và thực hành tạo user với quyền hạn chế |

---

## 7. Kế hoạch tuần 2

| Hạng mục | Nội dung chi tiết | Mục tiêu |
|----------|-------------------|-----------|
| Storage | - Tạo S3 bucket, upload/download file<br>- Cấu hình lifecycle policy tự động chuyển hoặc xóa file<br>- Tạo EBS volume, gắn vào EC2, tạo snapshot backup | Quản lý dữ liệu lâu dài, tối ưu chi phí lưu trữ |
| Database | - Tiếp tục làm việc với RDS (PostgreSQL)<br>- Thực hành backup, restore, read replica | Nắm vững quản trị DB trên cloud |
| Hands-on | - Xây dựng hệ thống upload file lên S3 từ web<br>- Dùng Lambda để xử lý ảnh sau khi upload | Tích hợp nhiều dịch vụ AWS vào một ứng dụng hoàn chỉnh |

---


> **Tổng kết tuần 1:** Đã hoàn thành tốt các mục tiêu đề ra, sẵn sàng cho tuần 2 với Storage & Database.