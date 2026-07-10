---
title: "Week 6: Serverless Computing (AWS Lambda, Amazon API Gateway, AWS Step Functions)"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Week 6 Objectives:
* Understand the Serverless architecture philosophy: No server management, auto-scaling, and pay-as-you-go pricing.
* Practice writing and deploying serverless source code with AWS Lambda, integrating IAM Roles to interact securely with S3 and DynamoDB.
* Build RESTful API communication gateways using Amazon API Gateway to connect the Frontend/Client with the Lambda Backend.
* Master how to orchestrate multiple Lambda functions into a complete business process (Workflow) using AWS Step Functions.

### Tasks carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - Learn about AWS Lambda compute service:<br>&emsp; + Operating mechanism: Triggers, Execution Environment, Cold Start / Warm Start.<br>&emsp; + Dependency management and Lambda Layers.<br>&emsp; + Timeout and Memory configuration. | 25/05/2026 | 25/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - Learn about Amazon API Gateway service:<br>&emsp; + Differentiate between REST API, HTTP API, and WebSocket API.<br>&emsp; + Lambda Proxy Integration mechanism.<br>&emsp; + Managing Stages and Deployments. | 26/05/2026 | 26/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - Research AWS Step Functions (Orchestration):<br>&emsp; + Differentiate between Standard and Express Workflows.<br>&emsp; + Learn the Amazon States Language (ASL).<br>&emsp; + Error handling and Retry mechanisms in the workflow. | 27/05/2026 | 27/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **Lambda & API Gateway Practice:**<br>&emsp; + Write the **fcaj-idp-hello-function** Lambda function using Python/Node.js.<br>&emsp; + Grant basic permissions (Execution Role) for the function.<br>&emsp; + Create a REST API on API Gateway, route the GET method to call the newly created Lambda function, and test it using Postman/Browser. | 28/05/2026 | 28/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **Step Functions Practice:**<br>&emsp; + Use Workflow Studio to drag and drop a simple State Machine named **fcaj-idp-doc-workflow**.<br>&emsp; + Simulate the steps: Pass (Start) -> Task (Invoke Lambda) -> Choice (Categorize success/failure).<br>&emsp; + Run a test (Start Execution) and observe the visual workflow chart. | 29/05/2026 | 29/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Achievements:
* Discarded the traditional server management (EC2) mindset, successfully transitioned to the mindset of deploying independent source code with AWS Lambda.
* Knew how to securely open external communication flows by configuring Amazon API Gateway to connect directly with Lambda (a complete Serverless Backend).
* Got familiar with the ASL language and Workflow Studio, manually designed a draft document processing workflow (State Machine) using the graphical interface.
* Understood how to break down a monolithic application into small, compact microservices functions, smoothly orchestrating them with Step Functions to avoid nested Lambda invocations (Anti-pattern).

---
![AWS Lambda Function](/images/1-Worklog/1.6-Week6/week6-1.png)
<p align="center"><i>Figure 1: The management interface of the <b>fcaj-idp-hello-function</b> on AWS Lambda along with the source code ready to be executed.</i></p>

![API Gateway Integration](/images/1-Worklog/1.6-Week6/week6-2.png)
<p align="center"><i>Figure 2: Successful integration configuration between Amazon API Gateway (GET method) and AWS Lambda to form a complete API endpoint.</i></p>

![Step Functions Workflow](/images/1-Worklog/1.6-Week6/week6-3.png)
<p align="center"><i>Figure 3: Visual Workflow chart of a State Machine simulating the document processing workflow on AWS Step Functions.</i></p>