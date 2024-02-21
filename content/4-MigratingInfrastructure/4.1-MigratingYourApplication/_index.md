---
title : "Migrate infrastructure "
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---
### MGN
[AWS Application Migration Service (AWS MGN)](https://aws.amazon.com/application-migration-service/) is a highly automated solution that simplifies, expedites, and reduces the cost of migrating and modernizing applications. It allows companies to migrate a large number of physical, virtual, and cloud servers without compatibility issues, performance disruption, or long cutover windows. AWS MGN continuously replicates source servers to your AWS account. When you’re ready, it automatically converts and launches your servers on AWS so you can quickly benefit from the cost savings, productivity, resilience, and agility of the Cloud. In addition, AWS MGN allows you to modernize launched applications by running pre-configured actions.
### How it works?
![Migrating your application](../../images/4.migrateinfra/4.1migrateapp/4.1.1migrateapp.png?width=90pc)

### Benefits of Application Migration Service include:
+ Cutover windows of minutes and no data loss.
+ Large-scale migrations with no performance impact.
+ Wide platform and source Operating Systems support.
+ Automated migration to minimize IT resources and project length.

### Content
+ 4.1.1 [Configure AWS MGN service](4.1.1-configureawsmgnservice/)
+ 4.1.2 [Configure default target templates](4.1.2-configuredefaulttargettemplates/)
+ 4.1.3 [Create AWS replication agent IAM user](../4.1.3-createawsreplicationagentiamuser/)
+ 4.1.4 [Install AWS replication agent](../4.1.4-installawsreplicationagent/)
+ 4.1.5 [AWS MGN migration lifecycle](../4.1.5-awsmgnmigrationlifecycle/)
+ 4.1.6 [Launch test instance](../4.1.6-launchtestinstance/)
+ 4.1.7 [Shutdown source environment](../4.1.7-shutdownsourceenvironment/)
+ 4.1.8 [Launch cutover instance](../4.1.8-launchcutoverinstance/)
+ 4.1.9 [Update DNS and validate the applications](../4.1.9-updatednsandvalidatetheapplications/)
+ 4.1.10 [Finnalize Cutover and archive servers](../4.1.10-finalizecutoverandarchiveservers/)

