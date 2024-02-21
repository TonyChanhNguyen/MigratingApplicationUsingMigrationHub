---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
### Content
1. [Introduce](../1-introduce)
2. [Prerequire](../2-prerequiste/)
    + 2.1 [Create Key Pair](../2-prerequiste/2.1-createkeypair/)
    + 2.2 [Launch CloudFormation template](../2-prerequiste/2.2-lauchcloudformationtemplate/)
    + 2.3 [Connect to Bastion Host](../2-prerequiste/2.3-connecttobastionhost/)
    + 2.4 [Explore environment](../2-prerequiste/2.4-exploreenvironment/)
    + 2.5 [Create IAM credential](../2-prerequiste/2.5-createiamcredential/)
3. [Discovering existing infrastructure](../3-discoveryexistinginfrastructure/)
    + 3.1 [Enable Athena integration](../3-discoveryexistinginfrastructure/3.1-enableathenaintegration/)
    + 3.2 [Install ADS Agent to VMs](../3-discoveryexistinginfrastructure/3.2-installadsagenttovms/)
    + 3.3 [Browse discovered data](../3-discoveryexistinginfrastructure/3.3-browsediscovereddata/)
    + 3.4 [Viewing network connections](../3-discoveryexistinginfrastructure/3.4-viewingnetworkconnections/)
    + 3.5 [EC2 instance recommendations](../3-discoveryexistinginfrastructure/3.5-ec2instancerecommendations/)
    + 3.6 [Explore data using Athena](../3-discoveryexistinginfrastructure/3.6-exploredatausingathena/)
4. [Migrating infrastructure](../4-migratinginfrastructure/)
    + 4.1 [Migrating your application](../4-migratinginfrastructure/4.1-migratingyourapplication/)
        + 4.1.1 [Configure AWS MGN service](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.1-configureawsmgnservice/)
        + 4.1.2 [Configure default target templates](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.2-configuredefaulttargettemplates/)
        + 4.1.3 [Create AWS replication agent IAM user](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.3-createawsreplicationagentiamuser/)
        + 4.1.4 [Install AWS replication agent](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.4-installawsreplicationagent/)
        + 4.1.5 [AWS MGN migration lifecycle](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.5-awsmgnmigrationlifecycle/)
        + 4.1.6 [Launch test instance](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.6-launchtestinstance/)
        + 4.1.7 [Shutdown source environment](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.7-shutdownsourceenvironment/)
        + 4.1.8 [Launch cutover instance](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.8-launchcutoverinstance/)
        + 4.1.9 [Update DNS and validate the applications](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.9-updatednsandvalidatetheapplications/)
        + 4.1.10 [Finalize Cutover and archive servers](../4-migratinginfrastructure/4.1-migratingyourapplication/4.1.10-finalizecutoverandarchiveservers/)
    + 4.2 [Migrating your database](../4-migratinginfrastructure/4.2-migratingyourdatabase/)
        + 4.2.1 [Create Aurora final target databases](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.1-createaurorafinaltargetdatabases)
        + 4.2.2 [Create replication subnet groups](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.2-createreplicaitonsubnetgroups/)
        + 4.2.3 [Create a replication instance](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.3-createareplicationinstance)
        + 4.2.4 [Specify source and target endpoints](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.4-specifysourceandtargetendpoints)
        + 4.2.5 [Create and monitor the tasks](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.5-createandmonitorthetasks/)
        + 4.2.6 [Shut down source server and update DNS](../4-migratinginfrastructure/4.2-migratingyourdatabase/4.2.6-shutdownsourceserverandupdatedns/)
5. [Clean up resources](../5-cleanup/)