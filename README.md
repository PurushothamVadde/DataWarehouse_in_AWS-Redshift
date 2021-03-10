# DataWarehouse_in_AWS-Redshift

![etl](https://github.com/PurushothamVadde/DataWarehouse_in_AWS-Redshift/blob/master/s3to%20redshift.png)

This project has below modules:
- [Project Understanding](#project-understanding)
- [Data](#data)
- [AWS Setup](#aws-setup)
- [ETL Pipeline](#etl-pipeline)
- [Data Analytics](#data-analytics)


## Project Understanding
The Goal of this project is to build a ETL pipeline that will be able to Extract the **Songs** data from AWS S3 bucket and Transform the data to make it friendly for Analytics and load the data into Fact and Dim tables in Redshift, so that the data can be used by Business Intelligence and visualization apps that will help the Data Analytics team to better understand what are the most frequently played songs in the music app.

## Data
The Datasets log_data and song_data used for this project are retrived from the s3 bucket and are in the json format.
- Song data: s3://udacity-dend/song_data
- Log data: s3://udacity-dend/log_data

## AWS Setup
As part of this project we have setup the AWS Redshift with Iac(Infrastructure as Code). 
design the config file as below with AWS iam credentials, Redshift cluster details and s3 bucket details so that we can use this config file in set setup the Redshift cluster and access the AWS and s3 bucket.

> [DWH] \
  CLUSTER_TYPE = multi-node \
  NUM_NODES = 4 \
  NODE_TYPE = dc2.large \ 
  IAM_ROLE_NAME = XXXXXXXX \
  CLUSTER_IDENTIFIER = XXXXXXX \
  HOST = sparkifycluster.XXXXXXXXX.us-west-2.redshift.amazonaws.com \
  DB_NAME = sparkify \
  DB_USER = XXXXXXX \
  DB_PASSWORD = XXXXXXX \
  DB_PORT = 5439 \
  [IAM_ROLE] \
  ARN = arn:aws:iam::XXXXXXX:role/myXXXXXXRole \
  [S3] \
  LOG_DATA = 's3://udacity-dend/log_data' \
  LOG_JSONPATH = 's3://udacity-dend/log_json_path.json' \
  SONG_DATA = 's3://udacity-dend/song_data' \
  [AWS] \
  ACCESS_KEY = XXXXXXXXXXXXXXXXX \
  SECRET_KEY = XXXXXXXXXXXXXXXXXXXXXXXX \
  [CLUSTER] \
  HOST = sparkifycluster.XXXXXX.us-west-2.redshift.amazonaws.com \
  DB_NAME = sparkify \
  DB_USER = XXXXX \
  DB_PASSWORD = XXXXX \
  DB_PORT = 5439 \
## ETL Pipeline
- In this step the data from the S3 bucket and stored into the redshift by creating the staging tables.
- We created the Fact and Dimension tables by following the star schema which is more suitable for the OLAP operations which is the purpose of ETL.
- The data in the staging tables need to transformed to fit the data model in the Fact and Dimension tables such as the source timestamo is in unix format and need to convert to year, month, day , hour etc.
## Data Analytics

### Fact Table
![fact](https://github.com/PurushothamVadde/DataWarehouse_in_AWS-Redshift/blob/master/images/fact.png)
### Dimension Tables
#### user
![user](https://github.com/PurushothamVadde/DataWarehouse_in_AWS-Redshift/blob/master/images/user.png)
#### artist
![artist](https://github.com/PurushothamVadde/DataWarehouse_in_AWS-Redshift/blob/master/images/artist.png)
#### song
![song](https://github.com/PurushothamVadde/DataWarehouse_in_AWS-Redshift/blob/master/images/song.png)
#### time
![time](https://github.com/PurushothamVadde/DataWarehouse_in_AWS-Redshift/blob/master/images/time.png)
