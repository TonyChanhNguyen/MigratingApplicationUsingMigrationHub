---
title : "Tải ADS Agent cho VMs"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2 </b> "
---

1. Đăng nhập vào máy chủ Bastion Host giống bước 10 của [Kết nối máy chủ Bastion Host](./2.3-connecttobastionhost/). Sử dụng Putty trong màn hình máy chủ Bastion host để kết nối tới mỗi máy chủ:
|Application        |FQDN                          |OS      |Username   |Password |
|-------------------|------------------------------|--------|-----------|---------|
| wordpress-web     |wordpress-web.onpremsim.env   |Centos7 |user       |12345678 |
| wordpress-db      |wordpress-db.onpremsim.env    |Centos7 |user       |12345678 |
| ofbiz-web         |ofbiz-web.onpremsim.env       |Centos7 |user       |12345678 |
| ofbiz-db          |ofbiz-db.onpremsim.env        |Centos7 |user       |12345678 |

2. Nhập FQDn của máy chủ, sau đó nhấn **Open**
![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.1installads.png?width=90pc)

3. Nhập user name **user** và password **12345678** (Root password bạn đã nhập khi tạo mẫu CloudFormation).
![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.2installads.png?width=90pc)

4. Tải xuống và cài đặt agents theo hướng dẫn sau:
```
curl -o ./aws-discovery-agent.tar.gz https://s3-us-west-2.amazonaws.com/aws-discovery-agent.us-west-2/linux/latest/aws-discovery-agent.tar.gz
tar -xzf aws-discovery-agent.tar.gz
sudo bash install -r "us-west-2" -k "<AWS key id>" -s "<AWS key secret>"
```
 {{%notice info%}}
Thay thế < AWS key id > và < AWS key secret > với thông tin đã tải xuống ở bước tạo chứng thực cho ADS user.
{{%/notice%}}
![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.3installads.png?width=90pc)

5. Lặp lại bước này với tất cả máy chủ để cài đặt agent.

6. Khi bạn đã cài Discovery Agent, thu thập dữ liệu sẽ khởi chạy tự động. Bạn có thể kiểm tra trạng thái thu thập và các thông tin khác tại  [Discovery Agents tab of Data Collectors page of Migration Hub console](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/discover/datacollectors?type=agent&filter=collectionStatus%2B%3D%2BSTARTED).
 {{%notice info%}}
Sẽ mất khoảng vài phút cho agents xuất hiện.
{{%/notice%}}

![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.4installads.png?width=90pc)