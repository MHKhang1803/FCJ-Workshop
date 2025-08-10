---
title : "Clean up resource"
date : "2025-08-07"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

#### Delete Health Check

- Access **Route 53** → **Health checks**
- Select the health checks you created → Delete

![Cleanup](/images/02/CR1.png?featherlight=false&width=90pc)

#### Delete the DNS record in the Hosted Zone

- Access **Route 53** → **Hosted zones**
- Go to your domain 
- Select and delete the Weighted, Failover, and Geolocation records you created

![Cleanup](/images/02/CR2.png?featherlight=false&width=90pc)

#### Delete Hosted Zone

- Only delete this if you no longer need to use the domain/zone

![Cleanup](/images/02/CR3.png?featherlight=false&width=90pc)

#### Terminate EC2 instance

{{% notice note %}}
Clean up in both the Singapore and Virginia regions
{{% /notice %}}

1. Access the **EC2** dashboard
2. Navigate to **Instances**
3. Select the instances associated with the workshop
4. Click on **Instance state**
5. Select **Terminate instance**

![Cleanup](/images/02/CR4.png?featherlight=false&width=90pc)

![Cleanup](/images/02/CR5.png?featherlight=false&width=90pc)

#### Delete Security group

{{% notice note %}}
Clean up in both the Singapore and Virginia regions 
{{% /notice %}}

1. Access the **EC2** dashboard
2. Go to **Security Groups** in the left navigation pane
3. Select the security groups associated with the workshop
4. Click on **Actions**
5. Select **Delete security group**

![Cleanup](/images/02/CR6.png?featherlight=false&width=90pc)

#### Delete Key Pair

{{% notice note %}}
Clean up in both the Singapore and Virginia regions 
{{% /notice %}}

1. Access the **EC2** dashboard
2. Navigate to **Key Pairs** in the left navigation pane
3. Select the key pair used for the workshop
4. Click on **Actions**
5. Select **Delete**

![Cleanup](/images/02/CR7.png?featherlight=false&width=90pc)