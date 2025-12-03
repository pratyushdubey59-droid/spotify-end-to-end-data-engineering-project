# spotify-end-to-end-data-pipeline-project

### Introduction
## In this project we will build an ETL (Extract, Transform, Load) pipeline using the spotify API on AWS. The pipeline wil retrieve data from the spotify API, transform it to a desired format, and load it into an AWS data store.
## Architecture
![Architecture Diagram](https://github.com/pratyushdubey59-droid/spotify-end-to-end-data-engineering-project/blob/main/spotify_data_pipeline.jpg)

### About Dataset/API
This API contains information about music artists, albums and songs - [Spotify API](https://developer.spotify.com/documentation/web-api)


### Services Used
1. **S3(Simple Storage Service):** Amazon S3 (Simple Storage Service) is a highly scalable object storage service that can store and retrieve any amount of data from anywhere on the web. It is commonly used to store and distribute large media files, data backups, static website files.

2. **AWS Lambda**:AWS Lambda is an event-driven, serverless compute service from Amazon Web Services that runs code without you needing to provision or manage servers. You can use Lambda to run code in response to events like changes in S3, DynamoDB, or other AWS services.

3. **Cloud Watch:** Amazon Cloudwatch is monitoring service for AWS resource and the applucation you run on them. You can use CloudWatch to collect and track metrics, collect and monitor log files, and set alarms.

4. **Glue Crawler:** AWS Glue Crawler is fully managed service that automatically crawls your data sources, identifies, data formats, and infers schemas to create an AWS Glue Data Catalog.

5. **Data Catalog:** The AWS Glue Data Catalog is a centralized metadata repository for all your data assets across various data sources. It provides a unified interface to store and query information about data formats, schemas, and sources.

6. **Amazon Athena:** AWS Athena is a serverless, interactive query service that uses standard SQL to analyze data directly in Amazon S3, without requiring you to load data into a separate system. You can use Athena to analyze data in your Glue Data Catalog or in S3 buckets.

### Install Packages
```
pip install pandas
pip insyall numpy
pip install spotipy
```

### Project Execution Flow
Extract Data from API -> Lambda Trigger (every 1 hour) -> Run Extract Code -> Store Raw Data -> Trigger Transform Function -> Transform Data and Load It -> Query Using Athena
