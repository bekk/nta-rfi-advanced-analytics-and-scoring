# 5. Responses to "Key topics"

The Google Cloud Platform is managed by Google, leaving domain experts to focus on domain logic only. The services are integrated and tools can perform tasks such as moving data and ETL. Custom development is required for specific domain logic implementation and low-level or complex behavior. The sections below addresses the key topics listed by the NTA.

## Analytical tools and metadata support
*The analytics platform will enable NTAs analysts/data scientists to perform a variety of analytical tasks, give insights to data and develop, maintain and evaluate risk models. Through the use of tools and integrated metadata, they should be able to perform necessary preparation and processing of data for analytical purposes without the need for IT resources ("self-service" principle).*

| **Topic** | **Response**| 
| --- | --- |
| Analytical tools and metadata support | BigQuery is a powerful Big Data analytics platform supporting SQL for queries, views and user defined functions. The BigQuery schema is user defined to handle any meta data requirements. |
| Development, testing, deployment, monitoring and evaluation of risk models | The Google Cloud platform allows any number of environments. Users can easily define, duplicate and move data between instances to according to their requirements. |
| Sharable secure data work spaces ("sandboxes") | Google Cloud Platform services like BigQuery and Cloud Storage uses Access Control Lists (ACLs) for authorization. ACLs can be used to define sharable and secure sandboxes. |
| Data access, filtering, processing and search | BigQuery supports data access, filtering and search. Processing is typically implemented using Cloud Dataflow. |
| Processing and manipulation of large datasets | All Google Cloud Platform services, like BigQuery and Cloud Dataflow, are designed to scale for billions of entities and terabytes of data. |
| Data exploration and visualization. | BigQuery SQL is used for data exploration. Additionally, several [third party tools](https://cloud.google.com/bigquery/third-party-tools) are available for integration and visualization. BigQuery can also be [connected to Excel](https://cloud.google.com/bigquery/bigquery-connector-for-excel). |
| Basic statistical methods  | The Predication API supports machine learning based on statistical methods. Use Dataproc Spark for more algorithms and additional support for customization. |
| Identification of patterns and anomalies | BigQuery can be used to understand and discover patterns and relations in the datasets. The Prediction API and Dataproc Spark can be used for automated prediction, pattern recognition and discover anomalies. |
| Text mining supporting Norwegian language | Dataproc Spark MLlib supports many data mining algorithms. BigQuery and the Prediction API also provide text mining functionality. Another option is to use BigQuery for a preflight check by quick data analysis, and Dataproc Spark/Hadoop or Cloud Dataflow to execute a production data processing or data mining. The Google Cloud Platform supports internationalization and Norwegian language by default. |
| Forecasting, simulation, optimization. | The Prediction API supports forecasting, simulation and optimization. Furthermore, Dataproc Spark MLlib can be utilized for custom algorithms and behavior. |

## Decision engine

*The decision engine will use models and rules and other supporting technologies to provide business processes with risk based decision support in real time. Lifecycle management will enable NTA to develop, test, configure, deploy and evaluate a rich set of risk models.*

| **Topic** | **Response**| 
| --- | --- |
| Combine rules, predictive/expert models, pattern and graph analysis | All Google Cloud Platform services are integrated and can be used in concert. Use Cloud Dataflow to move data, and Cloud Pub/sub to coordinate between services. |
| Risk scoring and handling strategies in real time and batch | BigQuery, Prediction API and the rest of the Google Cloud Platform is designed for elasticity and can handle both real time and batch processing. |
| Real time use cases | Use Cloud Pub/Sub to coordinate events among services. For instance, a Prediction API execution can trigger an event consumed by the Dataproc Spark GraphX library to run a graph analysis based on the prediction result. |
| Standardized development and deployment, governance, life-cycle | [Cloud Deployment Manager](https://cloud.google.com/deployment-manager/) allows developers to easily design, deploy, and reuse complex Cloud Platform solutions using simple and flexible declarative templates.  |
| Administrative tools  | Google Cloud Platform services offer administrative interfaces like [BigQuery Web UI](https://cloud.google.com/bigquery/bigquery-web-ui) and command line tools like the [BigQuery Command-Line Tool](https://cloud.google.com/bigquery/bq-command-line-tool). All services have APIs for automation and customization. Management tools include the [Deployment Manager](https://cloud.google.com/deployment-manager/), [Logging](https://cloud.google.com/logging/docs/) and [Monitoring](https://cloud.google.com/monitoring/)  |
| Process and model improvements  | No built-in support except standard logging. |

## General goals and objectives
| **Topic** | **Response**| 
| --- | --- |
| Open standards enabling integration | Google Cloud Platform services has open APIs and open source API clients. This allows for third party integration like [BigQuery third-party tools and services](https://cloud.google.com/bigquery/third-party-tools) as well as custom integration. Dataproc Spark and Hadoop are open source components with a large open source ecosystem. |
| Open standards for rules and predictive models | Predictive API supports [PMML preprocessing](https://cloud.google.com/prediction/docs/pmml-schema). Dataproc Spark MLlib is an open source platform. |
| Integrated security | The Google security model is an end-to-end process, encrypting data in-flight and at-rest. ACLs are used for authorization. There is no built-in support for anonymization. Se also the [Google Security Model](https://cloud.google.com/security/#security_measures) and the [Google Security Whitepaper](https://cloud.google.com/security/whitepaper#for_customer_administrators). |
| Scalability, performance and flexibility | The Google Cloud Platform is designed for scalability and performance, and can do real time queries, processing and scoring. |
