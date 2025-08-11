---
title : "Weighted Routing"
date : "2025-08-07"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### Cấu hình Weighted Routing

1. Đăng nhập vào [AWS Console](https://aws.amazon.com/console/).

    - Tìm **Route 53**
    - Chọn **Route 53**

2. Trong giao diện **Route 53**

    - Chọn **Hosted zones** đã tạo 
    - Chọn **Create records**

![WeightedRouting](/FCJ-Workshop/images/2/CWT1.png?featherlight=false&width=90pc)

![WeightedRouting](/FCJ-Workshop/images/2/CWT2.png?featherlight=false&width=90pc)

3. Tạo 2 A Record với Routing Policy là Weighted

- Record 1: Singapore

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address của EC2 Singapore
   - **TTL** : 300
   - **Routing Policy**: Weighted
   - **Weight**: 50
   - **Health check ID**: Chọn Singapore Health check
   - **Record ID**: SG-Weighted
   - Nhấn **Create records**

![WeightedRouting](/FCJ-Workshop/images/2/CWT3.png?featherlight=false&width=90pc)

- Record 2: Virginia

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address của EC2 Virginia
   - **TTL** : 300
   - **Routing Policy**: Weighted
   - **Weight**: 50
   - **Health check ID**: Chọn Virginia Health check
   - **Record ID**: VG-Weighted
   - Nhấn **Create records**

![WeightedRouting](/FCJ-Workshop/images/2/CWT4.png?featherlight=false&width=90pc)

4. Kiểm thử

- Mở trình duyệt, truy cập vào địa chỉ domain (ví dụ http://www.workshopkhang.com)
- Refresh nhiều lần, chúng ta sẽ thấy:

   - Đôi lúc hiện Web Server in Singapore
   - Đôi lúc hiện Web Server in Virginia
   - Tần suất sẽ phản ánh theo tỉ lệ 50/50 đã cấu hình

![WeightedRouting](/FCJ-Workshop/images/2/CWT5.png?featherlight=false&width=90pc)

![WeightedRouting](/FCJ-Workshop/images/2/CWT6.png?featherlight=false&width=90pc)
