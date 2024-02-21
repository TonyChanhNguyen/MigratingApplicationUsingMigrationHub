---
title : "Install ADS Agent to VMs "
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

1. Log in to Bastion Host same as step 10 of [Connect to Bastion Host](./2.3-connecttobastionhost/). Use Putty icon on the Bastion host desktop to connect to each server:
|Application        |FQDN                          |OS      |Username   |Password |
|-------------------|------------------------------|--------|-----------|---------|
| wordpress-web     |wordpress-web.onpremsim.env   |Centos7 |user       |12345678 |
| wordpress-db      |wordpress-db.onpremsim.env    |Centos7 |user       |12345678 |
| ofbiz-web         |ofbiz-web.onpremsim.env       |Centos7 |user       |12345678 |
| ofbiz-db          |ofbiz-db.onpremsim.env        |Centos7 |user       |12345678 |

2. Input FQDn of instance, then click **Open**
![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.1installads.png?width=90pc)

3. Enter user name **user** and password **12345678** (Root password you had created by CloudFormation template).
![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.2installads.png?width=90pc)

4. Download and install the agents as per the following instructions:
```
curl -o ./aws-discovery-agent.tar.gz https://s3-us-west-2.amazonaws.com/aws-discovery-agent.us-west-2/linux/latest/aws-discovery-agent.tar.gz
tar -xzf aws-discovery-agent.tar.gz
sudo bash install -r "us-west-2" -k "<AWS key id>" -s "<AWS key secret>"
```
 {{%notice info%}}
Replace < AWS key id > and < AWS key secret > with the information downloaded during the ADS user key creation step.
{{%/notice%}}
![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.3installads.png?width=90pc)

5. Repeat the steps until all instances have the agent installed.

6. Once you have installed the Discovery Agent, data collection will start automatically. You can check collection status and other additional information on [Discovery Agents tab of Data Collectors page of Migration Hub console](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/discover/datacollectors?type=agent&filter=collectionStatus%2B%3D%2BSTARTED).
 {{%notice info%}}
It may take several minutes for the agents to appear.
{{%/notice%}}

![Install ADS agents](/images/3.discoveryexistinginfra/3.2installads/3.2.4installads.png?width=90pc)