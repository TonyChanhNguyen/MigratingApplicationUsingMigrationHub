---
title : "Create and monitor the tasks "
date : "`r Sys.Date()`"
weight : 5 
chapter : false
pre : " <b> 4.2.5 </b> "
---

An AWS Database Migration Service (AWS DMS) task is where all the work happens. You specify what tables (or views) and schemas to use for your migration and any special processing, such as logging requirements, control table data, and error handling.

When creating a migration task, you need to know several things:

+ Before you can create a task, you must create a source endpoint, a target endpoint, and a replication instance.
+ You can specify many task settings to tailor your migration task. You can set these by using the AWS Management Console, AWS Command Line Interface (AWS CLI), or AWS DMS API. These settings include specifying how migration errors are handled, error logging, and control table information.
+ After you create a task, you can run it immediately. The target tables with the necessary metadata definitions are automatically created and loaded, and you can specify ongoing replication.
+ By default, AWS DMS starts your task as soon as you create it. However, in some situations, you might want to postpone the start of the task. For example, when using the AWS CLI, you might have a process that creates a task and a different process that starts the task based on some triggering event. As needed, you can postpone your task's start.
+ You can monitor, stop, or restart tasks using the AWS DMS console, AWS CLI, or AWS DMS API.

### Create your task
1. Go to [Database migration tasks](https://us-west-2.console.aws.amazon.com/dms/v2/home?region=us-west-2#tasks).
2. Click on **Create task**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.1createtask.png?width=90pc)

3. At **Task identifier**, input ```WordPress-MySQL-to-Aurora```.
4. At **Replication instance**, select **mid-repinst-wp**.
5. At **Source database endpoint**, select **sourcewordpress**.
6. At **Target database endpoint**, select **targetwordpress**.
7. At **Migration Type**, select **Migrating existing data**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.2createtask.png?width=90pc)

8. In **Table mappings** feature, select **Wizard** at **Editing mode**.
9. Click on **Add new selection data**.
10. At **Schema**, select **Enter a schema**.
11. At **Schema name**, select **%**.
12. At **Table name**, select **%**.
13. At **Action**, select **Include**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.3createtask.png?width=90pc)

14. Then, click on **Create task**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.4createtask.png?width=90pc)

15. Now, your replication from the EC2 database instance to Aurora MySQL is running and the data started to be replicated.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.5createtask.png?width=90pc)

### Monitor your task

Now that your migration tasks are running, we have to monitor them and wait until the status **Load complete**.
![Migrate your database](../../../images/4.migrateinfra/4.2migratedb/4.2.5createtask/4.2.5.6createtask.png?width=90pc)