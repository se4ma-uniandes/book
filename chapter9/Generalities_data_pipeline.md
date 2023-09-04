# 9.1  Data Pipelines
___

A data pipeline could be seen as layers. And each layer is the input of the next layer. We will not deepen in the explanation of each layer, but we will mention only the most common layers that a data pipeline could have.


* **Data source:** this is the foundation of your pipeline: all your raw data live in this layer. Your data can be structured or unstructured data. This layer can be compound from multiple elements. Relational, NoSQL, plain files, etc.., For example:

  * MySQL
  * Maria db
  * Google cloud storage
  * Firebase
  * RDS
  * XML files
  * Apps
  * Werables

* **Ingestion and integration layer:** this is layer is capable of reading the data from data sources into data processing. In this layer you load the data in a targeted storage, giving it a format that the rest of your pipeline its capable of understanding.

  * REST/MQTT endpoints
  * Message queue
  * Firebase rest API
  * SFTP

* **Storage layer:** this layer is responsible for saving the data. We can have NoSQL and SQL databases. We will focus on this in the next subchapter since this is an important concept for your applications.
  * SQL databases
  * No SQL databases

* **Processing/computation layer:** this layer is used for doing aggregation, mix data sources, and pre-calculate data to use it in the next layer for visualization. This layer can be used for streaming or batch processing. *(Here is where our analytics engine reside, but needs a stable storage layer and a good presentation layer)*
  * Self hosted scripts (e.g., Python script, SQL scripts, etc..,)
  * Storm
  * Apache Spark
  * Flink
  * Machine learning models 
  * Crashlytics

* **Presentation layer:** this layer presents the insights through dashboards, emails, SMSs, push notifications, and more. Take into account that, generally, machine learning models are exposed as Micro-services.
  * Quicksight Amazon
  * Metabase
  * Apache Superset
  * Tableu
  * Looker
  * Realtime dashboard
  * Zoomdata

In the next following two chapters, we are going to go deeper into the storage layer and present to you a brief explanation of the popular types of data pipelines.