---
title: "Week 12: Project Finalization - API Integration, Data Storage (DynamoDB), Optimization & Final Report"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:
* Initialize a complete non-relational (NoSQL) database framework with Amazon DynamoDB to handle high-speed invoice-related operations.
* Build an API ecosystem (API Gateway combined with an AWS Lambda cluster) responsible for secure communication between the Backend and the ReactJS Frontend application.
* Apply identity authentication standards (Amazon Cognito), application-level security (AWS WAF), and automated redundant storage cleanup (S3 Lifecycle).

### Tasks Completed During the Week:

| Date | Tasks Performed | Start Date | Completion Date | Reference Materials (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - **Set up DynamoDB NoSQL infrastructure:**<br>&emsp; + Initialize 4 data tables with On-demand Read/write capacity settings to optimize costs: `InvoicesData`, `InvoicesPayments`, `UserCategories`, and `UserBudgets`.<br>&emsp; + Define accurate Partition keys for each table (e.g., `documentId` for the InvoicesData table, `userEmail` for User-related tables). | 06/07/2026 | 06/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - **Develop Lambda APIs Cluster (Backend):**<br>&emsp; + Write the `idp-api-presign` function to grant upload URLs (with a standard `Content-Type`) directly to the S3 `idp-ingest-bucket-1` bucket to resolve CORS 403 errors.<br>&emsp; + Build Get API functions: `idp-api-get-invoices` (handling Data Masking to hide tax codes), `idp-api-get-stats` (processing revenue charts), `idp-api-categories` (classifying Cloud/Operational expenses), and `idp-api-payments` (tracking UNPAID invoices). | 07/07/2026 | 07/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - **Build API Gateway & Cognito Auth:**<br>&emsp; + Deploy a REST API named `idp-rest-api` (Regional).<br>&emsp; + Bind endpoints (`/get-upload-url`, `/invoices`, `/stats`, etc.) to the respective Lambda functions using Lambda proxy integration and enable CORS.<br>&emsp; + Create the `idp-react-app` Cognito User Pool (SPA type), disable Self-registration (preventing unauthorized public registrations), and initialize a Cognito Authorizer on the API Gateway to protect the GET method. | 08/07/2026 | 08/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **Configure CDN Distribution & WAF Firewall:**<br>&emsp; + Configure AWS WAF with a Rate-based rule named `BlockSpamIP` to automatically block connections if an IP exceeds the threshold of 100 requests / 5 minutes, linking it directly to the API Gateway `dev` stage. | 09/07/2026 | 09/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **Cost Optimization & E2E Flow Acceptance:**<br>&emsp; + Set up an S3 Lifecycle rule named `Auto-Delete-Raw-Invoices` to automatically delete temporary files after 1 day under the `uploads/` prefix to free up storage space.<br>&emsp; + Conduct comprehensive end-to-end (E2E) testing of the business flow from Frontend to Backend. Compile architectural documentation, draft the final report, and prepare for the Bootcamp graduation project demo. | 10/07/2026 | 10/07/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Results Achieved:
* The database system on DynamoDB operates stably, with an accurate key organization structure serving ultra-high-speed (milliseconds) retrieval for the data analysis tables.
* The Backend API Gateway interface operates with absolute security against minor DDoS attacks thanks to WAF protection, while completely blocking anonymous access (only allowing users authenticated with a valid Cognito Token to pass through).
* Successfully optimized the storage garbage collection process (S3 Lifecycle) and maximized the distribution performance of static web assets. The project concludes successfully with a complete Serverless IDP system.

---
![DynamoDB Tables](../../images/1-Worklog/1.12-Week12/week12-1.png)
<p align="center"><i>Figure 1: The structure of 4 data tables successfully created on the Amazon DynamoDB NoSQL database service with On-demand Capacity mode to help optimize costs.</i></p>

![API Gateway Methods](../../images/1-Worklog/1.12-Week12/week12-2.png)
<p align="center"><i>Figure 2: Deploying resources and configuring the GET method on Amazon API Gateway directly integrated with AWS Lambda data processing functions.</i></p>

![AWS WAF Rule](../../images/1-Worklog/1.12-Week12/week12-3.png)
<p align="center"><i>Figure 3: Setting up the AWS WAF barrier with a Rate-limiting rule (BlockSpamIP) to protect the API infrastructure against massive spam access from malicious IP addresses.</i></p>

![AWS WAF Rule](../../images/1-Worklog/1.12-Week12/week12-4.png)
<p align="center"><i>Figure 4: Setting up the AWS WAF barrier with a Rate-limiting rule (BlockSpamIP) to protect the API infrastructure against massive spam access from malicious IP addresses.</i></p>

![Cognito Configuration](../../images/1-Worklog/1.12-Week12/week12-5.png)
<p align="center"><i>Figure 5: Setting up the Amazon Cognito User Pool Authorizer authentication module to block unauthorized requests, requiring users to send an Authorization Token before calling the API.</i></p>

![Cognito Configuration](../../images/1-Worklog/1.12-Week12/week12-6.png)
<p align="center"><i>Figure 6: Setting up the Amazon Cognito User Pool Authorizer authentication module to block unauthorized requests, requiring users to send an Authorization Token before calling the API.</i></p>