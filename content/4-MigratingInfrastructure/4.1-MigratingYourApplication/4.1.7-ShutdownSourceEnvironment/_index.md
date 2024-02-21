---
title : "Shut down source environment "
date : "`r Sys.Date()`"
weight : 7
chapter : false
pre : " <b> 4.1.7 </b> "
---

In a real-world application migration, once you have completed all of your testing and are ready to fully transition your machines to the cloud, you should perform the shutdown and termination of the source servers and update the DNS records properly to reflect the new servers running in the cloud.

1. From Bastion host,  connect to ofbiz-web and ofbiz-db server using SSH.
2. Shutdown the source servers running in the on-premises environment as per the following instructions:
```
sudo shutdown -h now
```
After the source environment is stopped, all final changes from the source systems are replicated to the Staging area, and we are ready for the final cutover.

3. Go to [Source servers](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#/sourceServers). Note that in the **Alert** column the status will change to **Lagging** after source systems have been shut down.

![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.7shutdown/4.1.7.1shutdown.png?width=90pc)

After a few minutes, both **Alerts** and **Data replication status** columns will change servers' status into **Stalled**. This is expected as we have stopped all source serves and the replication process has been interrupted. However, all the data from source servers is fully synced to the EBS volumes in the **Staging** area, and now the final cutover servers, when launched, will have the latest data from the source systems.

![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.7shutdown/4.1.7.2shutdown.png?width=90pc)