# Analyze solution requirements (25-30%)

## Recommend Azure Cognitive Services APIs to meet business requirements
* [1. select the processing architecture for a solution](#1-select-the-processing-architecture-for-a-solution)
* [2. select the appropriate data processing technologies](#2-select-the-appropriate-data-processing-technologies)
* [3. select the appropriate AI models and services](#3-select-the-appropriate-AI-models-and-services)
* [4. identify components and technologies required to connect service endpoints](#4-identify-components-and-technologies-required-to-connect-service-endpoints)
* [5. identify automation requirements](#5-identify-automation-requirements)

## Map security requirements to tools, technologies, and processes
* [6. identify processes and regulations needed to conform with data privacy, protection and regulatory requirements](#6-identify-processes-and-regulations-needed-to-conform-with-data-privacy-protection-and-regulatory-requirements)
* [7. identify which users and groups have access to information and interfaces](#7-identify-which-users-and-groups-have-access-to-information-and-interfaces)
* [8. identify appropriate tools for a solution](#8-identify-appropriate-tools-for-a-solution)
* [9. identify auditing requirements](#9-identify-auditing-requirements)

## Select the software, services, and storage required to support a solution
* [10. identify appropriate services and tools for a solution](#10-identify-appropriate-services-and-tools-for-a-solution)
* [11. identify integration points with other Microsoft services](#11-identify-integration-points-with-other-Microsoft-services)
* [12. identify storage required to store logging, bot state data, and Azure Cognitive Services output](#12-identify-storage-required-to-store-logging-bot-state-data-and-Azure-Cognitive-Services-output)


### 1. select the processing architecture for a solution

HDInsight. Cloud-based service of Hadoop clusters that allows you to process big data workloads in parallel. Supports Scala, Python, R, Java and .Net

### 2. select the appropriate data processing technologies

You can use Computer Vision to determine if the image is a car and to determine if competitors are using your company's logo. Computer Vision can detect objects, faces and brands. It is not specific enough to detect distinct facial features though, you'd need the Face API for that.

Bing Visual Search when you want to upload a picture of a vehicle starter to determine where it can be purchased. The API returns insights about an image, such as lists of similar images or where products within the image can be purchased.

Bing Image Search returns a list of images based on a text query (just like when you search the internet for images)

Bing Video Search returns a list of videos based on a text query.

Video Indexer when you want to determine whether a video contains a certain actress. It returns insights about an image such as whether it contains an actor or an actress from a public list, such as the public internet movie database. Automatically identifies over 1M celebrities. Allows you to extract insights from a video to determine if someone famous is in it.

Personalizer will choose next video to play based on what a user is currently watching and what they skip. This API allows you to displat a user experience based on the users real-time behaviour.

Face API allows you to detect specific features on a persons face, and if that person belongs to a group of similar faces.

Content Moderator allows you to create a list of explicit terms to be matched against user-generated content. The API returns a response specifying any banned terms that appear in the content.

Cognitive Services Text Analytics can extract key phrases from text and determine positive or negative sentiment, returning a sentiment result between O and 1, with O being negative and 1 being positive.You can use the returned values to determine the next options to provide to the user.

### 3. select the appropriate AI models and services

A ML experiment allows you to add source data as input to data science models. A model performs actions on data, such as removing empty rows or columns. The Train, Score and Evaluate Models together allow you to use historical data to predict trends. A regression algorithm is used to predict a number. 

You can use the Score Model to compare predicted presults with actual results.

A classification model will give binary answers - Yes or No. Or it will classify stuff - it's a Lily, or it's a Rose.

Azure Bot Service allows you to build intelligent bots, which are computer programs that automatically respond to user inputs. Bots use dialogs to respond to users without human intervention.

Machine Learning Service is a data science solution that allows you to train, manage, automate and deploy machine learning models.

### 4. identify components and technologies required to connect service endpoints

IoT Hub is a big data stream ingestion service. It can process large amounts of data in parallel. It supports per-device provisioning and bi-directional communication. It supports MQTT, AMQP and Https.

Stream Analytics is a real-time analytics and event processing solution that ingests data from multiple sources simulataneously. However the sources *must be Azure Resources*. They cannot be Apps on a Device. It can ingest from Azure Event Hub and Azure IOT Hub and blob storage.

Azure SQL DB, Azure Table Storage and Azure Cosmos DB are supported as outputs to stream analytics.

You should use SQL Database, Table storage, or Cosmos DB. All three are supported as output to Stream Analytics, which is what you should use to query and process the input data as soon as it arrives in the cloud. In addition to these three, Stream Analytics also supports, Event Hub, Blob storage, Service Bus, Function, Data Lake, and Power Bl as outputs. 

You should not use Databricks or Data Factory. Neither of these are supported as Stream Analytics output.
Data Factory allows you to create big data pipelines to copy data between sources and destinations.

Service Bus is a cloud-based messaging broker. 

Service Fabric is a cloud-based distribution platform that allows you to run workloads in parallel across thousands of VMs.

Event Hub is a big data ingestion and streaming platform.

### 5. identify automation requirements


### 6. identify processes and regulations needed to conform with data privacy, protection and regulatory requirements

SOC
HIPAA
PCI DSS


### 7. identify which users and groups have access to information and interfaces

Cognitive Services User can list and read keys.

Cognitive Services Contributor can create and manage keys.

Security Reader is for ASC, no effect of CS.

Security Admin - no effect on CS.

Shared Access Signature. A SAS is a URL with a token that specifies the allowed permissions. Example: You are developing a solution that allows developers to create ML experiments. The data for the solution will be stored in an Azure Table. You need to ensure developers can read from the table but not modify or delete it.

A shared access signature (SAS) provides secure delegated access to resources in your storage account. With a SAS, you have granular control over how a client can access your data. For example:

* What resources the client may access.
* What permissions they have to those resources.
* How long the SAS is valid.

Configure encryption with customer-managed keys stored in Azure Key Vault Managed HSM:
* Assign an identity to the storage account
* Assign a role to the storage account for access to the managed HSM
* Configure encryption with a key in the managed HSM

An Access Key provides Admin Access to an Azure Storage Account.

RBAC will not provide fine-grained access to Azure Tables.

Storage Blob Reader Role is a built-in tole that allows accounts to read and list storage containers and blobs.

Owner role can manage everything.

User Access Admin role - grant or deny access to other users for Azure resources. 


### 8. identify appropriate tools for a solution

Azure Key Vault allows you to securely store secrets, which can be passwords or API keys.

### 9. identify auditing requirements


### 10. identify appropriate services and tools for a solution

### 11. identify integration points with other Microsoft services

### 12. identify storage required to store logging, bot state data, and Azure Cognitive Services output

CosmosDB and Table API allow you to store data as key-attribute pairs. Each row in the table can have a different number of columns.

CosmosDB with the Gremlin API is useful for Graph based data.

Data Lake allows you to temporarily store data of any size and type. This is a storage solution for big solution workloads. It supports data of any size and type. It does not store structured data. It is an Apache Hadoop file system that allows you to ingest and store data in it's native format.

**Databricks** is a **Spark** based analytics solution that allows you to process data in **batches** or **real-time streams**. Allows you to create Big Data Pipelines. Runs on Spark Clusters not Hadoop Clusters. Not supported as Stream Analytics Output.

Azure Log Analytics allows you to write queries to monitor application usage.

Azure Table Storage. This allows you to store structured data as key-attribute pairs. Each entity (row) can have a varying number of attributes (columns). This solution provides a NoSQL data store for structured data. It is not designed to process data in a particular order.

Azure Queue Storage allows you to store and retrieve messages. It does not store structured data. It is a reliable message store for processing messages in sequence asynchronously. Example - you are designing a solution that will process and analyze data asynchronously. The data must be processed in the order in which it is received.

Azure Blob Storage allows you to store files. It does not store structured data. A Scalable data store for text and binary data. Azure blob storage allows you to store text and binary files. It does not support ingestion of streaming data.

