---
title : "Launch cutover instance "
date : "`r Sys.Date()`"
weight : 8
chapter : false
pre : " <b> 4.1.8 </b> "
---

1. Once servers are in **Ready for cutover** status, select all 2 servers to start cutover. 
2. Choose **Test and Cutover** on top right drop down.
3. Then under **Cutover** section, choose **Launch cutover instances**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.1cutover.png?width=90pc)

4. Click on **Launch**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.2cutover.png?width=90pc)

5. **Migration lifecycle** status changes to **Cutover in progress**.
6. For more detail, click on **View job details**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.3cutover.png?width=90pc)

7. Wait 10 - 15 minutes, the **Status** of **Source server name** will be **Launched**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.8cutover/4.1.8.4cutover.png?width=90pc)
Now, as all the servers have been launched as new cutover instances, we need to validate the applications in the new environment.