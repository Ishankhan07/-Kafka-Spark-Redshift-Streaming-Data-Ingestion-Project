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

This PySpark script sets up a real-time streaming pipeline that reads data from Kafka, processes it with Spark, and writes the results into Redshift. It defines the data schema for Kafka messages, applies a filter to ensure data quality (e.g., positive call durations), and then uses a custom function to write processed batches to a Redshift table. It includes Docker-based deployment, Kafka configuration, Redshift JDBC connection, and S3 as a temporary storage directory for the data. The script leverages writeStream for continuous data ingestion.

## Kafka producer Script
[kafka_producer.py]()

This Python script creates a Kafka producer to send simulated telecom data to a Kafka topic. The Faker library generates random caller and receiver names, phone numbers, call durations, and other details like the network provider and total call cost. The producer continuously sends these events to the specified Kafka topic (telecom-data) at three-second intervals. The script runs in an infinite loop, which can be stopped with a keyboard interrupt.

## Redshift Connection Codes
[redshift_connect.py]()

This script establishes a connection to an Amazon Redshift cluster using the psycopg2 library in Python. The connection parameters (host, port, database name, user, and password) are defined to connect to Redshift. After connecting, the script creates a cursor to execute a simple query (SELECT version();) to retrieve and display the Redshift version. Finally, it safely closes the cursor and connection.

## Table Creation Redshift
[redshift_create_table.txt]()

This sets up a schema named telecom and a table telecom_data with appropriate data types for the telecom dataset we're working with.

## Future Upgrade

In the future, this project can be extended by exporting processed data from Redshift to popular data visualization tools such as Power BI and Tableau. This integration will enable advanced analytics and visual reporting, offering deeper insights from the real-time ingested data. By establishing direct connections from Redshift to these tools, users can create dynamic dashboards and reports, enhancing the overall utility of the pipeline for business intelligence.

