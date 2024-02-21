---
title : "Finalize cutover and archive servers "
date : "`r Sys.Date()`"
weight : 10
chapter : false
pre : " <b> 4.1.10 </b> "
---

### Finalize the cutover
When the cutover process is completed and you no longer need the replicated data in the Staging area, you can finalize the cutover. This will remove all the resources created during the migration and clean up the Staging area.

1. Go to [Source servers](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#/sourceServers).
2. Select two servers.
3. Click on **Test and cutover**.
4. Choose **Finalize cutover**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.1cutover.png?width=90pc)

5. Click on **Finalize**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.2cutover.png?width=90pc)

6. The **Migration lifecycle** status changed to **Cutover complete**, **Data replication** status changed to **Disconnected**, and **Alerts** column shows the last alert as **Launched**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.4cutover.png?width=90pc)

Now as all servers have been cutover and finalized, you can archive servers to remove them from the list of Active source servers

### Archive Already Migrated Servers
You can now archive your source servers that have launched Cutover instances. Archiving will remove these source servers from the main Source Servers page, allowing you to focus on source servers that have not yet been cutover. You will still be able to access the archived servers through filtering options.
1. Select two servers.
2. Click on **Action**.
3. Choose **Mark as archived**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.5cutover.png?width=90pc)

4. Click on **Archive**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.6cutover.png?width=90pc)

5. To see your archived servers, open upper left drop-down menu and select **Archived source servers**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.10cutover/4.1.10.7cutover.png?width=90pc)