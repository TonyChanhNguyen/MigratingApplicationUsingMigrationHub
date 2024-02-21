---
title : "Specify source and target endpoint "
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4.2.4 </b> "
---
While your replication instance is being created, you can specify the source and target data stores. The source and target data stores can be on an Amazon Elastic Compute Cloud (Amazon EC2) instance, an Amazon Relational Database Service (Amazon RDS) DB instance, or an on-premises database.
### Create Source endpoint
1. Go to [EC2 instances](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances).
2. Filter with ```MID-Wordpress-DB```.
3. Save the **Private IPv4 address**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.1targetendpoint.png?width=90pc)

4. Go to [Endpoint of Database Migration Services](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#endpointList).
5. Click on **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.2targetendpoint.png?width=90pc)

6. At **Endpoint identifier**, input ```SourceWordpress```.
7. At **Source engine**, select **MariaDB**.
8. Click on **Provide Access Information Manually**.
9. At **Server name**, input the IP address that you saved in step 3.
10. At **Port**, enter ```3306```.
11. At **User name**, input ```wordpress```.
12. At **Password**, input ```12345678```.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.3targetendpoint.png?width=90pc)

13. Expand **Test endpoint connection**.
14. At **VPC**, select **Source** VPC.
15. At **Replication Instance**, select **mid-repinst-wp**.
16. Click on **Run test**.
17. After the successful status, click on **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.4targetendpoint.png?width=90pc)

### Create Target endpoint
1. Click on **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.5targetendpoint.png?width=90pc)

2. At **Endpoint type**, select **Target endpoint**. 
3. Check box **Select RDS DB instance**.
4. Select the **RDS Instance** name **mid-wordpress-instance-1**.
5. At **Endpoint identifier**, input ```TargetWordpress```.
6. At **Target engine**, select **Amazon Aurora MySQL**.
7. At **Access to endpoint database**, select **Provide access information manually**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.6targetendpoint.png?width=90pc)

8. At **Password**, input ```12345678```.
9. Expand **Test endpoint connection**.
10. At **VPC**, select **Target** VPC.
11. At **Replication Instance**, select **mid-repinst-wp**.
12. Click on **Run test**.
13. After the successful status, click on **Create endpoint**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.4targetendpoint/4.2.4.7targetendpoint.png?width=90pc)

At the end, you should have 1 Source and 1 Target, in a total of 2 endpoints:
|Type       |Engine                 |
|-----------|-----------------------|
| Source    |MariaDB                |
| Target    |Amazon Aurora MySQL    |
