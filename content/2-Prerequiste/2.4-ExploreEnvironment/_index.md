---
title : "Explore environment "
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

The current production environment running on-premise is comprised of 2 applications and 4 servers as per the following: 
|Application |Hostname       |FQDN                          |OS      |Platform   |
|------------|---------------|------------------------------|--------|-----------|
| Wordpress  |wordpress-web  |wordpress-web.onpremsim.env   |Centos7 |Apache+PHP |
| Wordpress  |wordpress-db   |wordpress-db.onpremsim.env    |Centos7 |MariaDB    |
| OFBiz      |ofbiz-web      |ofbiz-web.onpremsim.env       |Centos7 |Java       |
| OFBiz      |ofbiz-db       |ofbiz-db.onpremsim.env        |Centos7 |PostgreSQL |

1. Test the applications that we’re going to migrate. In the Bastion Host, open the following URL using Chrome browser.
|Application |URL                                                   |
|------------|------------------------------------------------------|
| Wordpress  |	http://wordpress-web.onpremsim.env/                 |
| OFBiz ERP  |https://ofbiz-web.onpremsim.env:8443/accounting       |

2. You should be able to visualize these 2 web applications:
###[Wordpress
![Explore environment](../../images/2.prerequires/2.4exploreenv/2.4.1exploreenv.png?width=90pc)

### OFBiz
![Explore environment](../../images/2.prerequires/2.4exploreenv/2.4.2exploreenv.png?width=90pc)
You can log into the OFBiz application using the following username and password:
|Application |Test URL                                              |App username  |App password |
|------------|------------------------------------------------------|--------------|-------------|
| OFBiz ERP  |	https://ofbiz-web.onpremsim.env:8443/accounting     |admin         |ofbiz        |


