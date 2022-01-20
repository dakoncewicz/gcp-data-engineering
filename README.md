# gcp-data-engineering
Data Engineering - Hands-on projects

Key words: Dataproc, Spark, Py-spark, Bigquery, GCS

Topics:
1. Batch Processing and ETL using BigQuery, Dataproc and PySpark ETL job
2. Batch data ingestion (into Bigquery/GCD ) using Appache Sqoop and DataProc

# Batch Processing and ETL using BigQuery, Dataproc and PySpark ETL job
## Batch ETL - Bigquery
### 1. Loading data into non-partinioned table
   - create a bucket sid-etl /bigquery-etl
   - uplad files to bucket 
   - choose a project/create one bigquery-etl
   - create dataset data-analysis
   - create a tabel within bigdata-etl: data-analysis - push the button [CREATE TABLE] 
        - source : `Google Cloud Storage`
        - table name : `flights_delay_jason_non_partitioned`
        - set ON `Auto detect` flag (Schema and input parameters)
        - push [CREATE_TABLE] button
        - to do the same action from CLI run bash script load_json_non_partitioned.sh
            - schema.json declare the table in Bigquery explicitly
   - Note 1: we can use analogous concept to load data in csv.files
### 2. Creating partitioned tables
   - Note 2: to play with __time partinioned__ data table - run the script load_json_partitioned.sh
### 3. Loading Data into Partitioned table
## Batch ETL - Dataproc
  - Batch processing using Pyspark on Dataproc - Project agenda
### 1. Set up Dataproc cluster
   - create dataproc cluster using script ./create_cluster.sh
### 2. Apply transformation to flight dalays data using spark-sql
   - at the begining use Jupyter/ Colabs (Google Colaboratory) and simple get part of the code in file `flights-etl.py` - copied fragments between comments eg. #In[5] to # In[6]
   - run the script `flights-etl.py`
### 3. Save the transformed Data into Bigquery partitioned tables
### 4. Use google’s workflow templates to automate the Spark ETL batch processing job
### 5. Use Apache Airflow to create DAGs and automate the batch processingj ob

# Batch data ingestion (into Bigquery/GCD ) using Appache Sqoop and DataProc
