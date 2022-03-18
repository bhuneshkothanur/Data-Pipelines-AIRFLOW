# Sparkify Airflow Data Pipeline

### Project Summary: 
This project builds a data pipeline for Sparkify using Apache Airflow that automates and monitors the running of an ETL pipeline.

The ETL first stages the data into staging_events and staging_songs. The the data gets loaded into Fact and Dimension tables.Song and log data in JSON format. A star schema has been used to allow the Sparkify team to readily run queries to analyze user activity on their app. The Airflow dag has been configured to perform data quality checks.

### Structure
udac_example_dag.py contains the tasks and dependencies of the DAG. It is placed in the dags directory. 
create_tables.sql contains the SQL queries used to create all the required tables in Redshift.
sql_queries.py contains the SQL queries used in the ETL process.

stage_redshift.py contains StageToRedshiftOperator, which copies JSON data from S3 to staging tables in the Redshift data warehouse.
load_dimension.py contains LoadDimensionOperator, which loads a dimension tables from the staging tables.
load_fact.py contains LoadFactOperator, which loads the fact table from data in the staging tables.
data_quality.py contains DataQualityOperator, which runs a data quality check by passing a SQL query and expected result as arguments.

### To Run the DAG
Create AWS and Redshift connections and tun on the DAG.


**REFERENCES**

> Udacity Knowledge hub.