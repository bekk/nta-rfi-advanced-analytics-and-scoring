# 6. Proposed implementation roadmap

As the services in the Google Cloud Platform are available immediately after ordering, and integrate well, NTA has full flexibility on how to approach implementation. First the NTA has to connect and move data into the Google Cloud Platform. A high level implementation road map could be very straightforward:

* Establish a secure and reliable connection between NTA and Google Cloud Platform with [Carrier Interconnect](https://cloud.google.com/interconnect/).
* Transfer documents and data to Cloud Storage or any of the other hosted storage services.
* Define schema and move data into BigQuery using Cloud Dataflow to start experimenting, learning and evolving the solution.
 * Experiment with streaming to enable real time analysis.
 * Choose a strategy to handle schema versioning and maintenance.
 * De-normalize data when necessary to increase performance.
 * Use BigQuery to establish training data for the Prediction API.
* Establish hypothesis and models for the Prediction API
 * Experiment with prediction, risk assessment, fraud detection and other models as required.
 * Use BigQuery to provide establish models and training data.
* Establish Spark MLLib and GraphX to handle custom requirements.

An essential benefit of using the Google Cloud Platform is the ability to experiment and evolve the solution as requirements are understood, clarified, added and removed. There is virtually no cost of trying a new service or approach, and if it fails the NTA can change direction and try an alternative approach. You only pay for actual usage of the services, and once you stop you also stop paying.