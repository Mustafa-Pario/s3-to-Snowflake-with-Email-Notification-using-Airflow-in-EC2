# s3-to-Snowflake-with-Email-Notification-using-Airflow-in-EC2

This project automates data ingestion from Amazon S3 to Snowflake using Apache Airflow running on an EC2 instance, with email notifications for task success or failure.

<p align="center">
  <img width="1000" height="550" alt="Project_Diagram"
       src="https://github.com/user-attachments/assets/24faced3-1a39-4346-a1fa-74927dafc95d" />
</p>

## 📌 Project Overview

The goal of this project is to build an end-to-end, production-style data pipeline that:

- Extracts data from Amazon S3

- Loads it into Snowflake

- Orchestrates the workflow using Apache Airflow

- Sends email notifications on DAG success or failure

- Runs Airflow on an EC2 instance

This simulates a real-world data engineering use case with cloud services and orchestration.


## 🏗️ Architecture

### Flow:

- Data is stored in an S3 bucket

- Airflow DAG is triggered (manually or on schedule)

- Airflow copies data from S3 into Snowflake

- Email notification is sent based on task status
  

## 🛠️ Tech Stack

- AWS S3 – Source data storage

- AWS EC2 – Hosting Apache Airflow

- Apache Airflow – Workflow orchestration

- Snowflake – Cloud data warehouse

- Python – DAG and task logic

- SMTP / Email Service – Notifications
  

## ⚙️ Prerequisites

### Before running this project, make sure you have:

AWS account with:
- S3 bucket

- EC2 instance

- Apache Airflow installed on EC2

- Snowflake account

- Python

- SMTP credentials for email notifications


## 🔐 Airflow Connections & Variables

Configure the following in Airflow UI:

### Connections

aws_default
- AWS Access Key
- AWS Secret Key

snowflake_default
  - Account
  - Username
  - Password
  - Warehouse
  - Database
  - Schema
  - Email

Configure SMTP settings in airflow.cfg
  - Enable email_on_failure and/or email_on_success
 
## 🚀 How It Works

- Airflow DAG monitors or triggers the pipeline

- Uses Snowflake operator to copy data from S3

- Executes SQL to load data into Snowflake tables

- Sends email notification on:

Success ✅

Failure ❌


## ▶️ How to Run

- Start Airflow services on EC2:

airflow webserver
airflow scheduler


- Place the DAG file inside:

airflow/dags/


- Open Airflow UI:

http://<EC2_PUBLIC_IP>:8080


- Trigger the DAG manually or wait for the schedule


## 📧 Email Notifications

Email alerts are sent automatically when:

A task fails

The DAG completes successfully

Helps with monitoring and quick issue resolution


## ✅ Use Cases

- Automated data ingestion

- Cloud data pipelines

- Data engineering portfolio project

- Production-style Airflow workflows
