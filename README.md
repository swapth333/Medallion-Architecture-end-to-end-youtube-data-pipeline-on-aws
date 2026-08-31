# Medallion Architecture – End-to-End YouTube Data Pipeline on AWS

## Overview

This project implements an end-to-end data engineering pipeline using AWS services and the Medallion Architecture.

The pipeline ingests trending YouTube video data through the YouTube Data API, stores raw data in Amazon S3, transforms and cleans the data using AWS Lambda and AWS Glue, performs data quality validation, and creates analytics-ready Gold datasets for querying through Amazon Athena.

## Architecture

The pipeline follows a Bronze → Silver → Gold architecture.

### Bronze Layer
Raw YouTube API JSON data is stored in Amazon S3.

### Silver Layer
AWS Glue and AWS Lambda transform raw data into cleansed and standardized Parquet datasets.

Data quality checks validate:
- Row counts
- Null percentages
- Schema
- Value ranges
- Data freshness

### Gold Layer
AWS Glue creates analytics-ready datasets including:

- Trending Analytics
- Channel Analytics
- Category Analytics

### Orchestration

AWS Step Functions orchestrates the complete workflow.

### Monitoring and Alerting

Amazon CloudWatch provides logging and monitoring.

Amazon SNS sends pipeline success and failure notifications.

### Query Layer

Amazon Athena is used to query the analytics-ready Gold datasets.

## AWS Services

- Amazon S3
- AWS Lambda
- AWS Glue
- AWS Step Functions
- Amazon Athena
- Amazon SNS
- Amazon CloudWatch
- AWS IAM

## Technologies

- Python
- PySpark
- Pandas
- AWS SDK for Python (Boto3)
- AWS Data Wrangler
- Apache Parquet
- SQL

## Pipeline Flow

YouTube Data API
→ Lambda
→ S3 Bronze
→ Lambda / AWS Glue
→ S3 Silver
→ Data Quality
→ AWS Glue
→ S3 Gold
→ Athena 

scripts/
sql/
Report/
data/
