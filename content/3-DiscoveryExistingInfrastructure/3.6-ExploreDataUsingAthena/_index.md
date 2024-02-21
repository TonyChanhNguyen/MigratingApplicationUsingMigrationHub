---
title : "Explore data using Athena "
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 3.6 </b> "
---
Once you have enabled Data Exploration in Amazon Athena, you can begin exploring and working with current, detailed data discovered by your agents in Amazon Athena. You can query this data directly in Athena to do such things as generate spreadsheets, run a cost analysis, port the query to a visualization program to diagram network dependencies, and more.

### Understand ADS Database in Athena
1. Go to [Server of Migration Hub](https://us-west-2.console.aws.amazon.com/migrationhub/home?region=us-west-2#/discover/servers).
2. Click on **Actions** button.
3. Then click **View in Amazon Athena**.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.1exploredata.png?width=90pc)

4. At **Query editor** interface, select tab **Settings**.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.2exploredata.png?width=90pc)

5. Then, click on **Manage**.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.3exploredata.png?width=90pc)

6. At **Manage settings** interface, click on **Browse S3**.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.4exploredata.png?width=90pc)

7. Select the S3 bucket name **aws-application-discovery-service-xxxxxxxxxxxxxxxxxxxxxxxxx**.
8. Then, click on **Choose**.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.5exploredata.png?width=90pc)

9. Then, click **Save**.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.6exploredata.png?width=90pc)

10. On the **Editor** tab, in the navigation pane under **Database**, make sure that *application_discovery_service_database* is selected.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.7exploredata.png?width=90pc)

11. Under **Tables** the following tables represent the datasets grouped by the agents.
+ os_info_agent
+ network_interface_agent
+ sys_performance_agent
+ processes_agent
+ inbound_connection_agent
+ outbound_connection_agent
+ id_mapping_agent
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.8exploredata.png?width=90pc)

### Explore discovered data with pre-built queries.
1. Place your code in **Athena's Query Editor** window and paste the query.
2. Choose **Run** to see the result.

```
CREATE OR REPLACE VIEW hostname_ip_helper AS
SELECT DISTINCT
  "os"."host_name"
, "nic"."agent_id"
, "nic"."ip_address"
FROM
  os_info_agent os
, network_interface_agent nic
WHERE ("os"."agent_id" = "nic"."agent_id");
```
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.9exploredata.png?width=90pc)

3. To see what this query looks like, locate the **Views** section under your **Tables**. 
4. Click the 3-dot menu and select **Preview View**.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.10exploredata.png?width=90pc)

5. See the result.
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.11exploredata.png?width=90pc)

#### Identify Servers With or Without Agents
This query can help you perform data validation. If you've deployed agents on a number of servers in your network, you can use this query to understand if there are other servers in your network without agents deployed on them. In this query, we look into the inbound and outbound network traffic, and filter the traffic for private IP addresses, only. That is, IP addresses starting with 192, 10, or 172.
```
SELECT DISTINCT "destination_ip" "IP Address" ,
         (CASE
    WHEN (
    (SELECT "count"(*)
    FROM network_interface_agent
    WHERE ("ip_address" = "destination_ip") ) = 0) THEN
        'no'
        WHEN (
        (SELECT "count"(*)
        FROM network_interface_agent
        WHERE ("ip_address" = "destination_ip") ) > 0) THEN
            'yes' END) "agent_running"
    FROM outbound_connection_agent
WHERE ((("destination_ip" LIKE '192.%')
        OR ("destination_ip" LIKE '10.%'))
        OR ("destination_ip" LIKE '172.%'))
UNION
SELECT DISTINCT "source_ip" "IP ADDRESS" ,
         (CASE
    WHEN (
    (SELECT "count"(*)
    FROM network_interface_agent
    WHERE ("ip_address" = "source_ip") ) = 0) THEN
        'no'
        WHEN (
        (SELECT "count"(*)
        FROM network_interface_agent
        WHERE ("ip_address" = "source_ip") ) > 0) THEN
            'yes' END) "agent_running"
    FROM inbound_connection_agent
WHERE ((("source_ip" LIKE '192.%')
        OR ("source_ip" LIKE '10.%'))
        OR ("source_ip" LIKE '172.%'));

```
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.12exploredata.png?width=90pc)

#### Analyze System Performance Data for Servers With Agents
You can use this query to analyze system performance and utilization pattern data for your on-premises servers that have agents installed on them. The query combines the system_performance_agent table with os_info_agent table to identify the hostname for each server. This query returns the time series utilization data (in 15 minute intervals) for all the servers where agents are running.
```
SELECT "OS"."os_name" "OS Name" ,
     "OS"."os_version" "OS Version" ,
     "OS"."host_name" "Host Name" ,
     "SP"."agent_id" ,
     "SP"."total_num_cores" "Number of Cores" ,
     "SP"."total_num_cpus" "Number of CPU" ,
     "SP"."total_cpu_usage_pct" "CPU Percentage" ,
     "SP"."total_disk_size_in_gb" "Total Storage (GB)" ,
     "SP"."total_disk_free_size_in_gb" "Free Storage (GB)" ,
     ("SP"."total_disk_size_in_gb" - "SP"."total_disk_free_size_in_gb") "Used Storage" ,
     "SP"."total_ram_in_mb" "Total RAM (MB)" ,
     ("SP"."total_ram_in_mb" - "SP"."free_ram_in_mb") "Used RAM (MB)" ,
     "SP"."free_ram_in_mb" "Free RAM (MB)" ,
     "SP"."total_disk_read_ops_per_sec" "Disk Read IOPS" ,
     "SP"."total_disk_bytes_written_per_sec_in_kbps" "Disk Write IOPS" ,
     "SP"."total_network_bytes_read_per_sec_in_kbps" "Network Reads (kbps)" ,
     "SP"."total_network_bytes_written_per_sec_in_kbps" "Network Write (kbps)"
FROM "sys_performance_agent" "SP" , "OS_INFO_agent" "OS"
WHERE ("SP"."agent_id" = "OS"."agent_id") limit 10;

```
![Explore data using Athena](/images/3.discoveryexistinginfra/3.6exploredata/3.6.13exploredata.png?width=90pc)