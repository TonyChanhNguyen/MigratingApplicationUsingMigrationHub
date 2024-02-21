---
title : "Cleanup resources "
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
### DMS Tasks
1. Go to [Database migration tasks](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#tasks).
2. Select the tasks that contains **wordpress** in the name, click on **Actions** and **Delete**. After, click **Delete** again to confirm.

### DMS Endpoints
1. Go to [DMS endpoint](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#endpointList).
2. Select all endpoints where name contains **wordpress**, click on **Actions** and **Delete**. After, click **Delete** again to confirm.

### DMS Replication Instances
1. Go to [DMS replication instances](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#replicationInstances).
2. Select all Replication Instances where name starts with **mid** and contains **wordpress**, click on **Actions** and **Delete**. After, click **Delete** again to confirm.

### DMS Subnet Groups
1. Go to [DMS subnet groups](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#subnetGroup).
2. Select all Subnet Groups where name contains **wordpress**, click on **Actions** and **Delete**. After, click **Delete** again to confirm.

### RDS WordPress
1. Go to [RDS](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#databases:).
2. Expand **mid-wordpress** and select the **Writer** instance. After, go to **Actions** and select **Delete**.
3. As this is a lab, we will not create a final snapshot. But, in a real environment, it's a good idea. And then, to confirm the deletion, type ```delete me``` and click delete.

### Onprem EC2 Instances (MGN and DMS)
1. Go to [EC2](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Instances:).
2. Add **MID** , **onpremsim.env** and **MGN** as a filters. Then, select all servers listed by the filter.
3. Click on **Actions**, click on **Instance State** and click on **Terminate**.

### CloudFormation
1. Go to [CloudFormation](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks?filteringText=&filteringStatus=active&viewNested=true).
2. Select stack name **FCJ-MigrationHub-Workshop**, and click **Delete**.
3. If there are some issue, perform manually deletion for each stacks.

### Volume and snapshot
1. Go to [EBS Volume](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Volumes:) and [EBS Snapshot](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#Snapshots:).
2. Select and perform deletion snapshots and volumes created by MGN for the related servers used on this workshop.