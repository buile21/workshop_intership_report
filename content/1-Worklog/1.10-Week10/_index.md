---
title: "Week 10: Project Initialization - Serverless IDP Architecture Design & Ingesting Input Documents"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:
* Initialize a secure storage layer in the cloud to receive input documents and serve the Frontend.
* Apply event-driven architecture, establishing an automated communication flow between the storage service (Amazon S3) and the queue service (Amazon SQS).
* Prepare a strict security authorization system (IAM Role) for core AI analysis tasks in the following weeks.

### Tasks Completed During the Week:

| Date | Tasks Performed | Start Date | Completion Date | Reference Materials (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - **Set up S3 Bucket for document ingestion:**<br>&emsp; + Create a bucket named `idp-ingest-bucket-1` in us-east-1.<br>&emsp; + Disable ACLs and block all public access (Block all public access) to ensure absolute document security.<br>&emsp; + Configure CORS to allow PUT, POST, and GET methods so that the Frontend can communicate directly. | 22/06/2026 | 22/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - **Set up S3 Bucket to serve the Frontend:**<br>&emsp; + Create a bucket named `idp-frontend-bucket-01` in us-east-1.<br>&emsp; + Uncheck "Block all public access" to allow hosting public static content for the web application. | 23/06/2026 | 23/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - **Initialize Amazon SQS for task orchestration:**<br>&emsp; + Create a Standard queue named `idp-document-queue`.<br>&emsp; + Set the Visibility timeout to 2 minutes to allow sufficient time for the AI to process large documents.<br>&emsp; + Define an Access policy (Advanced) granting `sqs:SendMessage` permissions, specifying the source as the ingest bucket. | 24/06/2026 | 24/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **Configure Event Notifications:**<br>&emsp; + Set up an Event notification named `SendToSQS` on the Ingest bucket.<br>&emsp; + Capture all object creation events (`All object create events`) and route them directly to the newly created SQS Queue. | 25/06/2026 | 25/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **Configure IAM Role security authorization:**<br>&emsp; + Create a role named `idp-lambda-ai-role` dedicated to AWS Lambda with Lambda as the Trusted entity.<br>&emsp; + Grant exactly 5 required permissions: `AWSLambdaSQSQueueExecutionRole`, `AmazonS3ReadOnlyAccess`, `AmazonDynamoDBFullAccess`, `AmazonTextractFullAccess`, and `AmazonBedrockFullAccess`. | 26/06/2026 | 26/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Results Achieved:
* Successfully built a secure landing zone for invoice documents using the Amazon S3 storage service.
* Finalized the automated message flow: whenever an invoice is uploaded to S3, an event is immediately sent to the SQS queue to throttle processing, completely preventing system overload.
* Ensured the principle of Least Privilege with the IAM Role, leaving the infrastructure fully prepared for integration with the AI engine next week.

---
![Block Public Access S3](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-1.png)
<p align="center"><i>Figure 1: Configuring "Block all public access" on the S3 Bucket to ensure absolute security for input invoice documents.</i></p>

![Block Public Access S3](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-2.png)
<p align="center"><i>Figure 2: Configuring "Block all public access" on the S3 Bucket to ensure absolute security for input invoice documents.</i></p>

![SQS Access Policy](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-3.png)
<p align="center"><i>Figure 3: Configuring the Access policy to allow Amazon SQS to receive trigger messages directly from Amazon S3.</i></p>

![SQS Access Policy](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-4.png)
<p align="center"><i>Figure 4: Configuring the Access policy to allow Amazon SQS to receive trigger messages directly from Amazon S3.</i></p>

![S3 Event Notification](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-5.png)
<p align="center"><i>Figure 5: Setting up the Event Notification (SendToSQS) to automatically capture file upload events and route them to the SQS queue.</i></p>

![S3 Event Notification](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-6.png)
<p align="center"><i>Figure 6: Setting up the Event Notification (SendToSQS) to automatically capture file upload events and route them to the SQS queue.</i></p>

![IAM Role Permissions](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-7.png)
<p align="center"><i>Figure 7: Initializing the IAM Role with specialized permission policies (S3, DynamoDB, Textract, SQS) in preparation for the AI document processing engine.</i></p>

![IAM Role Permissions](/workshop_intership_report/images/1-Worklog/1.10-Week10/week10-8.png)
<p align="center"><i>Figure 8: Initializing the IAM Role with specialized permission policies (S3, DynamoDB, Textract, SQS) in preparation for the AI document processing engine.</i></p>