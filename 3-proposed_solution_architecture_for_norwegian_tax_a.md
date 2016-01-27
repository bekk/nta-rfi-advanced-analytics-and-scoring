# Proposed solution architecture for Norwegian Tax Administration

The solution architecture is based on the [Google Cloud Platform](https://cloud.google.com/) (GCP). GCP is a set of modular cloud-based services built on Google infrastructure, outlined below.

![Google Cloud Platform Services](GoogleCloudPlatform.png)

The benefits of using a cloud platform are many:
* **Managed services**: Infrastructure and operations are managed by Google.
* **Pay as you go**: No need for a huge investment up front.
* **Pay for what you use**: Pay for actual usage instead of guessing capacity demand before procurement.
* **Experimentation**: Start small, test hypotheses and technology. Scale fast when solutions are verified.
* **Elasticity**: Scale up and down on demand in development and production.
* **Future-proof**: The cloud is becoming the industry standard. The life cycle of the NTA advanced analytics and risk platform is probably 5-10 years.
* **Reduced risk**: The benefits listed above adds up to a significantly lower risk compared to an on-premises alternative.

TODO: Data in the cloud

## BigQuery for analytics
[BigQuery](https://cloud.google.com/bigquery/) is a fully managed, large scale analytics database. Using the processing power of Google's infrastructure, terabytes of data and billions of entries can be queried in seconds.

BigQuery loads data into tables with a schema describing field names and types. Data is queried using the [BigQuery SQL Dialect](https://cloud.google.com/bigquery/query-reference), supporting joins, aggregation, regular expressions, geospoatial queries and more. Views can also be defined, and data can be federated from [Google Cloud Storage](https://cloud.google.com/storage/).

You can access BigQuery by using a [web UI](https://bigquery.cloud.google.com/) or a [command-line tool](https://cloud.google.com/bigquery/docs/cli_tool), or by making calls to the [BigQuery REST API](https://cloud.google.com/bigquery/docs/reference/v2) using a variety of client libraries such as [Java](https://developers.google.com/api-client-library/java/apis/bigquery/v2), [.NET](https://developers.google.com/api-client-library/dotnet/get_started) or [Python](https://developers.google.com/api-client-library/python/). There are also a variety of [third-party tools](https://cloud.google.com/bigquery/third-party-tools) that you can use to interact with BigQuery, such as visualizing the data or loading the data, for instance:
* Simba provides a [BigQuery ODBC driver](http://www.simba.com/drivers/bigquery-odbc-jdbc/) that enables SQL access to BigQuery.
* [Tableau has a native, optimized connector to Google BigQuery](http://www.tableau.com/solutions/google-bigquery) that supports both live data and in-memory BI analytics.

TODO: Security and privacy

## Prediction API for prediction models and scoring
The [Prediction API](https://cloud.google.com/prediction/) is a decision engine, using machine learning algorithms to analyze data and predict future outcomes. Use cases include fraud detection and suspicious activity identification. Most prediction queries take less than 200ms, and can be used in real time processing.

The Google Prediction API supports [preprocessing your data against a PMML transform](https://cloud.google.com/prediction/docs/pmml-schema) specified using PMML 4.0 syntax. Regression and categorical models are supported:
* Regression model: Given a new item, predict a numeric value - a *score* - for that item, based on similar valued examples in its training data.
* Categorical model: Given a new item, choose a category that describes it best, given a set of similar categorized items in its training data.

[A RESTful API](https://cloud.google.com/prediction/docs/reference/v1.6/) is available through libraries for many popular languages, such as [Python, JavaScript and Java](https://cloud.google.com/prediction/docs/libraries#generic). Results from Google BigQuery can be used directly or datasets can be pulled from  Cloud Storage to create a predictive model.

## Cloud Dataproc for managed Hadoop and Spark
[Google Cloud Dataproc](https://cloud.google.com/dataproc/) is a managed Hadoop MapReduce, Spark, Pig, and Hive service, to process big datasets at low cost. It provides built-in integration with BigQuery, Cloud Storage, Bigtable, Cloud Logging, and Cloud Monitoring. Cluster Management is automated, handling managed deployment, logging, and monitoring. Clusters can be created and scaled quickly with a variety of virtual machine types, disk sizes, number of nodes, and networking options. 

The [Apache Hadoop](https://hadoop.apache.org/) software library is a framework that allows for the distributed processing of large data sets across clusters of computers using simple programming models. It is designed to scale up from single servers to thousands of machines, each offering local computation and storage. Rather than rely on hardware to deliver high-availability, the library itself is designed to detect and handle failures at the application layer, so delivering a highly-available service on top of a cluster of computers, each of which may be prone to failures. Hadoop implements the MapReduce pattern, pioneered by Google for large scale, distributed batch processing. Hadoop on Google Cloud Dataproc supports:
* The [Apache Hive](http://hive.apache.org/) data warehouse software facilitates querying and managing large datasets residing in distributed storage. Hive provides a mechanism to project structure onto this data and query the data using a SQL-like language called HiveQL.
* The [Apache Pig](http://pig.apache.org/) platform for analyzing large data sets. Pig consists of a high-level language for expressing data analysis programs, coupled with infrastructure for evaluating these programs in parallell.

[Apache Spark](http://spark.apache.org/) is a fast and general engine for large-scale data processing, and is compatible with Hadoop data. It can run in Hadoop clusters through YARN or Spark's standalone mode, and it can process data in HDFS, HBase, Cassandra, Hive, and any Hadoop InputFormat. The Spark platform provides the following libraries which can be combined seamlessly:
* [Spark SQL](http://spark.apache.org/sql/) lets you query structured data inside Spark programs
* [Spark Streaming](http://spark.apache.org/streaming/) to build scalable fault-tolerant streaming applications.
* [MLlib](http://spark.apache.org/mllib/) for scalable machine learning, supporting logistic regression, classification and regression tree, hypothesis testing and several more.
* [GraphX](http://spark.apache.org/graphx/) for graphs and graph-parallel computation. 

We recommend that NTA starts experimenting with BigQuery and the Prediction API. Use the Spark MLLib library if more specific algorithms and methods are required.

## TODO ETL