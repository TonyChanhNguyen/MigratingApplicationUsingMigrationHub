---
title : "EC2 instnace recommendations "
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 3.5 </b> "
---
Let us explore the EC2 instance recommendation feature in Migration Hub to estimate the cost of running your existing servers in AWS. This feature analyzes the details about each server, including server specification, CPU, and memory utilization data. The compiled data is then used to recommend the least expensive Amazon EC2 instance type that can handle the existing performance workload.

### Prerequisites
Before you can get Amazon EC2 instance recommendations, you must have data about your on-premises servers in Migration Hub. This data can come from the discovery tools (AWS Application Discovery Agent or Application Discovery Service Agentless Collector) or from Migration Hub import. For the purpose of this lab we going to use Application Discovery Agent.

##### Overview of the 3 options:
1. [AWS Application Discovery Agent](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-agent.html) is software that you install on on-premises servers and VMs targeted for discovery and migration. Agents support most Linux and Windows operating systems, and you can deploy them on physical on-premises servers, Amazon EC2 instances, and virtual machines.
2. [Application Discovery Service Agentless Collector](https://docs.aws.amazon.com/application-discovery/latest/userguide/agentless-collector.html) is an on-premises application that collects information through agentless methods about your on-premises environment. You install the Agentless Collector as a virtual machine (VM) in your VMware vCenter Server environment using an Open Virtualization Archive (OVA) file.
3. [AWS Migration Hub (Migration Hub) import](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-import.html) allows you to import details of your on-premises environment directly into Migration Hub without using the Agentless Collector or Discovery Agent, so you can perform migration assessment and planning directly from your imported data. You also can group your devices as applications and track their migration status.

### Generating Amazon EC2 Recommendations:
1. Go to [Migration Hub](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/dashboard).
2. At **Asset** feature. Choose **EC2 instance recommendations** .
![EC2 instance recommendations](../../images/3.discoveryexistinginfra/3.5ec2recommendation/3.5.1ec2recommendation.png?width=90pc)
3. At  **EC2 instance recommendations** interface, choose **Average utilization** under **Sizing preferences**.
4. Choose **US West (Oregon)** at **Region**.
5. Choose **Shared instances** at **Tenancy**.
6. Choose **On-Demand** at **Pricing model**.
7. Then, click on **Export recommendations**.
![EC2 instance recommendations](../../images/3.discoveryexistinginfra/3.5ec2recommendation/3.5.2ec2recommendation.png?width=90pc)

8. When the process is complete, your browser will automatically download a compressed archive (ZIP) file, containing a comma-separated values (CSV) file with your recommendations.
9. Checking recommendation file, there are analysis and recommendations for your systems. Example: When checking column P name Recommendation.EC2.Instance.Model, it recommend the model for each instance can be at least suitable with this system.
|Server.HostName                |Current model                 |Recommendation model    |
|-------------------------------|------------------------------|------------------------|
| ofbiz-db.onpremsim.env        |t3.small                      |t3a.nano                |      
| ofbiz-web.onpremsim.env       |t3.medium                     |t3a.medium              |      
| wordpress-web.onpremsim.env   |t3.small                      |t3a.micro               |      
| wordpress-db.onpremsim.env    |t3.small                      |t3a.nano                |      

 {{%notice info%}}
The results of this analysis only provide recommendations and do not obligate you to any further actions. Selections and preferences for your EC2 instance(s) are made at your sole discretion.
{{%/notice%}}
