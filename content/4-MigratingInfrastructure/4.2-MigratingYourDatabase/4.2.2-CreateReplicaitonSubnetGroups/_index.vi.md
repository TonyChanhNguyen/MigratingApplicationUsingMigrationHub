---
title : "Tạo replication subnet groups"
date :  "`r Sys.Date()`" 
weight : 2  
chapter : false
pre : " <b> 4.2.2  </b> "
---

Để có thể khởi chạy một DMS Replication, cần chỉ định nhóm mạng con nào trong VPC mà phiên bản Replication sẽ chạy. Mạng con là một dải địa chỉ IP trong VPC của bạn trong Availability Zone nhất định. Các mạng con này có thể được phân phối giữa các Availability Zones cho the AWS Region nơi đặt VPC của bạn. Phiên bản DMS Replication yêu cầu ít nhất hai Availability Zones. Bước sau đây sẽ trình bày cách tạo nhóm mạng con trong 2 Availability Zones.

1. Đi đến [Subnet Groups of Database Migration Service](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#subnetGroup).
2. Nhấn **Create subnet group**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.2subnetgroup/4.2.2.1subnetgroup.png?width=90pc)

3. Tại **Name**, nhập ```WP-SubnetGroup```.
4. Tại **Description**, nhập ```Migration Immersion Day - WordPress Subnet Group```.
5. Tại **VPC**, chọn **Source** VPC.
6. Tại **Add subnets**, chọn **SourcePrivate** và **SourcePrivateDB**.
7. Sau đó, nhấn **Create subnet group**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.2subnetgroup/4.2.2.2subnetgroup.png?width=90pc)

Bây giờ, bạn có một nhóm lớp mạng con được tạo:
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.2subnetgroup/4.2.2.3subnetgroup.png?width=90pc)
