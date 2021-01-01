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

Example: You are designing an Azure Data Factory pipeline that must perform the following tasks: 

1 . Copy images from on-premises file servers to blob storage accounts.
2. Run several Cognitive Services APIs in a workflow.

You need to choose the Data Factory integration runtime type for the first task and the Azure resource to use for the second task. Your solution must not require you to create an Azure virtual network (VNet).

Self-hosted IR. This is required when you need to copy data from on-premises file servers to Azure.

You should use a Logic App to run several Cognitive Services APIs in a workflow. A Logic App allows you to create workflows graphically. 

You should not use the Azure IR. This IR allows you to copy data between data sources in Azure. It does not support on-premises files. 

You should not use the Azure SSIS IR. This IR allows you to use SSIS packages to copy data between data sources in Azure. It does not support on-premises files unless you connect an Azure VNet to an on-
premises network.

You should not use a WebJob to run several Cognitive Services APIs in a workflow. A WebJob is code that runs in the context of an Azure web application. It can be run on a schedule or via a trigger. It does not allow you to create graphical workflows.

You should not use Databricks to run several Cognitive Services APIs in a workflow. Databricks is a Sparks-based analytics platform that allows you to read data from a variety of sources and write code to transform and analyze the data. It does not allow you to create graphical workflows.

## 2. Design solutions that use Cognitive Services

Example: You are designing a solution that must determine whether images contain racy content. You create a Cognitive Services endpoint named sample. You have the following URL: 
https://eastus.api.cognitive.microsoft.com/[placeholder l]/[placeholder 2]/v1.O/Processlmage/[placeholder 3]

You need to replace the [placeholders] in the URL with the correct values for returning information about racy content. How should you construct the URL?

You should use the following URL: 
https://eastus.api.cognitive.microsoft.com/contentmoderator/moderate/v1.O/Processlmage/evaluate 

The first placeholder represents the name of the Cognitive Services service. In this case, you should use the Content Moderator service (contentmoderator), which allows you to detect racy or adult content in images and text. 

The second placeholder represents the name of the specific API. The image moderation API (moderate/v1.O/Processlmage) allows you to detect racy content in images. 

The final placeholder represents the specific operation to invoke in the API. The Evaluate operation (evaluate) analyzes the image for racy content and returns an appropriate response.

Alt: 
You could specify vision as the value of the first placeholder. This represents the Computer Vision service. You must then use the Analyze API (analyze), as the 2nd placeholder.

You design an Al workflow that uses Azure Stream Analytics to detect fraudulent activity of financial transactions. 
You need to recommend an appropriate input for the data stream. 

Event Hub: Stream Analytics supports a number of sources for input data, including Event Hub, IOT Hub, and blob storage.

You should not use Data Lake, SQL Database, or Cosmos DB as an input source. None of these resources are supported as Stream Analytics stream input sources. SQL Database is supported as a reference data source. All three are supported as output sources.

### Cognitive Services Custom Vision
After training has completed, the model's performance is estimated and displayed. The Custom Vision Service uses the images that you submitted for training to calculate precision and recall, using a process called k-fold cross validation. Precision and recall are two different measurements of the effectiveness of a classifier:

<p><img align="center" src="https://github.com/msandfor/AI-100/blob/main/assets/unpublished-iteration.png" alt="image classifier"></p>
<p align="center"></p>

Precision indicates the fraction of identified classifications that were correct. For example, if the model identified 100 images as dogs, and 99 of them were actually of dogs, then the precision would be 99%.

Recall indicates the fraction of actual classifications that were correctly identified. For example, if there were actually 100 images of apples, and the model identified 80 as apples, the recall would be 80%.

## 3. Design solutions that implement the Microsoft Bot Framework

Example: You are designing a bot that uses Azure Bot Service and Azure Bot Framework. The bot will be integrated into your company's website. The bot must allow users to enter freeform feedback regarding their like or dislike of a product. The bot must then interpret the user's feedback. If the feedback is negative, the bot 
must display one set of options. If the feedback is positive, the bot must display a different set of options. 

Cognitive Services Text Analytics can extract key phrases from text and determine positive or negative sentiment, returning a sentiment result between O and 1, with O being negative and 1 being positive.You can use the returned values to determine the next options to provide to the user.

Cognitive Services Personalizer allows you to present the best experience to users by using machine learning models that analyze real-time behavior. It will choose which video to play next, like YouTube, based on what you play and what you skip.

LUIS allows applications to understand what a user wants when it is expressed in his or her own words. It uses custom machine learning intelligence to predict natural language meaning and return relevant information. 

For LUIS You should create one intent and many utterancess. A LUIS intent specifies a function the user wants to perform. It is a way of organizing text entered by the user in the bot application. Each utterance represents a different way the user can perform the same 
function. 

You should not create many intents. An intent should specify a single function. Therefore, you should only have one intent, and add each question as an utterance. 

You should not create only one utterance. An utterance represents a different way the user can perform the same function. Therefore you should create many utterances per intent. 

Regex entity: This represents an entity that uses a regular expression. A regular expression allows you to mark the part of text that represents, for example, the flight number. This allows the runtime prediction service to capture it from the rest of the text.

A List entity: This requires that you list all the possible flight numbers during design-time. Where flight numbers vary, and there are over 50,000 flight numbers per day this becomes an impossible task. 

Composite entity: This requires that you create child entities. This is useful for an entity that has multiple parts.

Simple entity. This entity type cannot identify flight numbers.

## 4. Design the compute infrastructure to support a solution

## 5. Design for data governance, compliance, integrity, and security

