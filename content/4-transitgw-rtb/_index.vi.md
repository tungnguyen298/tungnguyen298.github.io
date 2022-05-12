+++
title = "Tạo Route Table cho TGW"
date = 2020
weight = 4
chapter = false
pre = "<b>4. </b>"
+++
#### Tổng quan

Ở phần này, bạn sẽ tạo Route Table cho Transit Gateway để Transit Gateway biết rằng những **VPC attachment** nào sẵn sàng gửi và đón nhận traffic được phân phối thông qua Transit Gateway.


**Nội dung:**
- [Tạo Transit Gateway Route Tables](#tạo-transit-gateway-route-tables)

#### Tạo Transit Gateway Route Tables
1. Mở **VPC Management Console**, chọn **Transit Gateway Route Tables** ở thanh bên trái, và chọn **Create Transit Gateway Route Table**.

![3_CreateTGWRT](/images/transitgateway/3_Create_TGW_RT.png?width=90pc)


2. Nhập **Name tag** (VD:lab-TGW-RT), chọn transit gateway mà bạn đã tạo, và chọn **Create Transit Gateway Route Table**.

![3_ConfigureTGWRT](/images/transitgateway/3_Config_TGW_RT.png?width=90pc)

3. Sau khi Route table trở nên sẵn sàng, tick vào route table chúng ta mới tạo, chọn tab **Associations**, và nhấn **Create association**.

![4_CreateAssociation](/images/transitgateway/4_Create_TGW_Associations.png?width=90pc)

5. Lần lượt đính từng VPC. Quá trình association báo Transit Gateway biết route table của VPC nào sẽ gửi các data packet tới Transit Gateway.

![4_Config Associations](/images/transitgateway/4_Config_TGW_Associations.png?width=90pc)

![4_AllAss](/images/transitgateway/4_Attached_VPC.png?width=90pc)

6. Sau đó chuyển qua tab **Propagations**, nhấn **Create propagation**. 

![4_CreatePropagation](/images/transitgateway/4_Create_Propagations.png?width=90pc)

7. Lần lượt đính từng VPC. Quá trình propagation báo Transit Gateway biết route table của VPC nào sẽ nhận các data packet từ Transit Gateway.

![4_CreatePropagation](/images/transitgateway/4_Config_TGW_Propagations.png?width=90pc)

![4_AllPro](/images/transitgateway/4_Attached_VPC_Propagations.png?width=90pc)

