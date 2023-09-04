# 4.1 Data architecture is the foundation of analytics
___

The context canvas is one of tools we have for designing a software solution that involves mobile devices and applications.  But have in mind that one of the design constraints in the course is to include (in your solution) a back-end analytics/machine-learning engine. While the context canvas focuses on the app and the devices, it does not cover the design of the domain model and analytics engine. There are several methods and processes that have been proposed to design analytics and data science projects such as  [CRISP-DM,](https://data.sngular.team/en/art/40/crisp-dm-the-methodology-to-put-some-order-into-data-science-projects) [guerilla analytics](http://guerrilla-analytics.net/the-principles/), and the [Team Data Science Process Lifecycle](https://docs.microsoft.com/en-us/azure/machine-learning/data-science-process-overview); however, before defining a process to follow, we need to design the data architecture that will support the analytics engine.

 > "Data architecture is composed of models, policies, rules or standards that govern which data is collected, and how it is stored, arranged, integrated, and put to use in data systems and in organizations"[^1]   [^2]


In our context, the analytics engine is a back-end service that will provide personas with insights, patterns, knowledge, and information extracted from the data collected within the whole system. Therefore, the mobile devices and the apps running on them become a "data collection system" from the point of view of the analytics engine. While the app has their own purpose and it is to provide  features to a set of personas, the analytics engine takes advantage of all the data collected through the app usages and also provides features to another set of personas interested on the information and knowledge derived from the raw data. In conclusion, designing the analytics engine requires to design the data architecture that integrates (i) the data collected with the device/app, (ii) data that can be extracted from any other source (e.g., a government open data service, a private web service), and (iii) the knowledge/information expected to be extracted from the data.

<br>
<br>
[^1] John Parkinson. What is Data Architecture? Linkedin, Mark 3rd, 2017. https://www.linkedin.com/pulse/what-data-architecture-john-parkinson
[^2] Wikipedia. Data Architecture. August 28th, 2017. https://en.wikipedia.org/wiki/Data_architecture
