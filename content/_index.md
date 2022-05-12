+++
title = "Thiết lập Transit Gateway"
date = 2020
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

# Thiết lập Transit Gateway

#### Tổng quan

In this part, you will set up the network infrastructure with CloudFormation Template for the lab with the following architecture: **AWS Transit Gateway**:

![Image](/images/transitgateway/Transit_Gateway.png?width=40pc)

In previous labs [Thiêt lập VPC Peering](https://000019.awsstudygroup.com/vi/), we have configured **Peering Connection** between 2 VPC. Now, if we want to connect 4 VPCs together, How many peering connection will we need       ?

![Image](/images/transitgateway/0-NoTGW.png?width=30pc)

**Answer**: You will need 6 Peering Conneection to connect 4 VPCs together. In case, you need to connect 6, 4 or 10 VPCs. you will see that Peering Connection is not highly scalable



#### AWS Transit Gateway (AWS TGW)

To resolve limitation of Peering Connection, **AWS Transite Gateway** used to connect VPCs and on-premises networks through a central hub. This simplifies the network and ends complex routing. It works like a cloud router - each new connection is made only 1.


#### AWS Transit Gateway Attachment
**AWS Transit Gateway Attachment** is a tool to assign the subnets of each VPC to be connected to an initialized TGW. **Transit Gateway Attachment** operates on the scale of Availability Zone (*AZ-level*). In VPC, when a subnet in an AZ has a **Transit Gateway Attachment** with a TGW, other subnets in the same AZ can connect to that TGW.

{{% notice warning %}}
This lab will cost your AWS account fees. Instance version should be **t3.nano**. In addition, the lab has cost associated with Transit Gateway. Therefore, you have to delete the lab template at the end of the lab to avoid additional costs
{{% /notice %}}

#### Nội dung

- [1. Setting Up Infrastructure](1-infrastructure/)
- [2. Create Transit Gateway](2-create-transitgw/)
- [3. Create Transit Gateway Attachments](3-transitgw-attachment/)
- [4. Create Transit Gateway Route Tables](4-transitgw-rtb/)
- [5. Assign Transit Gateway Routes to VPC Route Tables](5-attach-rtb/)
