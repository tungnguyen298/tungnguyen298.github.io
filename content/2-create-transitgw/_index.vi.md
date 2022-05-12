+++
title = "Tạo Transit Gateway"
date = 2020
weight = 2
chapter = false
pre = "<b>2. </b>"
+++
#### Tổng quan
Trong phần này, bạn sẽ tạo một **Transit Gateway** trên AWS Cloud. 

![2_Infra](/images/transitgateway/2_Infra.png?width=40pc)


**Nội dung:**
- [Tạo Transit Gateway](#tạo-transit-gateway)

#### Tạo Transit Gateway
1. Mở **VPC Management Console**, chọn **Transit Gateway** ở thanh bên trái, và chọn **Create Transit Gateway**.

![2_CreateTGW](/images/transitgateway/2_Create_TGW.png?width=90pc)

2. Ở trang **Create Transit Gateway**, nhập những thông số sau:
    - Name tag: **lab-tgw**
    - Description: **Transit Gateway**
    - Configure the Transit Gateway: bỏ chọn các cấu hình **Default route table association** và **Default route table propagation**.
{{% notice note %}}
Chúng ta sẽ thực hiện thủ công những cấu hình đã bỏ chọn để hiểu hơn về cách hoạt động của Route Table ở phần sau.
{{% /notice %}}

3. Kiểm tra và chọn **Create Transit Gateway**.

![2_ConfigureTGW](/images/transitgateway/2_Config_TGW.png?width=90pc)

4. Sẽ mất 1-2 phút để **Transit Gateway** trở nên sẵn sàng

