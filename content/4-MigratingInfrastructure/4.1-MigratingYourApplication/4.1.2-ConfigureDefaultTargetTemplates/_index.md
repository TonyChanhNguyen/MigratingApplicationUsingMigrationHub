---
title : "Configure default target template  "
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.1.2 </b> "
---
AWS MGN allows to set up default templates for target instances configuration, both for Launch Templates and Post-Launch settings . These templates will be applied to every new server added to the AWS MGN list of source servers, which happens after the AWS Replication Agent is installed on the source server.

### Define default target instances configuration
AWS MGN uses an **EC2 Launch Template**  to define the configuration of the target EC2 instances to be launched during the test and cutover migration stages.
1. Under **Settings**, choose **Launch template**.
2. Click on **Edit**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.1defaulttemplate.png?width=90pc)

3. At **General launch settings** feature, uncheck **Activate instance type right-sizing**.
4. Check **Transfer server tags**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.2defaulttemplate.png?width=90pc)

5. At **Default EC2 Launch Template** feature, choose subnet **TargetPublic** at **Default target subnet**
6. Select security group name **FCJ-MigrationHub-Workshop-SOURCENETWORK-XXXXXXXXXXXX-TargetSecurityGroup-XXXXXXXXXXXX** at **Additional security groups**.
7. Select **t3.small** at **Default instance type**
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.3defaulttemplate.png?width=90pc)

8. Then, click on **Save template**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.4defaulttemplate.png?width=90pc)

9. Wait a second and make sure your changes are saved.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.5defaulttemplate.png?width=90pc)


### Define default post-launch integration for target instances
AWS MGN uses **Post-Launch Template** configuration to define any post-launch automation actions to be executed on the target EC2 instances after successful launch of test/cutover instances. In this step we will use AWS MGN Post-Launch default template to configure integration with **AWS Systems Manager** with migrated servers. This will automatically enable **AWS System Manager** features such as Fleet Management, Inventory, Patch Management, Remote execution, execution of Automation documents.
1. Under **Settings**, choose **Post-launch template**.
2. Click on **Edit**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.6defaulttemplate.png?width=90pc)

3. Select the toggle saying *Install the Systems Manager agent and allow executing actions on launched servers*.
4. Keep **Deployment** option as **Test and Cutover instances**.
5. Then, click on **Save template**.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.7defaulttemplate.png?width=90pc)

6. After we have configured the **Post-Launch template** to enable **AWS System Manager Agent (SSM Agent)** integration, other SSM automation documents can be triggered upon successful launch of test or cutover instances.
![Migrating your application](/images/4.migrateinfra/4.1migrateapp/4.1.2defaulttemplate/4.1.2.8defaulttemplate.png?width=90pc)