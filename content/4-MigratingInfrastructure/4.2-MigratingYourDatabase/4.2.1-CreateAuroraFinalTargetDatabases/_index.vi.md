---
title : "Tạo cơ sở dữ liệu target Aurora cuối cùng"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.2.1 </b> "
---

1. Đi đến [RDS](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#databases:).
2. Nhấn **Create database**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.1createaurora.png?width=90pc)

3. Tại **Choose a database creation method**, chọn **Standard create**.
4. Tại **Engine options**, chọn **Aurora (MySQL Compatible)**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.2createaurora.png?width=90pc)

5. Tại **Available versions**, chọn **Aurora(MySQL 5.7)2.11.4** hoặc phiên bản mới nhất.
6. Tại **Templates**, chọn **Dev/Test**.
7. Tại **DB cluster identifier**, nhập ```MID-Wordpress```.
8. Tại **Master username**, nhập ```admin```.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.3createaurora.png?width=90pc)

9. Tại **Master password**, nhập ```12345678```.
10. Nhập lại mật khẩu tại **Confirm master password**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.4createaurora.png?width=90pc)

11. Tại **DB instance class**, chọn **Burstable classes (includes t classes)**.
12. Chuyển kích cỡ thành **db.t3.medium**.
13. Tại **Multi-AZ deployment**, chọn **Don't create an Aurora Replica**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.5createaurora.png?width=90pc)

14. Tại **Virtual private cloud (VPC)**, chọn **Target** VPC.
15. Tại **Public access**, chọn **No**.
16. Tại **VPC security group (firewall)**, chọn **Choose existing**.
17. Tại **Existing VPC security groups**, chọn lớp mạng con **FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXX-TargetSecurityGroup-XXXXXXXXXXXX**.
18. Tại **Availability Zone**, chọn **us-west-2a**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.6createaurora.png?width=90pc)

19. Tại **Database authentication option**, chọn **Password authentication**.
20. Tại **Monitoring**, bỏ chọn **Enable Enhanced monitoring**.
21. Mở rộng **Additional configuration**, tại **Initial database name** nhập ```wordpressdb```.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.7createaurora.png?width=90pc)

22. Tại **Encryption**, bỏ chọn **Enable encryption**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.8createaurora.png?width=90pc)

23. Sau đó, nhấn **Create database**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.9createaurora.png?width=90pc)

24. Chờ đến khi trạng thái **Available**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.10createaurora.png?width=90pc)

25. Nhấn CSDL **wordpressdb Writer** và lưu lại endpoint.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.11createaurora.png?width=90pc)

26. Từ Bastion Host, SSH đến máy chủ **wordpress-db**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.12createaurora.png?width=90pc)

27. Chạy các dòng lệnh sau để tạo người dùng wordpress trong CSDL Aurora mới của bạn.
```
mysql -u admin -h <AURORA Endpoint> -p
```
+ Password: 12345678

28. Chạy các dòng lệnh sau để tạo người dùng wordpress.
```
CREATE USER 'wordpress'@'%' IDENTIFIED BY '12345678';
GRANT ALL ON wordpressdb.* TO 'wordpress'@'%';
FLUSH PRIVILEGES;
QUIT
```
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.13createaurora.png?width=90pc)

