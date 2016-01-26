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
* Simba provides a BigQuery ODBC driver that enables SQL access to BigQuery. 