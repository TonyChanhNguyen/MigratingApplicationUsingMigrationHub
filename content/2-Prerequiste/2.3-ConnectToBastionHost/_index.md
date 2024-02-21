---
title : "Connect to Bastion Host "
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

1. Go to [EC2 instances](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances:instanceState=running).
2. Select instance name **MID-Bastion**.
3. Click on **Connect**.
![Connect Bastion Host](../../images/2.prerequires/2.3connectbastion/2.3.1connectbastion.png?width=90pc)

4. At **Connect to instance** interface, select **RDP client**.
5. Click on **Download remote desktop file**.
6. Click on **Get password**.
![Connect Bastion Host](../../images/2.prerequires/2.3connectbastion/2.3.2connectbastion.png?width=90pc)

 {{%notice warning%}}
Make sure that file name **MID-Bastion.rdp** was downloaded successful.
{{%/notice%}}

7. At **Get Windows password** interface, click on **Upload private key file**.
8. Then, click on **Decrypt password**.
![Connect Bastion Host](../../images/2.prerequires/2.3connectbastion/2.3.3connectbastion.png?width=90pc)

9. Password was generated.
![Connect Bastion Host](../../images/2.prerequires/2.3connectbastion/2.3.4connectbastion.png?width=90pc)

10. Open file **MID-Bastion.rdp** with password above.

Congratulation! You connected to Bastion Host successfully.
