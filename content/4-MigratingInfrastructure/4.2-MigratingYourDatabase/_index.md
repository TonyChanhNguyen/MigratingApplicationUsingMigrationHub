---
title : "Migrate your database "
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

### AWS Database Migration Services
Now that you just finished to migrate your applications to AWS using MGN, let's migrate the databases to run in Amazon Aurora using the AWS Database Migration Service tool.

AWS Database Migration Service helps you migrate databases to AWS quickly and securely. The source database remains fully operational during the migration, minimizing downtime to applications that rely on the database. The AWS Database Migration Service can migrate your data to and from most widely used commercial and open-source databases.

AWS Database Migration Service supports homogeneous migrations such as Oracle to Oracle, as well as heterogeneous migrations between different database platforms, such as Oracle or Microsoft SQL Server to Amazon Aurora. With AWS Database Migration Service, you can continuously replicate your data with high availability and consolidate databases into a petabyte-scale data warehouse by streaming data to Amazon Redshift and Amazon S3.

Amazon Aurora is a MySQL and PostgreSQL-compatible relational database built for the cloud, that combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases.

Amazon Aurora is up to five times faster than standard MySQL databases and three times faster than standard PostgreSQL databases. It provides the security, availability, and reliability of commercial databases at 1/10th the cost. Amazon Aurora is fully managed by Amazon Relational Database Service (RDS), which automates time-consuming administration tasks like hardware provisioning, database setup, patching, and backups.

### In this section, you perform the following tasks:
+ Create Amazon Aurora database
+ Migrate the existing database (running in EC2) to Aurora with AWS DMS
+ Update the DNS records to reflect the migration

### Content
+ 4.2.1 [Finnalize Cutover and archive servers](4-migratinginfrastructu4.2-migratingyourdataba4.2.1-createaurorafinaltargetdatabases)
+ 4.2.2 [Create replication subnet groups](4-migratinginfrastructu4.2-migratingyourdataba4.2.2-createreplicaitonsubnetgrou)
+ 4.2.3 [Create a replication instance](4-migratinginfrastructu4.2-migratingyourdataba4.2.3-createareplicationinstance)
+ 4.2.4 [Specify source and target endpoints](4-migratinginfrastructu4.2-migratingyourdataba4.2.4-specifysourceandtargetendpoints)
+ 4.2.5 [Create and monitor the tasks](4-migratinginfrastructu4.2-migratingyourdataba4.2.5-createandmonitorthetas)
+ 4.2.6 [Shut down source server and update DNS](4-migratinginfrastructu4.2-migratingyourdataba4.2.6-shutdownsourceserverandupdated)