---
title: "Week 11: Project Implementation - Building the Core Processing Engine (Amazon Textract, AWS Lambda)"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:
* Build and configure a serverless computing environment with AWS Lambda to handle large data processing loads.
* Integrate Amazon Textract using Python (`boto3` library) to automatically extract key data fields from invoices via natural language queries.
* Connect the data flow from the Amazon SQS system for asynchronous event processing and store the structured results in the database.

### Tasks Completed During the Week:

| Date | Tasks Performed | Start Date | Completion Date | Reference Materials (AWS Study Group Link) |
| :--- | :--- | :--- | :--- | :--- |
| **Monday**<br>(Day 1) | - **Initialize the AI-dedicated AWS Lambda function:**<br>&emsp; + Create the `idp-ai-worker` function using the Author from scratch option with a Python 3.12 Runtime environment.<br>&emsp; + Configure the Permissions section, selecting the Custom execution role as `idp-lambda-ai-role`, which was fully configured with security policies last week. | 29/06/2026 | 29/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Tuesday**<br>(Day 2) | - **Resource Optimization & Trigger Configuration:**<br>&emsp; + Access General configuration, upgrade the Memory configuration from 128 MB to 256 MB and the maximum Timeout to 1 min 0 sec to optimize the task of running the AI data extraction model.<br>&emsp; + Configure Add trigger from the Amazon SQS source, pointing specifically to the `idp-document-queue` with a standard Batch size of 10. | 30/06/2026 | 30/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Wednesday**<br>(Day 3) | - **Message Reception Logic Programming (Part 1):**<br>&emsp; + Write Python source code using the `boto3` library to initialize a client connecting to the Amazon Textract and Amazon DynamoDB services.<br>&emsp; + Implement the `lambda_handler` function to loop through the `Records` asynchronous event list pushed from SQS, decode the JSON payload to accurately extract the `bucket_name` and `object_key` information (cleaned using `urllib.parse.unquote_plus`). | 01/07/2026 | 01/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Thursday**<br>(Day 4) | - **Amazon Textract AI Integration Programming (Part 2):**<br>&emsp; + Use the `analyze_document` method with the parameter configuration `FeatureTypes=["QUERIES"]`.<br>&emsp; + Set up the `QueriesConfig` to pose 4 natural extraction questions: Invoice number (`invoice_number`), Date (`date`), Total amount (`total_amount`), and Vendor name (`vendor_name`).<br>&emsp; + Write a function to iterate through the `Blocks` to accurately map the relationships (`Relationships`) between the query (`QUERY`) and the answer (`ANSWER`) into a clear JSON structure. | 02/07/2026 | 02/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **Friday**<br>(Day 5) | - **NoSQL Database Storage & Flow Testing:**<br>&emsp; + Connect to the `InvoicesData` table on DynamoDB.<br>&emsp; + Create a storage document structure consisting of the primary key `documentId` (randomly generated using `uuid.uuid4()`), original file name, system upload time (`datetime.now().isoformat()`), and the newly extracted AI data block.<br>&emsp; + Execute the `table.put_item()` command, Deploy the source code, and perform a test upload of an invoice to S3 to verify the end-to-end (E2E) automated processing flow. | 03/07/2026 | 03/07/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Results Achieved:
* The Lambda compute engine operates stably, automatically scaling the number of executions based on the actual number of messages pushed from the SQS queue.
* Successfully applied the Amazon Textract Queries feature to accurately extract complex unstructured data fields on invoices into a JSON structure without the need for fixed templates (Template-less).
* Perfectly closed asynchronous processing flow: File pushed to S3 -> SQS receives the event -> Triggers Lambda for AI processing -> Successfully stores the clean results directly to DynamoDB, preparing the data for the Frontend application layer.

---
![Initialize Lambda](../../images/1-Worklog/1.11-Week11/week11-1.png)
<p align="center"><i>Figure 1: Successful initialization interface of the idp-ai-worker Lambda function using the Python 3.12 runtime environment and a specialized Execution role configuration.</i></p>

![Lambda Memory Config](../../images/1-Worklog/1.11-Week11/week11-2.png)
<p align="center"><i>Figure 2: Configuration adjustments increasing RAM resources (256 MB) and Timeout limits (1 minute) to well-serve heavy AI document analysis tasks.</i></p>

![SQS Trigger Config](../../images/1-Worklog/1.11-Week11/week11-3.png)
<p align="center"><i>Figure 3: Configuring the Amazon SQS queue (idp-document-queue) linkage as an automatic trigger for the Lambda function with a batch processing architecture of Batch size 10.</i></p>