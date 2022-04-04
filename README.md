# ANNUAL INCOME FOR NEWZEALAND
A data engineering Project 

At this project, i've tried to download a CSV file from the website of the newzealand gouvernemant to create a dashboard that resume the income of this country from 2013 to 2020.

we’re going to design a pipeline based on GCP (Google Cloud Platform) with the use of :
  -	Data studio for visualization 
  -	Airflow for Pipeline Orchestration
  -	BigQuery as a Warehouse
  -	Dbt : For tranforming data 

![DATA](https://user-images.githubusercontent.com/56431306/161545836-a9bc2bfc-c1e2-430f-8b58-97f7fd7cf668.jpg)

In this deposit you're going to find the data ingestion script in the folder airflow/dags + a docker-compose.yaml and a docker file in order to install airlow.
I've put some comments on the code
the results of airflow :

![Capture](https://user-images.githubusercontent.com/56431306/161546673-316d2f87-4cd2-4251-8266-7cedcec66718.PNG)
4 dags :
 - Download the data set (choose your dataset)
 - Format to park in order to change the type of document from csv to parquet size
 - local to gcs in order to put data in a DATA LAKE
 -  Bigquery in order to create the table in the DATA WAREHOUSE


After doing all that, we're going to use dbt tool (cloud version) in order to transform our data (raw data to transformed)
i've created a table named total income 
![image](https://user-images.githubusercontent.com/56431306/161547771-5a91f18c-56eb-47dc-9a6c-94a65e2fddfa.png)

look at the code :
Schema.yml : Define our source code
mytransformation.sql : my first transfomation 
Total_income.sql : my second one with where statement in order to get only the income


