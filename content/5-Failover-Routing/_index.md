---
title : "Failover Routing"
date : "2025-08-07"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

#### Configure Failover Routing

1. Login to [AWS Console](https://aws.amazon.com/console/)

    - Search for **Route 53**
    - Select **Route 53**

2. In the **Route 53** dashboard

    - Select **Hosted zones** you've created
    - Choose **Create records**

![FailoverRouting](/static/images/2/CWT1.png?featherlight=false&width=90pc)

![FailoverRouting](/static/images/2/CWT2.png?featherlight=false&width=90pc)

{{% notice note %}}
Delete the other record types because Route 53 only allows one record with a matching Name/Type, then proceed to create the new record.
{{% /notice %}}

3. Create 2 A Records with a Routing Policy of Failover

- Record 1: Singapore

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address of the EC2 in Singapore
   - **TTL** : 300
   - **Routing Policy**: Failover
   - **Failover record type**: Primary
   - **Health check ID**: Choose Singapore Health check
   - **Record ID**: SG-Failover
   - Enter **Create records**

![FailoverRouting](/static/images/2/CFL1.png?featherlight=false&width=90pc)

- Record 2: Virginia

   - **Record name**: www
   - **Record type**: A
   - **Value**: Public IPv4 address of the EC2 in Virginia
   - **TTL** : 300
   - **Routing Policy**: Failover
   - **Failover record type**: Secondary
   - **Health check ID**: Choose Virginia Health check
   - **Record ID**: VG-Failover
   - Enter **Create records**

![FailoverRouting](/static/images/2/CFL2.png?featherlight=false&width=90pc)

{{% notice note %}}
To quickly test this, visit the domain (e.g., http://www.workshopkhang.com). You'll see the Singapore homepage, as we set Singapore's failover record type as Primary, making it the main server.
{{% /notice %}}

4. Test

- Objective: When the Singapore server becomes "unresponsive" (unhealthy/unavailable), Route 53 will automatically failover to the Virginia server
- Steps:

  - Connect to the EC2 Singapore instance via SSH using MobaXterm

![FailoverRouting](/static/images/2/CFL3.png?featherlight=false&width=90pc)

  - Stop the web server (Apache) on the EC2 Singapore instance using the command: `sudo systemctl stop httpd`

![FailoverRouting](/static/images/2/CFL4.png?featherlight=false&width=90pc)

  - Wait for approximately 1-2 minutes (depending on your Health Check time and fail threshold). Route 53 will then detect that the Singapore server is unhealthy and reroute traffic to Virginia

![FailoverRouting](/static/images/2/CFL6.png?featherlight=false&width=90pc)

  - Access the domain again (e.g., http://www.workshopkhang.com). If the configuration is correct, you will see the web server from Virginia

![FailoverRouting](/static/images/2/CFL5.png?featherlight=false&width=90pc)

{{% notice note %}}
After the test is complete, you can restart Apache in Singapore to restore normal system operation by entering the command `sudo systemctl start httpd`
{{% /notice %}}

![FailoverRouting](/static/images/2/CFL7.png?featherlight=false&width=90pc)

- Route 53 will automatically fail back to Singapore once the Health Check detects that the server is healthy

![FailoverRouting](/static/images/2/CFL8.png?featherlight=false&width=90pc)