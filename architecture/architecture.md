             YouTube Data API
                    │
                    ▼
          Lambda – Ingestion
                    │
                    ▼
               S3 Bronze
                    │
          ┌─────────┴─────────┐
          │                   │
          ▼                   ▼
      Lambda             AWS Glue

JSON → Parquet Bronze → Silver
│ │
▼ ▼
S3 Silver
│
▼
Data Quality
Lambda
│
┌─────┴─────┐
│ │
PASS FAIL
│ │
▼ ▼
AWS Glue SNS
Silver → Gold Alert
│
▼
S3 Gold
│
▼
Athena
│
▼
Analytics
