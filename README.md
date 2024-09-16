# -Kafka-Spark-Redshift-Streaming-Data-Ingestion-Project

### Project Overview

This project demonstrates a real-time data pipeline using Kafka for message queuing, Spark for stream processing, and AWS Redshift for data storage. Docker is used to containerize the components, ensuring smooth orchestration and environment consistency. The pipeline ingests data through a Kafka producer, processes it using Spark Streaming, and stores the results in Redshift. Docker Compose simplifies the deployment of Kafka, Spark, and other dependencies.


### To execute the data Ingestion Project, Follow these steps:

1. #### Set up Kafka and Zookeeper Use Docker to deploy a Kafka broker and Zookeeper for message queuing and coordination.
2. #### Create Kafka producer write a script to push data to Kafka topics.
3. #### Deploy Spark Streaming create a Spark application to consume data from Kafka topics, process it, and prepare it for Redshift ingestion.
4. #### Configure Redshift set up AWS Redshift, create tables, and configure JDBC/ODBC connectors for Spark to interact with Redshift.
5. #### Run Docker Compose use Docker Compose to orchestrate services like Kafka, Spark, and Redshift in containers.
6. #### Execute Pipeline start Kafka producer, Spark job, and observe processed data being written to Redshift.




## Architecture

![Project Architecture](Architecture-diagram.jfif)

## Tech Stack
1. Python
2. Amazon Web Services
      - Redshift
      - Aws Glue
3. Apache Spark
      - Spark Streaming
4. Kafka
5. Docker  


## Script for Project
[spark_redshift_stream.py]()

## Kafka producer Script
[kafka_producer.py]()

## Redshift Connection Codes
[redshift_connect.py]()

## Table Creation Redshift
[redshift_create_table.txt]()

## Future Upgrade
### In the future, this project can be extended by exporting processed data from Redshift to popular data visualization tools such as Power BI and Tableau. This integration will enable advanced analytics and visual reporting, offering deeper insights from the real-time ingested data. By establishing direct connections from Redshift to these tools, users can create dynamic dashboards and reports, enhancing the overall utility of the pipeline for business intelligence.

