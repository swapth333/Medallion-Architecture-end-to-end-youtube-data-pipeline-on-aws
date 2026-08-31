Bronze Bucket Name - yt-data-pipeline-swap-bronze-dev
Silver Bucket Name- yt-data-pipeline-swap-silver-dev
Gold Bucket Name - yt-data-pipeline-swap-gold-dev

Scripts Bucket - yt-data-pipeline-swap-scripts-dev

SNS arn - arn:aws:sns:us-east-1:903126308419:yt-data-pipeline-alerts-dev:458ccdbd-ead2-4424-83bc-e31527ec3a57

glue bronze yt_pipeline_bronze_dev
glue silver yt_pipeline_silver_dev
glue gold yt_pipeline_gold_dev

Glue job script parameters bronze to silver
--bronze_database yt_pipeline_bronze_dev
--bronze_table raw_statistics
--silver_bucket yt-data-pipeline-swap-silver-dev
--silver_database yt_pipeline_silver_dev
--silver_table clean_statistics

Glue job parameters silver to gold

--silver_database yt_pipeline_silver_dev
--silver_table clean_statistics
--gold_bucket yt-data-pipeline-swap-gold-dev
--gold_database yt_pipeline_gold_dev
--gold_table

ATHENA_WORKGROUP primary
ATHENA_S3_OUTPUT s3://yt-data-pipeline-swap-glue-athena-query-result/
AWS_REGION us-east-1
