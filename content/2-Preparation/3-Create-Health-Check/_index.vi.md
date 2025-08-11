---
title : "Tạo Health checks"
date : "2025-08-07"
weight : 3
chapter: false
pre : " <b> 2.3 </b> "
---

{{% notice note %}}
Tiến hành tạo 2 Health checks ở 2 region, trước tiên là ở **Singapore**
{{% /notice %}}

#### Tạo Health checks

1. Đăng nhập vào [AWS Console](https://aws.amazon.com/console/).

    - Tìm **Route 53**
    - Chọn **Route 53**

2. Trong giao diện **Route 53**

    - Chọn **Health checks**
    - Chọn **Create health check**

![CreateHealthcheck](/static/images/01/CHC1.png?featherlight=false&width=90pc)

3. Cấu hình Health checks

    - **Name**: `SGHealthCheck`
    - **Resource**: Endpoint
    - **Specify endpoint by**: IP address
    - **IP address**: HTTP, sau đó nhập **Public IPv4 address** của EC2 instance ở region Singapore
    - Nhấn **Create Health check**

![CreateHealthcheck](/static/images/01/CHC2.png?featherlight=false&width=90pc)

![CreateHealthcheck](/static/images/01/CHC3.png?featherlight=false&width=90pc)

![CreateHealthcheck](/static/images/01/CHC4.png?featherlight=false&width=90pc)

{{% notice note %}}
Tương tự, tiến hành tạo Health checks ở region **Virginia**
{{% /notice %}}

- Cấu hình Health checks
  
    - **Name**: `VGHealthCheck`
    - **Resource**: Endpoint
    - **Specify endpoint by**: IP address
    - **IP address**: HTTP, sau đó nhập **Public IPv4 address** của EC2 instance ở region Virginia
    - Nhấn **Create Health check**

![CreateHealthcheck](/static/images/01/CHC5.png?featherlight=false&width=90pc)

![CreateHealthcheck](/static/images/01/CHC6.png?featherlight=false&width=90pc)

![CreateHealthcheck](/static/images/01/CHC7.png?featherlight=false&width=90pc)
