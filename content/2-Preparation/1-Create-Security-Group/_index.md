---
title : "Create Security Group"
date : "2025-08-07"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

{{% notice note %}}
We need to create 2 Security Groups in 2 different regions. The two regions to choose are Singapore and N. Virginia.
{{% /notice %}}

#### Configure Security Group

A Security Group acts as a virtual firewall to control inbound and outbound traffic for your EC2 instances. In this section, we will create a Security Group with appropriate rules for the EC2 instance.

Here are the steps to create a Security Group in the **Singapore** region:

1. Log in to the [AWS Console](https://aws.amazon.com/console/).

    - Search for and select **EC2**
    - Select **Security Groups**

![CreateSG](/static/images/1/CreateSG.png?featherlight=false&width=90pc)

2. On the **Create security group** interface

    - **Security group name**: Enter `web-sg`
    - **Description**: Enter `Allows SSH and HTTP access`
    - **VPC**: Keep the default VPC

![CreateSG](/static/images/1/CSG1.png?featherlight=false&width=90pc)

3. Configure **Inbound rules**: We need to add three inbound rules by clicking **Add rule** and then configuring each one as follows:

| Type  | Protocol | Port range |    Soucre     |
| ----- | -------- | ---------- | ------------- |
| SSH   |   TCP    |     22     |     My IP     |
| HTTP  |   TCP    |     80     | AnyWhere-IPv4 |
| HTTPS |   TCP    |     443    | AnyWhere-IPv4 |

![CreateSG](/static/images/1/CSG2.png?featherlight=false&width=90pc)

4. Click **Create security group**

![CreateSG](/static/images/1/CSG3.png?featherlight=false&width=90pc)

![CreateSG](/static/images/1/CSG4.png?featherlight=false&width=90pc)

{{% notice note %}}
Repeat the same steps to create a Security Group in the N. Virginia region, but this time, name the security group web-vg.
{{% /notice %}}

![CreateSG](/static/images/1/CSG5.png?featherlight=false&width=90pc)
