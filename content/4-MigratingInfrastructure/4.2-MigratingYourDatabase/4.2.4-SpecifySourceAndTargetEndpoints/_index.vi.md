---
title : "Chỉ định endpoint của source và target"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.2.4  </b> "
---
Trong khi phiên bản Replication của bạn đang được tạo, bạn có thể chỉ định nơi lưu trữ dữ liệu nguồn và đích. Nơi lưu trữ dữ liệu nguồn và đích  có thể nằm trong phiên bản Amazon Elastic Compute Cloud (Amazon EC2), một phiên bản CSDL Amazon Relational Database Service (Amazon RDS), hoặc CSDL tại chỗ
### Tạo điểm cuối nguồn
1. Đi đến [EC2 instances](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances).
2. Lọc với ```MID-Wordpress-DB```.
3. Lưu **Private IPv4 address**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.1targetendpoint.png?width=90pc)

4. Đi đến [Endpoint of Database Migration Services](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#endpointList).
5. Nhấn **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.2targetendpoint.png?width=90pc)

6. Tại **Endpoint identifier**, nhập ```SourceWordpress```.
7. Tại **Source engine**, chọn **MariaDB**.
8. Nhấn **Provide Access Information Manually**.
9. Tại **Server name**, nhập địa chỉ IP mà bạn đã lưu ở bước 3.
10. Tại **Port**, nhập ```3306```.
11. Tại **User name**, nhập ```wordpress```.
12. Tại **Password**, nhập ```12345678```.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.3targetendpoint.png?width=90pc)

13. Mở rộng **Test endpoint connection**.
14. Tại **VPC**, chọn **Source** VPC.
15. Tại **Replication Instance**, chọn **mid-repinst-wp**.
16. Nhấn **Run test**.
17. Sau khi trạng thái thành công, nhấn **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.4targetendpoint.png?width=90pc)

### Create Target endpoint
1. Nhấn **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.5targetendpoint.png?width=90pc)

2. Tại **Endpoint type**, chọn **Target endpoint**. 
3. Tích chọn **Select RDS DB instance**.
4. Chọn **RDS Instance** tên **mid-wordpress-instance-1**.
5. Tại **Endpoint identifier**, nhập ```TargetWordpress```.
6. Tại **Target engine**, chọn **Amazon Aurora MySQL**.
7. Tại **Access to endpoint database**, chọn **Provide access information manually**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.6targetendpoint.png?width=90pc)

8. Tại **Password**, nhập ```12345678```.
9. Mở rộng **Test endpoint connection**.
10. Tại **VPC**, chọn **Target** VPC.
11. Tại **Replication Instance**, chọn **mid-repinst-wp**.
12. Nhấn **Run test**.
13. Sau khi trạng thái thành công, nhấn **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.7targetendpoint.png?width=90pc)

Cuối cùng, bạn sẽ có 1 Source và 1 Target, trong tổng số 2 điểm cuối:
|Type       |Engine                 |
|-----------|-----------------------|
| Source    |MariaDB                |
| Target    |Amazon Aurora MySQL    |

