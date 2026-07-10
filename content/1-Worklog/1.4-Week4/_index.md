---
title: "Week 4: Database Services (Amazon RDS, DynamoDB, ElastiCache)"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Week 4 Objectives:
* Differentiate and master the real-world use cases of relational databases (Amazon RDS) and non-relational NoSQL databases (Amazon DynamoDB).
* Deep dive into the architecture and table design in Amazon DynamoDB - the core data storage service.
* Learn the mechanism of accelerating data retrieval and reducing load on the main Database using caching (Amazon ElastiCache).

### Tasks carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - Learn about Amazon RDS relational database:<br>&emsp; + Supported Database Engines (MySQL, PostgreSQL...).<br>&emsp; + High availability mechanism: Multi-AZ deployments.<br>&emsp; + Optimize read performance with Read Replicas. | 11/05/2026 | 11/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - Deeply research Amazon DynamoDB (NoSQL):<br>&emsp; + Concepts of Tables, Items, Attributes.<br>&emsp; + How to choose reasonable Partition Keys and Sort Keys.<br>&emsp; + Differentiate between On-demand capacity and Provisioned capacity (RCU/WCU). | 12/05/2026 | 12/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - Learn about Amazon ElastiCache in-memory caching:<br>&emsp; + Differentiate between Redis and Memcached.<br>&emsp; + Common Caching strategies (Lazy Loading, Write Through) to optimize Database queries. | 13/05/2026 | 13/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **DynamoDB Practice:**<br>&emsp; + Initialize the **fcaj-idp-metadata** table (storing document information after AI processing).<br>&emsp; + Set the Partition Key as **document_id**.<br>&emsp; + Create a Global Secondary Index (GSI) to support querying by **upload_date**. | 14/05/2026 | 14/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **RDS Practice & Data Manipulation:**<br>&emsp; + Experimentally create an Amazon RDS MySQL (Free Tier) to observe provisioning time.<br>&emsp; + Insert sample JSON Items into the DynamoDB table via the Explore items interface.<br>&emsp; + Compare the speed and interaction methods between SQL and NoSQL on the Console. | 15/05/2026 | 15/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Achievements:
* Mastered the NoSQL schema design mindset on DynamoDB, clearly differentiating how Partition Keys and Sort Keys work to avoid bottlenecks when retrieving data.
* Successfully initialized the **fcaj-idp-metadata** DynamoDB table by myself, ready to integrate with AWS Lambda for the IDP system.
* Knew how to create Global Secondary Indexes (GSI) to solve the problem of flexible data querying on DynamoDB without needing to Scan the entire table.
* Practically experienced the Amazon RDS initialization process, clearly recognizing the difference in wait time and infrastructure management compared to the "ready-to-use" Serverless nature of DynamoDB.

---
![DynamoDB Table Creation](/images/1-Worklog/1.4-Week4/week4-1.png)
<p align="center"><i>Figure 1: The <b>fcaj-idp-metadata</b> Amazon DynamoDB table was successfully created with the Capacity mode configured to On-demand.</i></p>

![DynamoDB Explore Items](/images/1-Worklog/1.4-Week4/week4-2.png)
<p align="center"><i>Figure 2: The Explore items interface showing sample JSON formatted records (items) successfully inserted into the DynamoDB table.</i></p>

![Amazon RDS Dashboard](/images/1-Worklog/1.4-Week4/week4-3.png)
<p align="center"><i>Figure 3: The Amazon RDS interface displaying a MySQL database in the Available state, ready to connect.</i></p>