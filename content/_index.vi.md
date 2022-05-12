+++
title = "Thiết lập Transit Gateway"
date = 2020
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

# Thiết lập Transit Gateway

#### Tổng quan

Ở bài lab này, bạn sẽ triển khai kiến trúc sau để kết nối bốn VPC với nhau qua **AWS Transit Gateway**:

![Image](/images/transitgateway/Transit_Gateway.png?width=40pc)

Ở bài lab [Thiêt lập VPC Peering](https://000019.awsstudygroup.com/vi/), bạn đã được thực hành thiết lập một **Peering Connection** giữa hai VPC. Bây giờ, hãy tưởng tượng bạn có tận bốn VPC muốn kết nối với nhau, vậy bạn cần bao nhiêu Peering Connection?

![Image](/images/transitgateway/0-NoTGW.png?width=30pc)

**Đáp án**: Bạn cần tới tận 6 Peering Connection để kết nối 4 VPC với nhau. Hãy thử tưởng tượng bạn cần kết nối sáu, tám, hoặc thậm chí mười VPC với nhau. Từ đó, bạn nhận ra được rằng phương pháp kết nối Peering Connection không có khả năng mở rộng cao.



#### AWS Transit Gateway (AWS TGW)

Để giải quyết giới hạn của Peering Conenction, **AWS Transite Gateway** được dùng để kết nối các VPC và mạng on-premises thông qua một hub trung tâm. Điều này đơn giản hoá mạng và kết thúc các mối quan hệ định tuyến phức tạp. Nó hoạt động như một cloud router - mỗi kết nối mới chỉ thực hiện 1 lần.


#### AWS Transit Gateway Attachment
**AWS Transit Gateway Attachment** là một công cụ để gán các subnet của từng VPC cần kết nối với nhau vào một TGW đã được khởi tạo. **Transit Gateway Attachment** hoạt động dựa trên quy mô của Availability Zone (*AZ-level*). Trong VPC, khi một subnet ở một AZ có **Transit Gateway Attachment** với một TGW, các subnet khác trong cùng AZ đều có thể kết nối tới TGW đó.

{{% notice warning %}}
Bài lab này sẽ dẫn đến các khoản phí cho account AWS của bạn. Instance sẽ chạy tất cả đều là **t3.nano**. Ngoài ra, bài lab còn có những phí liên quan đến Transit Gateway. Do đó, bạn sẽ phải xoá lab template ở cuối lab để tránh những chi phí phát sinh.
{{% /notice %}}

#### Nội dung

- [1. Thiết lập Hạ tầng](1-infrastructure/)
- [2. Tạo Transit Gateway](2-create-transitgw/)
- [3. Tạo Transit Gateway Attachments](3-transitgw-attachment/)
- [4. Tạo Transit Gateway Route Tables](4-transitgw-rtb/)
- [5. Thêm Transit Gateway Routes vào VPC Route Tables](5-attach-rtb/)
