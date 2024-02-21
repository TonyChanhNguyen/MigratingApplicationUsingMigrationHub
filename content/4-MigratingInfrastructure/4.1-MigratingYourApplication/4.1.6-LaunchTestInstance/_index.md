---
title : "Launch test instance "
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 4.1.6 </b> "
---

1. Once server status changed to **Ready for testing** on **AWS Application Migration Service** console. You can perform testing on that server.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.1testing.png?width=90pc)

2. Select instance to launch in test mode.
3. Click **Test and Cutover**.
4. Then, select **Launch Test Instance**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.2testing.png?width=90pc)

5. Click on **Launch**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.3testing.png?width=90pc)

6. This will change the **Migration Lifecycle Status** to **Test in progress**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.4testing.png?width=90pc)

7. Click to **ofbiz-db.onpremsim.env** and see testing job is starting.
8. Click on **Job ID**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.5testing.png?width=90pc)

9. Demonstrate **Job log** to see the detail.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.6testing.png?width=90pc)

10. Once launch job completes, you should see the actual status of each server's launch result in the **Source servers**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.7testing.png?width=90pc)

11. After performing all necessary testing procedures on these new test instances, select all 2 servers.
12. Choose **Test and cutover**.
13. Then mark them as **Ready for Cutover**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.8testing.png?width=90pc)

14. Click on **Continue**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.9testing.png?width=90pc)

15. The **Migration lifecycle** status changed to **Ready for cutover**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.6testing/4.1.6.10testing.png?width=90pc)

As all the testing has been finished and servers are marked as **Ready for cutover**, move to the next step to finalize any changes in the source environment before the final cutover.