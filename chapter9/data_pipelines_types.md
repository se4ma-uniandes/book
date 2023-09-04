# 9.3 Types of data Pipelines
___

In the same way we have types of candy factories, we also have different types of data pipelines. In this book we are only going to mention the most popular ones:

- **Batch:**  refers to those pipelines that process in batch, meaning that they do not process in real-time, they usually work in defined intervals. These intervals can be every night, every week, etc..,. Specific usage examples:

    - Strategic business intelligence
	- ETL
	- Descriptive and predictive analytics

- **Real-time/stream:**  this type of pipeline is optimized for real-time data processing. For example, to process streams of information, like traffic or application telemetry. Specific usage examples:
    - Operative business intelligence
	- Operative analytics
	- IOT

- **Cloud native:**  refers to those pipelines that are optimized to process cloud-based data, they are integrated with cloud solutions. This type of pipelines are attached to the cloud provider since it uses specific tools and resources form the provider.

Please, note that these types are not mutually exclusive, you can have a pipeline that is optimized for batch processing as well as cloud. For example, one common Big data architecture that uses batch and stream processing is lambda architecture.


 > Which type of data pipeline use?, it depends on the needs that your system has.

If you want to get more and detailed information you can visit these links:

- [Cloud-native using kafka](https://www.infoq.com/presentations/cloud-native-data-pipeline-kafka/)

- [Batch vs stream processing](https://medium.com/simpl-under-the-hood/data-pipeline-batch-vs-stream-processing-d038bdb29e18)
