---
title: "Week 9: Application Integration & Event-Driven Architecture (Amazon SQS, SNS, EventBridge)"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---


### Week 9 Objectives:
* Understand the philosophy of Event-Driven Architecture (EDA) and the benefits of decoupling services in a Serverless system.
* Master the operational mechanisms, configuration parameters, and real-world use cases of the Amazon SQS (Simple Queue Service) message queue and the Amazon SNS (Simple Notification Service) publish/subscribe service.
* Use Amazon EventBridge to set up flexible event routing rules, acting as the backbone for controlling the document flow for the IDP system.

### Tasks carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - Learn about the Amazon SQS message queue service:<br>&emsp; + Differentiate between Standard Queue and FIFO Queue.<br>&emsp; + Parameters: Visibility Timeout, Long Polling vs Short Polling.<br>&emsp; + Junk mail handling mechanism with Dead Letter Queue (DLQ). | 15/06/2026 | 15/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - Research the Amazon SNS notification service:<br>&emsp; + Concepts of Topics, Subscriptions (Email, SMS, HTTP, Lambda, SQS).<br>&emsp; + Fan-out pattern scalable architecture (SNS sends to multiple SQS simultaneously). | 16/06/2026 | 16/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - Learn about Amazon EventBridge (Event Bus):<br>&emsp; + Event routing model via: Event source, Rules, and Targets.<br>&emsp; + How to capture resource state change events from other AWS services. | 17/06/2026 | 17/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **SQS & SNS Practice (Fan-out model):**<br>&emsp; + Create an SNS Standard Topic named **fcaj-idp-notifications**.<br>&emsp; + Create an SQS Standard Queue named **fcaj-idp-document-queue**.<br>&emsp; + Configure a Subscription for SQS to receive messages from the SNS Topic, test sending a message (Publish message) from SNS to verify messages are automatically routed to SQS. | 18/06/2026 | 18/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **EventBridge Practice:**<br>&emsp; + Create an EventBridge Rule that listens to events from an S3 Bucket when a new file is uploaded.<br>&emsp; + Route that event to automatically trigger a Target which is an SQS queue or a Lambda function, checking the event payload being transmitted. | 19/06/2026 | 19/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Achievements:
* Shifted system design mindset from Synchronous to Asynchronous, helping the IDP system increase load tolerance and minimize bottleneck risks.
* Successfully deployed the Fan-out model (SNS + SQS), understanding how a single input event can simultaneously trigger multiple independent background processing tasks (e.g., extracting text while sending an email notification).
* Mastered Amazon EventBridge, knowing how to accurately manage and filter system events according to Event Patterns.
* Improved distributed data flow debugging skills by tracking messages moving back and forth between application integration services.

---
![SNS Topic and SQS Subscription](/images/1-Worklog/1.9-Week9/week9-1.png)
<p align="center"><i>Figure 1: Amazon SNS Topic configuration successfully connected to the Amazon SQS queue following the Fan-out architecture model.</i></p>

![SQS Message Polling](/images/1-Worklog/1.9-Week9/week9-2.png)
<p align="center"><i>Figure 2: The SQS Explore messages interface showing messages successfully pushed into the queue and ready to be processed.</i></p>

![EventBridge Rule Configuration](/images/1-Worklog/1.9-Week9/week9-3.png)
<p align="center"><i>Figure 3: An Amazon EventBridge Rule successfully configured to capture events from the S3 Bucket and forward them to the Target.</i></p>