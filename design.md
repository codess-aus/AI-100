# Design AI solutions (40-45%)

[1. Design solutions that include one or more pipelines](#1-Design-solutions-that-include-one-or-more-pipelines)
* define an AI application workflow process
* design a strategy for ingest and egress data
* design the integration point between multiple workflows and pipelines
* design pipelines that use AI apps
* design pipelines that call Azure Machine Learning models
* select an AI solution that meet cost constraints

[2. Design solutions that use Cognitive Services](#2-Design-solutions-that-use-Cognitive-Services)
* design solutions that use vision, speech, language, knowledge, search, and anomaly detection APIs

[3. Design solutions that implement the Microsoft Bot Framework](#3-Design-solutions-that-implement-the-Microsoft-Bot-Framework)
* integrate bots and AI solutions
* design bot services that use Language Understanding (LUIS)
* design bots that integrate with channels
* integrate bots with Azure app services and Azure Application Insights

[4. Design the compute infrastructure to support a solution](#4-Design-the-compute-infrastructure-to-support-a-solution)
* identify whether to create a GPU, FPGA, or CPU-based solution
* identify whether to use a cloud-based, on-premises, or hybrid compute infrastructure
* select a compute solution that meets cost constraints

[5. Design for data governance, compliance, integrity, and security](#5-Design-for-data-governance-compliance-integrity-and-security)
* define how users and applications will authenticate to AI services
* design a content moderation strategy for data usage within an AI solution
* ensure that data adheres to compliance requirements defined by your organization
* ensure appropriate governance of data
* design strategies to ensure that the solution meets data privacy regulations and industry standards

## 1. Design solutions that include one or more pipelines
Example: You need to choose a solution for ingesting the sensor data from the wells. 
Which two solutions should you recommend?

You should use Event Hub or IOT Hub to ingest the sensor and camera data. Both of these technologies are 
big data streaming ingesting services. Additionally, IOT Hub supports bi-directional communication, per- 
device provisioning, and device identification. 

You should not use Data Lake. Data Lake is an enterprise-scale hyper repository that supports data of any 
type and size. It does not support ingestion of streaming data. 

You should not use Blob Container. Azure blob storage allows you to store text and binary files. It does not 
support ingestion of streaming data. 

Example: A solution that allows the CEO to visualise the data.

You should use Power Bl. This is a collection of apps, services, and connectors that turn data into visual 
insights. It can automatically generate charts and graphs. 

You should not use Databricks. This is an Apache Spark-based analytics platform that allows you to create 
workflows. You can use it to generate charts, but it requires knowledge of a programming language to query 
the data. The CEO does not know any programming languages. 

You should not use IOT Hub. This is a big data streaming ingestion service. It supports bi-directional 
communication, per-device provisioning, and device identification. 
You should not use Data Lake. Data Lake is an enterprise-scale hyper repository that supports data of any 
type and size. 

You should not use Log Analytics. This allows you to write queries to monitor application logs. 

Example: You need to choose a solution that stores the sensor data after it is ingested and analyzed. 
Which three outputs should you recommend? 

You should use SQL Database, Table storage, or Cosmos DB. All three are supported as output to Stream 
Analytics, which is what you should use to query and process the input data as soon as it arrives in the 
cloud. In addition to these three, Stream Analytics also supports, Event Hub, Blob storage, Service Bus, 
Function, Data Lake, and Power Bl as outputs. 

You should not use Databricks or Data Factory. Neither of these are supported as Stream Analytics output. 
Data Factory allows you to create big data pipelines to copy data between sources and destinations. 

## 2. Design solutions that use Cognitive Services

## 3. Design solutions that implement the Microsoft Bot Framework

Example: You are designing a bot that uses Azure Bot Service and Azure Bot Framework. The bot will be integrated into your company's website. The bot must allow users to enter freeform feedback regarding their like or dislike of a product. The bot must then interpret the user's feedback. If the feedback is negative, the bot 
must display one set of options. If the feedback is positive, the bot must display a different set of options. 

Cognitive Services Text Analytics can extract key phrases from text and determine positive or negative sentiment, returning a sentiment result between O and 1, with O being negative and 1 being positive.You can use the returned values to determine the next options to provide to the user.

Cognitive Services Personalizer allows you to present the best experience to users by using machine learning models that analyze real-time behavior. It will choose which video to play next, like YouTube, based on what you play and what you skip.

LUIS allows applications to understand what a user wants when it is expressed in his or her own words. It uses custom machine learning intelligence to predict natural language meaning and return relevant information. 


## 4. Design the compute infrastructure to support a solution

## 5. Design for data governance, compliance, integrity, and security

