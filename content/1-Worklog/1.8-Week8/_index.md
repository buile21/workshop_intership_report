---
title: "Week 8: Infrastructure as Code (IaC) & Monitoring (AWS CloudFormation, AWS SAM, CloudWatch)"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---


### Week 8 Objectives:
* Grasp the philosophy of Infrastructure as Code (IaC) to automate, standardize, and version-control cloud infrastructure.
* Get familiar with AWS CloudFormation and the AWS Serverless Application Model (SAM) - specialized tools for rapidly deploying Serverless architectures.
* Set up automated monitoring, logging, and alerting systems using Amazon CloudWatch to ensure system reliability.

### Tasks carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - Learn about the AWS CloudFormation service:<br>&emsp; + Core concepts: Templates (YAML/JSON), Stacks, Resources, Parameters.<br>&emsp; + Benefits of automating resource provisioning. | 08/06/2026 | 08/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - Research AWS Serverless Application Model (SAM):<br>&emsp; + Compare SAM with traditional CloudFormation.<br>&emsp; + Understand the SAM template structure (**AWS::Serverless::Function**, **AWS::Serverless::Api**). | 09/06/2026 | 09/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - Learn about the Amazon CloudWatch monitoring service:<br>&emsp; + Differentiate between CloudWatch Metrics and CloudWatch Logs.<br>&emsp; + Mechanism of setting up automated alerts (CloudWatch Alarms). | 10/06/2026 | 10/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **CloudFormation Practice:**<br>&emsp; + Write a basic YAML template.<br>&emsp; + Deploy the **fcaj-week8-stack** via the CloudFormation interface to automatically create an S3 Bucket. | 11/06/2026 | 11/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **CloudWatch Practice:**<br>&emsp; + Test-run a Lambda function and access Log Groups to read execution logs.<br>&emsp; + Create a simple Alarm to monitor when the Lambda function's Errors metric exceeds a threshold. | 12/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Achievements:
* Completely changed the mindset regarding resource provisioning: shifting from manual "ClickOps" to managing infrastructure using professional, secure, and reusable code (IaC).
* Successfully deployed resources via an AWS CloudFormation Stack, clearly understanding the automated lifecycle of resource creation and deletion.
* Mastered Amazon CloudWatch, knowing how to trace Serverless application errors through Log Groups – a mandatory skill for debugging distributed systems.
* Mastered setting up automated Alarms to be notified when the system shows signs of overload or encounters errors.

---
![AWS CloudFormation Stack](/images/1-Worklog/1.8-Week8/week8-1.png)
<p align="center"><i>Figure 1: The AWS CloudFormation interface successfully deploying a Stack (CREATE_COMPLETE) that automatically provisions resources from a YAML template.</i></p>

![Amazon CloudWatch Logs](/images/1-Worklog/1.8-Week8/week8-2.png)
<p align="center"><i>Figure 2: The Log groups viewer on Amazon CloudWatch displaying detailed execution flows (Log streams) of the Serverless system.</i></p>

![Amazon CloudWatch Alarm](/images/1-Worklog/1.8-Week8/week8-3.png)
<p align="center"><i>Figure 3: Successfully configured an automated Alarm on CloudWatch to monitor service operational Metrics.</i></p>