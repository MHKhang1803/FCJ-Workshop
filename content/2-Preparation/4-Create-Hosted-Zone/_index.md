---
title : "Create Hosted Zones"
date : "2025-08-07"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

#### Create Hosted Zones

1. Login to [AWS Console](https://aws.amazon.com/console/)

    - Search for **Route 53**
    - Select **Route 53**

2. In the **Route 53** dashboard

    - Select **Hosted zones**
    - Choose **Create hosted zone**

![CreateHostedZone](/FCJ-Workshop/images/01/CHT1.png?featherlight=false&width=90pc)

3. Configure Hosted zones

    - **Domain name**: enter your registered domain (e.g., workshopkhang.com)
    - **Description**: write your own description (e.g., WorkshopAWS)
    - **Type**: Public hosted zone
    - Enter **Create hosted zone**

![CreateHostedZone](/FCJ-Workshop/images/01/CHT2.png?featherlight=false&width=90pc)

![CreateHostedZone](/FCJ-Workshop/images/01/CHT3.png?featherlight=false&width=90pc)

{{% notice note %}}
After successfully creating the hosted zone, we will copy the **4 NS records** from the newly created hosted zone and paste them into your domain
{{% /notice %}}

![CreateHostedZone](/FCJ-Workshop/images/01/CHT4.png?featherlight=false&width=90pc)

- Under **Registered domains**, choose **Action**, then select **Edit name servers**

![CreateHostedZone](/FCJ-Workshop/images/01/CHT5.png?featherlight=false&width=90pc)

- Proceed to paste the 4 NS records from the created hosted zone, then click Save changes

![CreateHostedZone](/FCJ-Workshop/images/01/CHT6.png?featherlight=false&width=90pc)

![CreateHostedZone](/FCJ-Workshop/images/01/CHT7.png?featherlight=false&width=90pc)