# 🚀 Overview
This project builds an automated ETL pipeline that collects Spotify data using the Spotify API, processes and stores it in AWS, and ultimately loads it into Snowflake for analytics and reporting. The workflow leverages Python for data extraction and transformation, AWS for orchestration and storage, and Snowflake (via Snowpipe) for scalable data loading.

# 🧰 Tech Stack
Python – Data extraction and transformation

AWS – S3, Lambda, CloudWatch

Snowflake – Cloud data warehouse with Snowpipe integration

# ⚙️ Architecture
1. Data Extraction (Python + AWS Lambda)
Python scripts interface with the Spotify API to pull raw track/artist data in JSON format.

An AWS Lambda function handles this process and stores the raw output into an S3 bucket.

2. Data Transformation (AWS Lambda)
A second Lambda function is triggered upon new object creation in S3 (object event).

This function transforms and cleans the raw data and writes it back into a different S3 location (transformed zone).

3. Data Loading (Snowpipe + Snowflake)
Snowpipe continuously monitors the transformed S3 location.

As new data arrives, it is automatically ingested into Snowflake tables for analysis.


![1742363494352](https://github.com/user-attachments/assets/829e5ed2-f3d6-4590-b424-85c0f2afb788)
