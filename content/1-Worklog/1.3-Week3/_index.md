---
title: "Week 3: Networking Essentials (VPC, Route 53, CloudFront)"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---


### Week 3 Objectives:
* Clearly understand the virtual private cloud architecture (Amazon VPC) and how to route data traffic (Routing, Internet Gateway).
* Configure strict network security filtering layers using Security Groups and Network ACLs.
* Learn about the content delivery network service (CloudFront) and domain name management (Route 53) to prepare for optimizing the system's document transfer speed later.

### Tasks carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - Learn foundational knowledge about Amazon VPC:<br>&emsp; + VPC, CIDR block, basic IPv4.<br>&emsp; + Differentiate between Public Subnet and Private Subnet.<br>&emsp; + Route Tables and Internet Gateway (IGW). | 04/05/2026 | 04/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - Learn about network security mechanisms:<br>&emsp; + Differentiate between Security Groups (Stateful) and Network ACLs (Stateless).<br>&emsp; + Operating mechanism of NAT Gateway for Private Subnets. | 05/05/2026 | 05/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - Learn about Amazon Route 53 domain name resolution management service:<br>&emsp; + Concepts: DNS, Hosted Zones, Records (A, CNAME, Alias).<br>&emsp; + Routing Policies. | 06/05/2026 | 06/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - Learn about the Content Delivery Network (CDN) service - Amazon CloudFront:<br>&emsp; + Caching mechanism and Edge Locations.<br>&emsp; + Integrate CloudFront with S3 to secure the bucket (Origin Access Control - OAC). | 07/05/2026 | 07/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **Networking Practice (Comprehensive):**<br>&emsp; + Design and create a complete Custom VPC yourself (**fcaj-idp-vpc**).<br>&emsp; + Configure a Security Group to only allow SSH from your personal machine's IP.<br>&emsp; + Set up a Route Table to route network traffic to the Internet Gateway. | 08/05/2026 | 08/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Achievements:
* Successfully designed and deployed an isolated and secure virtual private network (Custom VPC) environment by myself, ensuring a firm grasp of data flow.
* Strictly established firewall rules through Security Groups, adhering to the principle of only opening truly necessary network ports.
* Mastered the routing mechanism by configuring the Route Table to connect accurately with the Internet Gateway.
* Clearly understood the operating method of CloudFront combined with OAC to securely wrap the S3 document repository.

---
![Custom VPC Resource Map](/workshop_intership_report/images/1-Worklog/1.3-Week3/week3-1.png)
<p align="center"><i>Figure 1: The network resource map showing the newly created Custom VPC with Public/Private Subnets and how network traffic is routed.</i></p>

![Security Group Inbound Rules](/workshop_intership_report/images/1-Worklog/1.3-Week3/week3-2.png)
<p align="center"><i>Figure 2: The Inbound rules configuration of the Security Group is strictly set, only allowing the SSH port (22) from a personal IP address.</i></p>

![VPC Route Table](/workshop_intership_report/images/1-Worklog/1.3-Week3/week3-3.png)
<p align="center"><i>Figure 3: Route Table configuration for the Public Subnet, successfully routing traffic to the Internet via the Internet Gateway (IGW).</i></p>