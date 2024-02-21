---
title : "Discovery existing infrastructure "
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
### Overview
[AWS Application Discovery Service](https://docs.aws.amazon.com/application-discovery/latest/userguide/what-is-appdiscovery.html) helps enterprise customers plan migration projects by gathering information about their on-premises data centers.

[The AWS Application Discovery Agent](https://docs.aws.amazon.com/application-discovery/latest/userguide/discovery-agent.html) is software that you install on on-premises servers and VMs targeted for discovery and migration. Agents capture system configuration, system performance, running processes, and details of the network connections between systems. Agents support most Linux and Windows operating systems, and you can deploy them on physical on-premises servers, Amazon EC2 instances, and virtual machines.

The Discovery Agent runs in your local environment and requires root privileges. When you start the Discovery Agent, it registers with the Application Discovery Service endpoint, arsenal-discovery..amazonaws.com, and pings the service at 15 minute intervals for configuration information. When you send a command that tells an agent to start data collection, it starts collecting data for the host or VM where it resides. Collection includes system specifications, times series utilization or performance data, network connections, and process data. You can use this information to map your IT assets and their network dependencies. All of these data points can help you determine the cost of running these servers in AWS and also plan for migration.

Data is transmitted securely by the Discovery Agents to Application Discovery Service using Transport Layer Security (TLS) encryption. Agents are configured to upgrade automatically when new versions become available. You can change this configuration setting if desired.

### Content
+ 3.1 [Enable Athena integration](../3-discoveryexistinginfrastructure/3.1-enableathenaintegration/)
+ 3.2 [Install ADS Agent to VMs](../3-discoveryexistinginfrastructure/3.2-installadsagenttovms/)
+ 3.3 [Browse discovered data](../3-discoveryexistinginfrastructure/3.3-browsediscovereddata/)
+ 3.4 [Viewing network connections](../3-discoveryexistinginfrastructure/3.4-viewingnetworkconnections/)
+ 3.5 [EC2 instance recommendations](../3-discoveryexistinginfrastructure/3.5-ec2instancerecommendations/)
+ 3.6 [Explore data using Athena](../3-discoveryexistinginfrastructure/3.6-exploredatausingathena/) 