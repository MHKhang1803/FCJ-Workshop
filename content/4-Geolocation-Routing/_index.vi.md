---
title : "Geolocation Routing"
date : "2025-08-07"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### Cấu hình Geolocation Routing

1. Đăng nhập vào [AWS Console](https://aws.amazon.com/console/).

    - Tìm **Route 53**
    - Chọn **Route 53**

2. Trong giao diện **Route 53**

    - Chọn **Hosted zones** đã tạo 
    - Chọn **Create records**

![GeolocationRouting](/static/images/2/CWT1.png?featherlight=false&width=90pc)

![GeolocationRouting](/static/images/2/CWT2.png?featherlight=false&width=90pc)

{{% notice note %}}
Xóa các record kiểu khác do Route 53 chỉ cho một record trùng Name/Type, sau đó tiến hành tạo record mới 
{{% /notice %}}

3. Tạo 2 A Record với Routing Policy là Geolocation

- Record 1: Singapore

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address của EC2 Singapore
   - **TTL** : 60
   - **Routing Policy**: Geolocation
   - **Location**: Asia
   - **Health check ID**: Chọn Singapore Health check
   - **Record ID**: SG-Geolocation
   - Nhấn **Create records**

![GeolocationRouting](/static/images/2/CGC1.png?featherlight=false&width=90pc)

- Record 2: Virginia

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address của EC2 Virginia
   - **TTL** : 60
   - **Routing Policy**: Geolocation
   - **Location**: North America
   - **Health check ID**: Chọn Virginia Health check
   - **Record ID**: VG-Geolocation
   - Nhấn **Create records**

![GeolocationRouting](/static/images/2/CGC2.png?featherlight=false&width=90pc)

4. Kiểm thử

- Dùng công cụ test từ nhiều location như: https://geopeeker.com
- Truy cập địa chỉ domain (ví dụ http://www.workshopkhang.com)

![GeolocationRouting](/static/images/2/CGC3.png?featherlight=false&width=90pc)
