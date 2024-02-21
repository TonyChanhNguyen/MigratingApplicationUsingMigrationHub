---
title : "Viewing network connections "
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

Viewing network connections in AWS Migration Hub allows you to visualize a server's dependencies. The visualization of these dependencies helps you verify all of the resources required to successfully migrate each of your applications to Amazon Web Services.

You view network connections by using the network diagram. When using the network diagram, you can visually review large amounts of data to understand what server dependencies exist. Understanding these server dependencies helps you plan how to group together the needed resources to support an application for migration to AWS.

1. At [Server](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/discover/servers) feature of **Migration Hub**.
2. Select all the server then click **Visualize network**.
![Visualize Network](../../images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.1visualizenetwork.png?width=90pc)

3. Since we selected all servers, you will see a diagram depicting how they are all interrelated, it may take a few minutes for the interrelations to be updated.
![Visualize Network](../../images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.2visualizenetwork.png?width=90pc)

4. It may be overwhelming in some environments to see the whole network on the same diagram. Let's go back to the Server list tab and select the *wordpress-web* server to look at more closely. Select the instance and click the Network tab.
![Visualize Network](../../images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.3visualizenetwork.png?width=90pc)

5. The icon for the server you choose is centered in the network diagram. Connections fan out from the center server to servers that are directly connected to the server you choose.
![Visualize Network](../../images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.4visualizenetwork.png?width=90pc)

We now clearly see that this server has a dependencey with the wordpress-db server. Additoinally, we can notice that it is also communicating with 192.168.0.246 (the Bastion server) and 192.168.1.250 (DNS server).

6. We will want to group *wordpress-web* and *wordpress-db* together as they comprise the front and backend of the application. Go back to the Server list tab and select those 2 servers.
7. Then click **Group as application**.
![Visualize Network](../../images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.5visualizenetwork.png?width=90pc)

8. Choose **Group as a new application**.
9. Input **Application name** ```Wordpress```.
10. Click **Group**.
![Visualize Network](../../images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.6visualizenetwork.png?width=90pc)

11. Create an application group for the **ofbiz** application comprised of the 2 ofbiz servers.
![Visualize Network](../../images/3.discoveryexistinginfra/3.4visualizenetwork/3.4.7visualizenetwork.png?width=90pc)

 {{%notice info%}}
For actual production migration it is recommended that the Discovery Agent server data should be collected for two to six weeks before you can use the network diagram to view established connection patterns.
{{%/notice%}}
