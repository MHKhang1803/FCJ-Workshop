---
title : "Failover Routing"
date : "2025-08-07"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

#### Cấu hình Geolocation Routing

1. Đăng nhập vào [AWS Console](https://aws.amazon.com/console/).

    - Tìm **Route 53**
    - Chọn **Route 53**

2. Trong giao diện **Route 53**

    - Chọn **Hosted zones** đã tạo 
    - Chọn **Create records**

![FailoverRouting](/images/2/CWT1.png?featherlight=false&width=90pc)

![FailoverRouting](/images/2/CWT2.png?featherlight=false&width=90pc)

{{% notice note %}}
Xóa các record kiểu khác do Route 53 chỉ cho một record trùng Name/Type, sau đó tiến hành tạo record mới 
{{% /notice %}}

3. Tạo 2 A Record với Routing Policy là Failover

- Record 1: Singapore

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address của EC2 Singapore
   - **TTL** : 300
   - **Routing Policy**: Failover
   - **Failover record type**: Primary
   - **Health check ID**: Chọn Singapore Health check
   - **Record ID**: SG-Failover
   - Nhấn **Create records**

![FailoverRouting](/images/2/CFL1.png?featherlight=false&width=90pc)

- Record 2: Virginia

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address của EC2 Virginia
   - **TTL** : 300
   - **Routing Policy**: Failover
   - **Failover record type**: Secondary
   - **Health check ID**: Chọn Virginia Health check
   - **Record ID**: VG-Failover
   - Nhấn **Create records**

![FailoverRouting](/images/2/CFL2.png?featherlight=false&width=90pc)

{{% notice note %}}
Test nhanh bằng cách truy cập vào địa chỉ domain (ví dụ http://www.workshopkhang.com) sẽ thấy hiện ra trang chủ của Sigapore do chúng ta gán Failover record type của Singapore là Primary, tức là server chính
{{% /notice %}}

4. Kiểm thử

- Mục tiêu: Khi server Singapore "ngưng hoạt động", Route 53 sẽ tự động chuyển sang server Virginia
- Các bước thực hiện:

  - Kết nối SSH vào EC2 Singapore, dùng MobaXterm

![FailoverRouting](/images/2/CFL3.png?featherlight=false&width=90pc)

  - Dừng web server (Apache) trên EC2 Singapore bằng câu lệnh: `sudo systemctl stop httpd`

![FailoverRouting](/images/2/CFL4.png?featherlight=false&width=90pc)

  - Chờ khoảng 1–2 phút (tuỳ Health Check time và fail threshold), Route 53 sẽ phát hiện server Singapore bị lỗi (Unhealthy) và sẽ chuyển truy cập sang Virginia.

![FailoverRouting](/images/2/CFL6.png?featherlight=false&width=90pc)

  - Truy cập lại địa chỉ domain(ví dụ http://www.workshopkhang.com), nếu cấu hình đúng, chúng ta sẽ thấy Web Server của Virginia 

![FailoverRouting](/images/2/CFL5.png?featherlight=false&width=90pc)

{{% notice note %}}
Sau khi kiểm thử xong, chúng ta có thể khởi động lại Apache ở Singapore nếu muốn đưa hệ thống trở lại bình thường bằng cách nhập lệnh `sudo systemctl start httpd`
{{% /notice %}}

![FailoverRouting](/images/2/CFL7.png?featherlight=false&width=90pc)

- Route 53 sẽ tự động chuyển lại về Singapore sau khi Health Check nhận server Healthy.

![FailoverRouting](/images/2/CFL8.png?featherlight=false&width=90pc)
