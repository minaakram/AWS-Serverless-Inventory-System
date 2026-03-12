# Event-Driven Inventory Management: AWS Serverless Architecture

## Overview
This project implements a fully automated, **Event-Driven Inventory System** using a serverless approach. The architecture handles data ingestion, processing, and real-time alerting without the need for server provisioning or management, ensuring high scalability and cost-efficiency.

## Architecture & Service Stack
The system utilizes a decoupled workflow to process inventory updates:

* **Data Ingestion (Amazon S3):** Serves as the landing zone for raw inventory datasets (CSV).
* **Compute (AWS Lambda):** Triggered automatically by S3 events to execute Python-based business logic for data validation and parsing.
* **NoSQL Storage (Amazon DynamoDB):** Stores processed inventory records with high throughput and low latency.
* **Notification Service (Amazon SNS):** Orchestrates real-time email alerts triggered by specific stock threshold conditions.

## Key Technical Attributes
* **Serverless Execution:** Eliminated operational overhead by utilizing AWS Lambda for on-demand compute.
* **Event-Driven Scalability:** The system scales natively with the volume of concurrent file uploads.
* **Automated Workflow:** Seamless integration between S3 triggers and Lambda functions for zero-touch processing.

## Implementation Gallery

### 1. Event Source (Amazon S3)
![S3 Bucket](./s3.png)
*S3 Bucket configured with event notifications to trigger the processing pipeline.*

### 2. Compute Logic (AWS Lambda)
![Function Overview](./Function%20Overview.png)
*Lambda function architecture and environment configuration.*

### 3. State Management (DynamoDB)
![DynamoDB](./DynamoDB.png)
*Finalized inventory state stored in the NoSQL table after successful processing.*

### 4. Real-time Alerting (Amazon SNS)
![Email Alert](./Confirmed%20email.png)
*Automated SNS notification confirming out-of-stock events.*

## Repository Structure
* `/scripts`: Python source code for Lambda functions.
* `/data`: Sample CSV inventory datasets used for system validation.
