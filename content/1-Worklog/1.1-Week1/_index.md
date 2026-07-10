---
title: "Week 1: Getting familiar with AWS and basic services"
date: 2026-04-17
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---


### Week 1 Objectives:
* Connect and get acquainted with the culture and members of the First Cloud AI Journey program.
* Master core Cloud Computing concepts and basic AWS service groups.
* Become proficient in configuring and interacting with AWS via the web interface (Console) and command line (AWS CLI).

### Tasks carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Friday**<br>(Day 1) | - Meet and get acquainted with FCAJ members and mentors.<br>- Read and take notes on the internal rules and workflows of the Bootcamp program. | 17/04/2026 | 17/04/2026 | |
| **Monday**<br>(Day 2) | - Learn an overview of AWS and core service groups:<br>&emsp; + Compute<br>&emsp; + Storage<br>&emsp; + Networking<br>&emsp; + Database | 20/04/2026 | 20/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 3) | - Create an AWS Free Tier account.<br>- Get familiar with the AWS Management Console interface.<br>- Install and configure AWS CLI on the local environment. | 21/04/2026 | 21/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 4) | - **CLI Practice:**<br>&emsp; + Configure Access Key & Secret Key.<br>&emsp; + Test basic commands (**aws sts get-caller-identity**, **aws ec2 describe-regions**). | 22/04/2026 | 22/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 5) | - Learn basic Amazon EC2 service:<br>&emsp; + Instance types.<br>&emsp; + AMI (Amazon Machine Image).<br>&emsp; + Differentiate between EBS and Instance Store.<br>&emsp; + Learn about Elastic IP. | 23/04/2026 | 23/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 6) | - **EC2 Practice:**<br>&emsp; + Launch 1 Linux EC2 instance.<br>&emsp; + Create a Key Pair and successfully connect via SSH.<br>&emsp; + Attach an EBS volume to the EC2 instance. | 24/04/2026 | 24/04/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Achievements:
* Clearly understood the overall architecture of AWS and distinguished the functions of the main service groups (Compute, Storage, Network, Database).
* Successfully created an AWS Free Tier account to use throughout the internship project.
* Successfully configured the local working environment: integrated AWS CLI, and declared standard security credentials using Access/Secret Keys.
* Smoothly operated the first virtual server: manually deployed a Linux distribution on Amazon EC2, set up basic Security Groups, and accessed it remotely via SSH protocol.
* Became more proficient in using AWS Documentation for reference when configuring services.

---
![AWS CLI Configuration](/workshop_intership_report/images/1-Worklog/1.1-Week1/week1-1.png)
<p align="center"><i>Figure 1: Successfully verified AWS CLI configuration on the local machine using the <b>aws sts get-caller-identity</b> command.</i></p>

![EC2 Dashboard](/workshop_intership_report/images/1-Worklog/1.1-Week1/week1-2.png)
<p align="center"><i>Figure 2: EC2 virtual server successfully created and operating (Running status) on the AWS Management Console.</i></p>

![SSH Terminal](/workshop_intership_report/images/1-Worklog/1.1-Week1/week1-3.png)
<p align="center"><i>Figure 3: Successfully connected via SSH into the EC2 instance from the local terminal.</i></p>