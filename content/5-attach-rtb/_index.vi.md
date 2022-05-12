+++
title = "Thêm Gateway vào Route Tables & Kiểm tra kết quả"
date = 2020
weight = 5
chapter = false
pre = "<b>5. </b>"
+++
#### Tổng quan

Ở phần này, bạn sẽ cấu hình route table ở từng VPC để route traffic tới các VPC còn lại thông qua Transit Gateway.

**Nội dung:**
- [Thêm Transit Gateway Routes vào VPC Route Tables](#thêm-transit-gateway-routes-vào-vpc-route-tables)
- [Kiểm tra kết quả](#kiểm-tra-kết-quả)

#### Thêm Transit Gateway Routes vào VPC Route Tables
1. Mở **VPC Management Console**, chọn **Route Tables** ở thanh bên trái. Chúng ta quy ước rằng:
    - First VPC Main Route Table = Route Table của VPC1
    - Second VPC Main Route Table = Route Table của VPC2
    - Third VPC Main Route Table = Route Table của VPC3
    - Fourth VPC Main Route Table = Route Table của VPC4

2. Với Route Table của VPC1 và VPC3, chọn **Edit routes** để thêm route với thông số sau:
    - Destination: **172.16.0.0/16**
    - Target: chọn Transit Gateway bạn dã tạo.  

{{% notice note %}}
Điều này cho VPC1 và VPC3 biết rằng tất cả packet cho bất kỳ mạng 172.16.x.x nào đều thông qua Transit Gateway.
{{% /notice %}}

![5_Route13](/images/transitgateway/5_Route13.png?width=90pc)

3. Tương tự với Route Table của VPC2 và VPC4, chọn **Edit routes** để thêm route với thông số sau:
    - Destination: **0.0.0.0/0**
    - Target: chọn Transit Gateway bạn đã tạo

![5_Route24](/images/transitgateway/5_Route24.png?width=90pc)

{{% notice note %}}
Điều này cho VPC2 và VPC4 biết rằng tất cả packet cho bất kỳ mạng nào khác ngoài mạng local đều thông qua Transit Gateway.
{{% /notice %}}

Như vậy, bạn đã hoàn thành công tác cấu hình cho phép bốn VPC liên lạc với nhau thông qua Transit Gateway. Hãy cùng kiểm tra xem các EC2 instance từ VPC1 và VPC3 có thể kết nối tới các EC2 instance ở VPC2 và VPC4 không nhé!

#### Kiểm tra kết quả

1. Kết nối SSH đến EC2 instance ở VPC1 và xác thực bạn có thể ping www.amazon.com để xác thực kiểm tra kết nối internet

![5_InternetPing](/images/transitgateway/5_Internet_Ping.png?width=90pc)

2. Ping đến IP của EC2 instance trong VPC2.

![5_VPC2Ping](/images/transitgateway/5_VPC2_Ping.png?width=90pc)

3. Sử dụng Key Pair bạn đã copy vào instance ở phần trước, kết nối SSH từ EC2 instance ở VPC1 tới EC2 instance ở VPC2 bằng các câu lệnh:
    - ```chmod 400 AP-SE-key.pem``` để ngăn không người dùng công cộng xem được Key Pair trong instance. Đây là điều kiện an ninh tiên quyết để sử dụng Key Pair.
    - ```ssh -i "<YourKey.pem>" ec2-user@<YourEC2IP>``` để kết nối SSH tới EC2 instance từ Terminal

![5_VPC2SSH](/images/transitgateway/5_VPC2_SSH.png?width=90pc)

4. Lần lượt ping vào địa chỉ IP Private của EC2 instance ở VPC3 và VPC4


![5_PingSuccess](/images/transitgateway/5_Ping_Success_1.png?width=60pc)


Chúc mừng!!! Các EC2 Instance ở các VPC của bạn đã có thể kết nối với nhau thông qua Transit Gateway.

