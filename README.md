# DataWarehouse_in_AWS-Redshift

![etl](https://github.com/PurushothamVadde/DataWarehouse_in_AWS-Redshift/blob/master/s3to%20redshift.png)

This project has below modules:
- [Project Understanding](#project-understanding)
- [Data](#data)
- [AWS Setup](#aws-setup)
- [Database Schema Design](#database-schema-design)
- [ETL Pipeline](#etl-pipeline)
- [Data Analytics](#data-analytics)


## Project Understanding
The Goal of this project is to build a ETL pipeline that will be able to Extract the **Songs** data from AWS S3 bucket and Transform the data to make it friendly for Analytics and load the data into Fact and Dim tables in Redshift, so that the data can be used by Business Intelligence and visualization apps that will help the Data Analytics team to better understand what are the most frequently played songs in the music app.

## Data
The Datasets log_data and song_data used for this project are retrived from the s3 bucket and are in the json format.
- Song data: s3://udacity-dend/song_data
- Log data: s3://udacity-dend/log_data

## AWS Setup
## Database Schema Design
## ETL Pipeline
## Data Analytics
