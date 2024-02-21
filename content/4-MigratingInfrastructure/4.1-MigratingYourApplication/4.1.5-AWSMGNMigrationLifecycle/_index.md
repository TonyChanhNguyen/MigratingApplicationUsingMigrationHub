---
title : "AWS MGN migration lifecycle "
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 4.1.5 </b> "
---

Now you can monitoring replication progress to know when your migration completed by AWS MGN Migration Life Cycle.
1. Click on **Source server name** name **ofbiz-web.onpremsim.env**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.5lifecycle/4.1.5.1lifecycle.png?width=90pc)

2. Now, the migration progress of this instance is in **Not ready** step.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.5lifecycle/4.1.5.2lifecycle.png?width=90pc)

The Lifecycle view shows the current state of each server within the migration lifecycle. And there are 6 states in the migration lifecycle:

+ Not ready - The server is undergoing the Initial Sync process and is not yet ready for testing. This process might take a few hours to a few days depending on the network bandwidth and size of the source server.
+ Ready for testing - The server has been successfully added to Application Migration Service and Initial Sync has completed. Test or Cutover instances can now be launched for this server.
+ Test in progress - A Test instance is currently being launched for this server. Note there's a link to the Job ID of the launch job that is associated with the launch of this instance.
+ Ready for cutover - This server has been tested and is now ready for a Cutover instance to be launched.
+ Cutover in progress - A Cutover instance is currently being launched for this server. Note there's a link to the Job ID of the new launch job that is associated with the launch of this instance.
+ Cutover complete - This server's migration has been complete. All of the resources associated with migration of this server have been cleaned up.