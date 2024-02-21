---
title : "Tạo một replication instance"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.2.3 </b> "
---
Nhiệm vụ đầu tiên của bạn trong việc dịch chuyển CSDL là tạo một phiên bản nhân bản mà đủ sức mạnh lưu trữ và xử lý các tác vụ bạn chỉ định và dịch chuyển dữ liệu từ CSDL nguồn đến CSDL đích. Kích cỡ yêu cầu của phiên bản này tùy thuộc vào lượng dữ liệu bạn cần dịch chuyển cà các tác vụ mà phiên bản bạn cần thực hiện.
1. Đi đến [Replication instances of Database Migration Service](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#replicationInstances).
2. Nhấn **Create replication instance**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.1replicationinstances.png?width=89pc)

3. Tại **Name**, nhập ```MID-REPINST-WP```.
4. Tại **Description**, nhập ```Migration Immersion Day - Rep Inst WordPress```.
5. Tại **Instance class**, chọn **dms.t3.medium**.
6. Tại **Engine version**, chọn phiên bản **3.5.2** hoặc mới nhất.
7. Tại **Multi AZ**, chọn **Dev or Test workload (Single-AZ)**
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.2replicationinstances.png?width=90pc)

8. Tại **Virtual private cloud (VPC) for IPv4**, chọn **Source**.
9. Tại **Replication subnet group**, chọn **WP-SubnetGroup**.
10. Bỏ chọn **Public accessible**.
11. Mở rộng **Advanced settings**.
12. Tại **Availability zone**, chọn **us-west-2a**.
13. Tại **VPC security groups**, chọn **default** và **FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXX-SourceSecurityGroup-XXXXXXXXXXXXX**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.3replicationinstances.png?width=90pc)

14. Sau đó, nhấn **Create replication instance**.
Bây giờ, chờ trạng thái "Available" trong phiên bản Replication mà bạn vừa tạo:
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.4replicationinstances.png?width=90pc)
