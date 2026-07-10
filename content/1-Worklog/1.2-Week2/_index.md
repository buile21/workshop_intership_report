---
title: "Week 2: Deep Dive into Storage & Access Management (Amazon S3, IAM)"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Week 2 Objectives:
* Clearly understand and practice the Amazon S3 storage service in depth.
* Master identity management and secure authorization mechanisms with AWS IAM following the Least Privilege principle.
* Proficiently interact with S3 via AWS CLI and configure Resource Tags for resource management.

### Tasks carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - Learn about the Amazon S3 service:<br>&emsp; + Concepts: Buckets, Objects, Keys.<br>&emsp; + Differentiate Storage Classes (Standard, Infrequent Access, Glacier...).<br>&emsp; + Versioning and Object Lock features. | 27/04/2026 | 27/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - **S3 & CLI Practice:**<br>&emsp; + Create an S3 Bucket ensuring a Global Unique Name.<br>&emsp; + Use AWS CLI to upload/download files (**aws s3 cp**, **aws s3 sync**).<br>&emsp; + Write a Bucket Policy to block public access. | 28/04/2026 | 28/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - Deep dive into AWS IAM:<br>&emsp; + Differentiate between Users, Groups, Roles, and Policies.<br>&emsp; + Understand the structure of a JSON IAM Policy (Effect, Action, Resource).<br>&emsp; + Why you should use a Service Role instead of Access Keys. | 29/04/2026 | 29/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **IAM Practice (Self-study/Research):**<br>&emsp; + Create an IAM Role with **AmazonS3ReadOnlyAccess** permission.<br>&emsp; + Attach this Role to the EC2 instance (created in week 1) so EC2 can read files from S3 without storing hardcoded Access Keys. | 30/04/2026 | 30/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - Learn and practice AWS Resource Tags:<br>&emsp; + Assign Tags (Project: IDP, Environment: Dev) to the S3 Bucket and EC2.<br>&emsp; + Summarize and clean up resources to avoid incurring costs. | 01/05/2026 | 01/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Achievements:
* Successfully created and configured an Amazon S3 Bucket with strict security policies (blocked Public Access).
* Proficiently applied AWS CLI commands to sync and transfer document data to the S3 storage space.
* Built a solid security foundation for the project: successfully set up an IAM Role and attached it to resources instead of manually managing security keys (Access Keys).
* Read, understood, and self-wrote basic JSON IAM Policies to accurately grant permissions to services.
* Formed the habit of systematically tagging resources, which greatly helps in managing AWS costs later on.

---
![S3 Bucket Creation](/images/1-Worklog/1.2-Week2/week2-1.png)
<p align="center"><i>Figure 1: Amazon S3 Bucket successfully created with the Block all public access feature enabled.</i></p>

![CLI S3 Copy](/images/1-Worklog/1.2-Week2/week2-2.png)
<p align="center"><i>Figure 2: Using the <b>aws s3 cp</b> command to successfully upload a sample document from the local computer to the S3 Bucket.</i></p>

![IAM Role Creation](/images/1-Worklog/1.2-Week2/week2-3.png)
<p align="center"><i>Figure 3: The IAM interface showing the newly created Role with S3 access permissions successfully attached to the EC2 instance.</i></p>