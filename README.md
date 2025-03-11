# Reddit Data Pipeline using AWS Services

## Table of Contents

- [Description](#description)
- [Architecture](#architecture)
- [Code-Flow](#code-flow)
- [Module-Explanation](#module-explanation)
- [Future-Development](#future-development)


## Description
This project demonstrates a data pipeline solution to extract, transform, and load (ETL) Reddit data into a Redshift data warehouse. The pipeline leverages a combination of tools and services including Apache Airflow, Celery, PostgreSQL, Amazon S3, AWS Glue, Amazon Athena, and Amazon Redshift.

## Architecture
![RedditDataEngineering.png](assets%2FRedditDataEngineering.png)
1. **Reddit API**: Source of the data.
2. **Apache Airflow & Celery**: Orchestrates the ETL process and manages task distribution.
3. **PostgreSQL**: Temporary storage and metadata management.
4. **Amazon S3**: Raw data storage.
5. **AWS Glue**: Data cataloging and ETL jobs.
6. **Amazon Athena**: SQL-based data transformation.
7. **Amazon Redshift**: Data warehousing and analytics.

## Code-Flow
The project is structured in a way that AWS Commands and Python scripts works together to Extract, Transform, Load the input data.

The pipeline is designed to:

1. Extract data from Reddit using its API.
2. Store the raw data into an S3 bucket from Airflow.
3. Transform the data using AWS Glue and Amazon Athena.
4. Load the transformed data into Amazon Redshift for analytics and querying.

## Module Explanation
- `dags/reddit_dag.py`: The main script to pipeline the process of Extract data from Reddit API and load into Amazon S3 bucket.
- `data/output/reddit_*.csv`: This file holds the output data which is stored in this file location.
- `etls/aws_etl.py`: This script contains Connection, Creation, Updation functions for s3 bucket under this file location.
- `etls/reddit_etl.py`: The script contains the functions to Extract, Transform, Load the data.
- `pipelines/aws_s3_pipeline.py`: The script holds the pipeline to AWS S3 bucket.
- `etls/reddit_pipeline.py`: The script holds the pipeline to reddit API calls for data extraction.
- `utils/constants.py`: The script holds all the AWS constant keys and values under this file location.

## Future-Development

1. To integrate Amazon redshift cluster with Amazon Quicksight to drive insights about the data.




