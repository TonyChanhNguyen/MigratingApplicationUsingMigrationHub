---
title : "Create Aurora final target database "
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b>  4.2.1 </b> "
---

1. Go to [RDS](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#databases:).
2. Click on **Create database**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.1createaurora.png?width=90pc)

3. At **Choose a database creation method**, choose **Standard create**.
4. At **Engine options**, choose **Aurora (MySQL Compatible)**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.2createaurora.png?width=90pc)

5. At **Available versions**, choose **Aurora(MySQL 5.7)2.11.4** or its latest version.
6. At **Templates**, choose **Dev/Test**.
7. At **DB cluster identifier**, input ```MID-Wordpress```.
8. At **Master username**, input ```admin```.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.3createaurora.png?width=90pc)

9. At **Master password**, input ```12345678```.
10. Repeat password at **Confirm master password**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.4createaurora.png?width=90pc)

11. At **DB instance class**, choose **Burstable classes (includes t classes)**.
12. Change the size to **db.t3.medium**.
13. At **Multi-AZ deployment**, select **Don't create an Aurora Replica**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.5createaurora.png?width=90pc)

14. At **Virtual private cloud (VPC)**, choose **Target** VPC.
15. At **Public access**, select **No**.
16. At **VPC security group (firewall)**, select **Choose existing**.
17. At **Existing VPC security groups**, choose **FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXX-TargetSecurityGroup-XXXXXXXXXXXX** subnet.
18. At **Availability Zone**, choose **us-west-2a**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.6createaurora.png?width=90pc)

19. At **Database authentication option**, select **Password authentication**.
20. At **Monitoring**, uncheck **Enable Enhanced monitoring**.
21. Expand **Additional configuration**, at **Initial database name** set ```wordpressdb```.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.7createaurora.png?width=90pc)

22. At **Encryption**, uncheck **Enable encryption**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.8createaurora.png?width=90pc)

23. Then, click on **Create database**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.9createaurora.png?width=90pc)

24. Wait until the **Available** status.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.10createaurora.png?width=90pc)

25. Click on **wordpressdb Writer** database and write down the endpoint.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.11createaurora.png?width=90pc)

26. From Bastion Host, SSH to server **wordpress-db**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.12createaurora.png?width=90pc)

27. Run the following command to create the wordpress user in your new Aurora database.
```
mysql -u admin -h <AURORA Endpoint> -p
```
+ Password: 12345678

28. Run the following commands to create the user wordpress.
```
CREATE USER 'wordpress'@'%' IDENTIFIED BY '12345678';
GRANT ALL ON wordpressdb.* TO 'wordpress'@'%';
FLUSH PRIVILEGES;
QUIT
```
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.1createaurora/4.2.1.13createaurora.png?width=90pc)
