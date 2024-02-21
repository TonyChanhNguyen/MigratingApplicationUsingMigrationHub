---
title : "Create a replication instance "
date : "`r Sys.Date()`"
weight : 3 
chapter : false
pre : " <b> 4.2.3  </b> "
---

Your first task in migrating a database is to create a replication instance that has sufficient storage and processing power to perform the tasks you assign and migrate data from your source database to the target database. The required size of this instance varies depending on the amount of data you need to migrate and the tasks that you need the instance to perform.
1. Go to [Replication instances of Database Migration Service](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#replicationInstances).
2. Click on **Create replication instance**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.1replicationinstances.png?width=89pc)

3. At **Name**, input ```MID-REPINST-WP```.
4. At **Description**, input ```Migration Immersion Day - Rep Inst WordPress```.
5. At **Instance class**, select **dms.t3.medium**.
6. At **Engine version**, select version **3.5.2** or its latest.
7. At **Multi AZ**, select **Dev or Test workload (Single-AZ)**
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.2replicationinstances.png?width=90pc)

8. At **Virtual private cloud (VPC) for IPv4**, select **Source**.
9. At **Replication subnet group**, select **WP-SubnetGroup**.
10. Uncheck **Public accessible**.
11. Expand **Advanced settings**.
12. At **Availability zone**, select **us-west-2a**.
13. At **VPC security groups**, select **default** and **FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXX-SourceSecurityGroup-XXXXXXXXXXXXX**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.3replicationinstances.png?width=90pc)

14. Then, click on **Create replication instance**.
Now, wait for status "Available" in the Replication instance that you just created:
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.3replicationinstances/4.2.3.4replicationinstances.png?width=90pc)