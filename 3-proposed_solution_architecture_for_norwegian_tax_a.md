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