---
title : "Install AWS Replication Agent "
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4.1.4 </b> "
---
AWS Application Migration Service replicates data to AWS using an agent that must be installed on the source server.
1. Go to [Source server](https://us-west-2.console.aws.amazon.com/mgn/home?region=us-west-2#/sourceServers) of Application Migration Service.
2. Click on **Add server**.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.1installagent.png?width=90pc)

3. At **Select your operating system**, choose **Linux**.
4. At **IAM access key ID**, input **IAM access key ID** of user **MGNuser**.
5. At **IAM secret access key**, input **IAM secret access key** of user **MGNuser**.
6. Copy command at section 5 and 6.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.2installagent.png?width=90pc)

Now we will go to Bastion Host to install agent into instances.
7. Log in to Bastion Host
8. Use Putty in Bastion Host to SSH to instances.
9. SSH to Offbiz-web and Offbiz-db.
+ Log in: user
+ Password: 12345678
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.3installagent.png?width=90pc)

10. Run the command you had copied at step 6.
11. Installing an agent on each of the servers will take about 3-5 mins. Once agent is installed, you will see the final The AWS Replication Agent was successfully installed message in the SSH terminals.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.4installagent.png?width=90pc)

Also, you will see the servers added in the **AWS Application Service** console under **Source Servers** list in the initialization stage.
![Migrating your application](../../../images/4.migrateinfra/4.1migrateapp/4.1.4installagent/4.1.4.5installagent.png?width=90pc)