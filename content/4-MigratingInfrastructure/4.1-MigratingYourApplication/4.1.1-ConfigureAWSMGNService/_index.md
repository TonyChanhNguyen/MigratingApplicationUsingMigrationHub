---
title : "Configure AWS MGN service "
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1.1 </b> "
---

Application Migration Service must be initialized upon first use in each AWS Account and Region where replication will need to happen. The First step is to create the Replication Settings template, then the service is initialized by creating the IAM Roles which are required for the service to work.

1. Go to [AWS Application Migration Service](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#) .
2. Click on **Get started**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.1configure.png?width=90pc)

3. Choose **Set up service**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.2configure.png?width=90pc)

4. Once **Application Migration Service** is initialized, you'll be redirected into the **Application Migration Service Console Source Servers** page.
5. Under **Settings**, choose **Replication template**.
6. Then, click on **Edit**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.3configure.png?width=90pc)

7. At **Staging area subnet**, select subnet **Target Public**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.4configure.png?width=90pc)

8. Add tag with key is **Environment** and value is **Migration-Staging**.
9. Then, click on **Save template**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.5configure.png?width=90pc)

10. Wait a second and make sure your changes are saved.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.1configure/4.1.1.6configure.png?width=90pc)



