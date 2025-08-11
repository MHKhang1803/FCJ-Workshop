---
title : "Create Health checks"
date : "2025-08-07"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

{{% notice note %}}
Proceed to create 2 Health checks in 2 regions, first in **Singapore**
{{% /notice %}}

#### Create Health checks

1. Login to [AWS Console](https://aws.amazon.com/console/)

    - Search for **Route 53**
    - Select **Route 53**

2. In the **Route 53** dashboard

    - Select **Health checks**
    - Choose **Create health check**

![CreateHealthcheck](/images/01/CHC1.png?featherlight=false&width=90pc)

3. Configure Health checks

    - **Name**: `SGHealthCheck`
    - **Resource**: Endpoint
    - **Specify endpoint by**: IP address
    - **IP address**: HTTP, then enter the **Public IPv4 address** of the EC2 instance in the Singapore region
    - Enter **Create Health check**

![CreateHealthcheck](/images/01/CHC2.png?featherlight=false&width=90pc)

![CreateHealthcheck](/images/01/CHC3.png?featherlight=false&width=90pc)

![CreateHealthcheck](/images/01/CHC4.png?featherlight=false&width=90pc)

{{% notice note %}}
Similarly, proceed to create Health checks in the **Virginia** region
{{% /notice %}}

- Configure Health checks
  
    - **Name**: `VGHealthCheck`
    - **Resource**: Endpoint
    - **Specify endpoint by**: IP address
    - **IP address**: HTTP, then enter the **Public IPv4 address** of the EC2 instance in the Virginia region
    - Enter **Create Health check**

![CreateHealthcheck](/images/01/CHC5.png?featherlight=false&width=90pc)

![CreateHealthcheck](/images/01/CHC6.png?featherlight=false&width=90pc)

![CreateHealthcheck](/images/01/CHC7.png?featherlight=false&width=90pc)