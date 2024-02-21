---
title : "Create AWS Replication Agent IAM user "
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.1.3 </b> "
---
**The AWS Replication Agent (MGN agent)** that will be installed on the source servers requires IAM permissions in order to register the source machine with AWS MGN. In this step we will create the required IAM user that will be used by AWS Replication Agent in the next steps.

1. Go to [IAM](https://us-east-1.console.aws.amazon.com/iam/home?region=us-west-2#/home). Select **User** feature.
2. Click on **Create user**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.1createiamuser.png?width=90pc)

3. Input user name ```MGNuser```.
4. Click on **Next**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.2createiamuser.png?width=90pc)

5. At **Permissions options**, select **Attach policies directly**.
6. At **Permissions policies**, search and select policy name **AWSApplicationMigrationAgentInstallationPolicy**.
7. Then, click on **Next**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.3createiamuser.png?width=90pc)

8. Review and click on **Create user**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.4createiamuser.png?width=90pc)

9. Click **View user**, choose **Security credentials** tab.
10. Click on **Create credential**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.5createiamuser.png?width=90pc)

11. Choose **Application running outside AWS**.
12. Then, click on **Next**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.6createiamuser.png?width=90pc)

13. Next, click on **Create access key**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.7createiamuser.png?width=90pc)

14. Download your credential file by clicking on **Download .csv file**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.3createiamuser/4.1.3.8createiamuser.png?width=90pc)