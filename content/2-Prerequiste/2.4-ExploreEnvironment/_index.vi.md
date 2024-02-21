---
title : "Khám phá môi trường"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

Môi trường sản phẩm chạy trên on-premise hiện tại bao gồm 2 ứng dụng và 4 máy chủ sau đây:
|Application |Hostname       |FQDN                          |OS      |Platform   |
|------------|---------------|------------------------------|--------|-----------|
| Wordpress  |wordpress-web  |wordpress-web.onpremsim.env   |Centos7 |Apache+PHP |
| Wordpress  |wordpress-db   |wordpress-db.onpremsim.env    |Centos7 |MariaDB    |
| OFBiz      |ofbiz-web      |ofbiz-web.onpremsim.env       |Centos7 |Java       |
| OFBiz      |ofbiz-db       |ofbiz-db.onpremsim.env        |Centos7 |PostgreSQL |

1. Kiểm tra các ứng dụng mà chúng ta dự định dịch chuyển. Tại Bastion Host, mở đường dẫn sau đây bằng trình duyệt Chrome:
|Application |URL                                                   |
|------------|------------------------------------------------------|
| Wordpress  |	http://wordpress-web.onpremsim.env/                 |
| OFBiz ERP  |https://ofbiz-web.onpremsim.env:8443/accounting       |

2. Bạn sẽ có thể hình dung được 2 ứng dụng web này: 
### Wordpress
![Explore environment](/images/2.prerequires/2.4exploreenv/2.4.1exploreenv.png?width=90pc)

### OFBiz
![Explore environment](/images/2.prerequires/2.4exploreenv/2.4.2exploreenv.png?width=90pc)
Bạn có thể đăng nhập vào ứng dụng OFBiz sử dụng username và password dưới đây:
|Application |Test URL                                              |App username  |App password |
|------------|------------------------------------------------------|--------------|-------------|
| OFBiz ERP  |	https://ofbiz-web.onpremsim.env:8443/accounting     |admin         |ofbiz        |



