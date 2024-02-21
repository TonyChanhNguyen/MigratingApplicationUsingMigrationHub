---
title : "Create replication subnet groups "
date : "`r Sys.Date()`"
weight : 2 
chapter : false
pre : " <b> 4.2.2  </b> "
---

To be able to launch a DMS Replication instance, it is necessary to specify what subnet group in the VPC the Replication instance will run. A subnet is a range of IP addresses in your VPC in a given Availability Zone. These subnets can be distributed among the Availability Zones for the AWS Region where your VPC is located. DMS Replication instance requires at least two Availability Zones. The following step will demonstrate how to create the subnet group in 2 Availability Zones.

1. Go to [Subnet Groups of Database Migration Service](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#subnetGroup).
2. Click on **Create subnet group**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.2subnetgroup/4.2.2.1subnetgroup.png?width=90pc)

3. At **Name**, input ```WP-SubnetGroup```.
4. At **Description**, input ```Migration Immersion Day - WordPress Subnet Group```.
5. At **VPC**, select **Source** VPC.
6. At **Add subnets**, select **SourcePrivate** and **SourcePrivateDB**.
7. Then, click on **Create subnet group**.
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.2subnetgroup/4.2.2.2subnetgroup.png?width=90pc)

Now, you have 1 subnet groups created:
![Migrate your database](/images/4.migrateinfra/4.2migratedb/4.2.2subnetgroup/4.2.2.3subnetgroup.png?width=90pc)
