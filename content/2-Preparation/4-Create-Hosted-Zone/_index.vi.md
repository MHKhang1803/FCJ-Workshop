---
title : "Tạo Hosted Zones"
date : "2025-08-07"
weight : 4
chapter: false
pre : " <b> 2.4 </b> "
---

#### Tạo Hosted Zones

1. Đăng nhập vào [AWS Console](https://aws.amazon.com/console/).

    - Tìm **Route 53**
    - Chọn **Route 53**

2. Trong giao diện **Route 53**

    - Chọn **Hosted zones**
    - Chọn **Create hosted zone**

![CreateHostedZone](/static/images/01/CHT1.png?featherlight=false&width=90pc)

3. Cấu hình Hosted zones

    - **Domain name**: nhập domain của bạn đã đăng ký (ví dụ workshopkhang.com)
    - **Description**: ghi theo cách của bạn (ví dụ WorkshopAWS)
    - **Type**: Public hosted zone
    - Nhấn **Create hosted zone**

![CreateHostedZone](/static/images/01/CHT2.png?featherlight=false&width=90pc)

![CreateHostedZone](/static/images/01/CHT3.png?featherlight=false&width=90pc)

{{% notice note %}}
Sau khi thực hiện tạo hosted zone thành công, chúng ta sẽ tiến hành copy **4 NS records** của hosted zone vừa tạo và dán chúng vào domain của bạn 
{{% /notice %}}

![CreateHostedZone](/static/images/01/CHT4.png?featherlight=false&width=90pc)

- Trong phần **Registered domains**, chọn Action, sau đó chọn Edit name servers

![CreateHostedZone](/static/images/01/CHT5.png?featherlight=false&width=90pc)

- Tiến hành dán 4 NS records của hosted zone đã tạo vào, sau đó nhấn Save changes

![CreateHostedZone](/static/images/01/CHT6.png?featherlight=false&width=90pc)

![CreateHostedZone](/static/images/01/CHT7.png?featherlight=false&width=90pc)
