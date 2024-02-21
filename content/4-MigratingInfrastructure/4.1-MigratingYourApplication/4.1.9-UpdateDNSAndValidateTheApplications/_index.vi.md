---
title : "Cập nhật DNS và xác nhận các ứng dụng"
date :  "`r Sys.Date()`" 
weight : 9 
chapter : false
pre : " <b> 4.1.9 </b> "
---
Hiện tại các máy chủ nguồn OFbiz đã tắt, đây là thời điểm để cập nhật bản ghi DNS để phản ánh tất cả máy chủ mới vừa được dịch chuyển. Trong bài thực hành này chúng ta sử dụng máy chủ chạy một phiên bản Unix được đặt tên là trình phân giải DNS.
1. Đi đến [EC2 instances](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances:instanceState=running).
2. Lọc ```ofbiz```, và **Instance state** là **running**.
3. Lưu **Private IPv4 addresses** của 2 máy chủ **ofbiz-db.onpremsim.env** và **ofbiz-web.onpremsim.env**.
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.1dns.png?width=90pc)

4. Từ Bastion host, sử dụng Putty để kết nối tới địa chỉ mới.
+ Đăng nhập: user
+ Mật khẩu: 12345678
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.2dns.png?width=90pc)

5. Chạy các dòng lệnh dưới đây để cập nhật bản ghi DNS:
```
ADDR=`hostname -I`
HOST=`hostname`
sudo touch /tmp/nsupdate.txt
sudo chmod 666 /tmp/nsupdate.txt
echo "server dns.onpremsim.env" > /tmp/nsupdate.txt
echo "update delete $HOST A" >> /tmp/nsupdate.txt
echo "update add $HOST 86400 A $ADDR" >> /tmp/nsupdate.txt
echo "update delete $HOST PTR" >> /tmp/nsupdate.txt
echo "update add $HOST 86400 PTR $ADDR" >> /tmp/nsupdate.txt
echo "send" >> /tmp/nsupdate.txt
sudo nsupdate /tmp/nsupdate.txt
```

![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.3dns.png?width=90pc)

6. Lập lại quy trình cập nhật DNS với các máy chủ còn lại.

![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.4dns.png?width=90pc)

7. Sử dụng **Windows PowerShell** của Bastion Host để chạy những dòng lệnh này để thực hiện kiểm tra DNS mới của các máy chủ.
```
nslookup ofbiz-web.onpremsim.env
nslookup ofbiz-db.onpremsim.env
```
![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.5dns.png?width=90pc)

Bạn có thể thấy, địa chỉ IP trả về là Private IP Address của mỗi máy chủ.

8. Bây giờ bạn có thể kiểm tra ứng dụng OfBiz vừa được dịch chuyển. Bạn có thể chạy trên AWS hiện tại. Truy câho Chrom với đường dẫn sau.
+ URL: https://ofbiz-web.onpremsim.env:8443/accounting 
+ App username: admin
+ App password: ofbiz

![Migrating your application](../../../../images/4.migrateinfra/4.1migrateapp/4.1.9dns/4.1.9.6dns.png?width=90pc)
