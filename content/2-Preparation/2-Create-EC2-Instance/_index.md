---
title : "Create EC2 Instance"
date : "2025-08-07"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Create EC2 instance

{{% notice note %}}
Proceed to create 2 EC2 instances in 2 regions, starting with Singapore.
{{% /notice %}}

1. Login to [AWS Console](https://aws.amazon.com/console/)

    - Search for **EC2**
    - Select **EC2**

2. In the **EC2** dashboard

    - Select **Instances**
    - Choose **Launch instances**

![CreateEC2](/FCJ-Workshop/images/1/CEC1.png?featherlight=false&width=90pc)

3. Enter **Name**: `web-singapore`

![CreatEC2](/FCJ-Workshop/images/1/CEC2.png?featherlight=false&width=90pc)

4. Choose Amazon Machine Image (AMI)

Under the **Application and OS Images (Amazon Machine Image)** section, follow these steps:

   - Select **Quick Start**, then choose **Amazon Linux**.
   - From **Amazon Machine Image (AMI)**, select **Amazon Linux 2023 kernel-6.1 AMI** (Free tier eligible)

![CreatEC2](/FCJ-Workshop/images/1/CEC3.png?featherlight=false&width=90pc)

5. Choose instance type

    - Under the **Instance type** section, select **t2.micro**. This instance type is eligible for the AWS Free Tier, making it suitable for applications with low resource requirements or for development environments. 

![CreatEC2](/FCJ-Workshop/images/1/CEC4.png?featherlight=false&width=90pc)

6. Configure key pair

Under the **Key pair (login)** section, choose Create key pair, then configure it as follows:

   - Name: `keysg`
   - Key pair type: **RSA**
   - Private key file format: **.pem**

![CreatEC2](/FCJ-Workshop/images/1/CEC5.png?featherlight=false&width=90pc)

Press **Create key pair**

7. Configure Network settings

    - Next to **Network settings**, select **Edit**.
    - Choose **Select existing security group**.
    - From **Common security groups**, select the security group you created earlier..

![CreatEC2](/FCJ-Workshop/images/1/CEC6.png?featherlight=false&width=90pc)

![CreatEC2](/FCJ-Workshop/images/1/CEC7.png?featherlight=false&width=90pc)


8. Configure Advanced details

    - Scroll down to the bottom to the User data section and add the following code:

```js
    #!/bin/bash
    yum update -y
    yum install -y httpd
    systemctl start httpd
    systemctl enable httpd
    echo "<h1>Web Server in Singapore Region</h1>" > /var/www/html/index.html
```

![CreatEC2](/FCJ-Workshop/images/1/CEC11.png?featherlight=false&width=90pc)

9. Review and Launch Instance
   
    - Review your instance configuration in the **Summary panel**.
    - When you're ready, select **Launch instance**.

![CreatEC2](/FCJ-Workshop/images/1/CEC8.png?featherlight=false&width=90pc)

10. Confirm and Check Status

    - After receiving the confirmation message, select **View all instances** to return to the console dashboard.
    - Monitor the instance's launch status. Initially, the status will be **pending** and will then change to **running** when the instance is ready.
    - Wait until the instance passes its Status check before attempting to connect.

![CreatEC2](/FCJ-Workshop/images/1/CEC9.png?featherlight=false&width=90pc)

![CreatEC2](/FCJ-Workshop/images/1/CEC10.png?featherlight=false&width=90pc)

{{% notice note %}}
Create an EC2 instance in Virginia, similar to Singapore
{{% /notice %}}

- **Name**: `web-virginia`
- Create a key pair with the **Name**: `keyvg`
- Configure Network settings to connect with the security group previously created in the N. Virginia region, named web-vg

![CreatEC2](/FCJ-Workshop/images/1/CEC12.png?featherlight=false&width=90pc)

- Paste the following User data code, making sure to change the displayed content:

```js
    #!/bin/bash
    yum update -y
    yum install -y httpd
    systemctl start httpd
    systemctl enable httpd
    echo "<h1>Web Server in Virginia Region</h1>" > /var/www/html/index.html
```

![CreatEC2](/FCJ-Workshop/images/1/CEC13.png?featherlight=false&width=90pc)

- Confirmation of successful creation.

![CreatEC2](/FCJ-Workshop/images/1/CEC14.png?featherlight=false&width=90pc)

1.  Check Website 

- Copy the Public DNS and paste it into a browser to view the website content.

![CreatEC2](/FCJ-Workshop/images/1/CEC15.png?featherlight=false&width=90pc)

- The website is operational.

![CreatEC2](/FCJ-Workshop/images/1/CEC16.png?featherlight=false&width=90pc)
