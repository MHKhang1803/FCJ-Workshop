---
title : "Tạo EC2 Instance"
date : "2025-08-07"
weight : 2
chapter: false
pre : " <b> 2.2 </b> "
---

#### Tạo EC2 instance

{{% notice note %}}
Tiến hành tạo 2 EC2 instance ở 2 region, trước tiên là ở **Singapore**
{{% /notice %}}

1. Đăng nhập vào [AWS Console](https://aws.amazon.com/console/).

    - Tìm **EC2**
    - Chọn **EC2**

2. Trong giao diện **EC2**

    - Chọn **Instances**
    - Chọn **Launch instances**

![CreateEC2](/static/images/1/CEC1.png?featherlight=false&width=90pc)

3. Nhập **Name**: `web-singapore`

![CreatEC2](/static/images/1/CEC2.png?featherlight=false&width=90pc)

4. Chọn Amazon Machine Image (AMI)

Dưới phần **Application and OS Images (Amazon Machine Image)**, làm theo các bước sau đây:

   - Chọn **Quick Start**, sau đó chọn **Amazon Linux**.
   - Từ **Amazon Machine Image (AMI)**, chọn **Amazon Linux 2023 kernel-6.1 AMI** (Free tier eligible)

![CreatEC2](/static/images/1/CEC3.png?featherlight=false&width=90pc)

5. Chọn loại instance

    - Dưới phần **Instance type**, chọn loại instance **t2.micro** đủ điều kiện sử dụng trong AWS Free Tier, phù hợp cho các ứng dụng có yêu cầu tài nguyên thấp hoặc môi trường phát triển. 

![CreatEC2](/static/images/1/CEC4.png?featherlight=false&width=90pc)

6. Cấu hình key pair

Dưới phần **Key pair (login)**, chọn Create key pair, sau đó tiến hành cấu hình:

   - Name: `keysg`
   - Key pair type: **RSA**
   - Private key file format: **.pem**

![CreatEC2](/static/images/1/CEC5.png?featherlight=false&width=90pc)

Nhấn **Create key pair**

7. Cấu hình Network settings

    - Bên cạnh **Network settings**, chọn **Edit**.
    - Chọn **Select existing security group**.
    - Từ **Common security groups**, chọn security group đã tạo trước đó.

![CreatEC2](/static/images/1/CEC6.png?featherlight=false&width=90pc)

![CreatEC2](/static/images/1/CEC7.png?featherlight=false&width=90pc)


8. Cấu hình Advanced details

    - Cuộn xuống dưới cùng phần User data, thêm đoạn code như sau:

```js
    #!/bin/bash
    yum update -y
    yum install -y httpd
    systemctl start httpd
    systemctl enable httpd
    echo "<h1>Web Server in Singapore Region</h1>" > /var/www/html/index.html
```

![CreatEC2](/static/images/1/CEC11.png?featherlight=false&width=90pc)

9. Xác nhận và khởi tạo instance
   
    - Xem lại cấu hình instance trong **Summary panel**.
    - Khi đã sẵn sàng, chọn **Launch instance**.

![CreatEC2](/static/images/1/CEC8.png?featherlight=false&width=90pc)

10. Xác nhận và kiểm tra trạng thái

    - Sau khi nhận thông báo xác nhận, chọn **View all instances** để quay lại giao diện console.
    - Theo dõi trạng thái khởi tạo instance. Ban đầu, trạng thái sẽ là **pending** và sau đó chuyển sang **running** khi instance đã sẵn sàng.
    - Đợi cho đến khi instance vượt qua kiểm tra trạng thái (Status check) trước khi thử kết nối.

![CreatEC2](/static/images/1/CEC9.png?featherlight=false&width=90pc)

![CreatEC2](/static/images/1/CEC10.png?featherlight=false&width=90pc)

{{% notice note %}}
Tạo EC2 instance tại Virginia, tương tự như Singapore
{{% /notice %}}

- **Name**: `web-virginia`
- Tạo key pair với **Name**: `keyvg`
- Cấu hình Network settings kết nối với security group đã tạo ở region N.Virginia là web-vg

![CreatEC2](/static/images/1/CEC12.png?featherlight=false&width=90pc)

- Dán đoạn User data như sau (đổi nội dung hiển thị):

```js
    #!/bin/bash
    yum update -y
    yum install -y httpd
    systemctl start httpd
    systemctl enable httpd
    echo "<h1>Web Server in Virginia Region</h1>" > /var/www/html/index.html
```

![CreatEC2](/static/images/1/CEC13.png?featherlight=false&width=90pc)

- Xác nhận tạo thành công

![CreatEC2](/static/images/1/CEC14.png?featherlight=false&width=90pc)

11. Kiểm tra Website 

- Copy Public DNS đưa lên trình duyệt để xem nội dung website

![CreatEC2](/static/images/1/CEC15.png?featherlight=false&width=90pc)

- Website hoạt động

![CreatEC2](/static/images/1/CEC16.png?featherlight=false&width=90pc)
