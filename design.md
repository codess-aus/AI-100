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

Cognitive Services supports single-key authentication for multiple APIs including Computer Vision, Language, Search and Speech. You'd need a separate authentication key for each of Anomaly Detector, Content Moderator, Personalizer and Custom Vision. All the Vision API's except Custom support a single authentication key.

Allow a client app to make calls to the API for CS Translator Text:
Pass a subscription key as the value of the Ocp-Apim-Subscription-Key HTTP header with each API request. This is how Cognitive Services authenticates client requests. When you create a Cognitive Services resource, two subscription keys are generated. You can regenerate each of these keys as you see fit. 

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

Regex entity: This represents an entity that uses a regular expression. A regular expression allows you to mark the part of text that represents, for example, the flight number. This allows the runtime prediction service to capture it from the rest of the text. This entity type is useful for values that can be determined by regular expressions, such as tax ID numbers, ISBN numbers, and IP 
addresses. Example 'flightnumber" is defined as flight[A-Z]{2} {0-9}{4}

A regular expression entity extracts an entity based on a regular expression pattern you provide. A regular expression is best for raw utterance text. It ignores case and ignores cultural variant. Regular expression matching is applied after spell-check alterations at the character level, not the token level. If the regular expression is too complex, such as using many brackets, you're not able to add the expression to the model. Uses part but not all of the .NET Regex library.

The entity is a good fit when:

* The data are consistently formatted with any variation that is also consistent.
* The regular expression does not need more than 2 levels of nesting.

Example: Find KB-reference

A List entity: This requires that you list all the possible flight numbers during design-time. Where flight numbers vary, and there are over 50,000 flight numbers per day this becomes an impossible task. This entity type is useful for known values. For example, known values where there are the 15 department names.  This type is useful when an utterance can contain words from a pre-defined list. List entities represent a fixed, closed set of related words. While you, as the author, can change the list, LUIS won't grow or shrink the list. You can also import to an existing list entity using a list entity .json format.

A list entity isn't machine-learned. It is an exact text match. LUIS marks any match to an item in any list as an entity in the response.

The entity is a good fit when the text data:

* Are a known set.
* Doesn't change often. If you need to change the list often or want the list to self-expand, a simple entity boosted with a phrase list is a better choice.
* The set doesn't exceed the maximum LUIS boundaries for this entity type.
* The text in the utterance is a case-insensitive match with a synonym or the canonical name. LUIS doesn't use the list beyond the match. Fuzzy matching, stemming, plurals, and other variations are not resolved with a list entity. To manage variations, consider using a pattern with the optional text syntax.

Composite (ML) entity: This requires that you create child entities. This is useful for an entity that has multiple parts. This is useful for an entity that has multiple parts. A composite entity is made up of other entities, such as prebuilt entities, simple, regular expression, and list entities. The separate entities form a whole entity. This entity is deprecated. Please migrate to the machine-learning entity. The machine-learning entity is the preferred entity for building LUIS applications. Suppose the app takes pizza orders, such as the decomposable entity tutorial. Each order can include several different pizzas, including different sizes.

Example utterances include:

EXAMPLE JSON
Example utterances for pizza app
Can I get a pepperoni pizza and a can of coke please
can I get a small pizza with onions peppers and olives
pickup an extra large meat lovers pizza

Or, Book {2} {Business-Class} tickets to {Perth}


Simple entity. This entity type cannot identify flight numbers. This entity type cannot identify department names. This type is useful for capturing a specific word in an utterance, for example "Job". A simple entity is a generic entity that describes a single concept and is learned from the machine-learning context. Because simple entities are generally names such as company names, product names, or other categories of names, add a phrase list when using a simple entity to boost the signal of the names used.

The entity is a good fit when:

The data aren't consistently formatted but indicate the same thing.

Book me a Flight to Perth on Qantas.
Book me a Flight to Perth on an airline

Prebuilt entity. This type exists for pre-defined entities, such as 
addresses, phone numbers, and e-mails.

### Design a Bot
Design a bot that uses Azure Bot Service and Azure Bot Framework. The development team is creating a client desktop application that allows users to use the bot for communication. Configure the bot so that it can use the client application as a channel:

1. Create a Direct Line channel. A channel is a way for users to interact with a bot. A bot is simply an API endpoint that has automation code. 
2. Create a site. A default site is automatically created. Each site that you create has a different set of API keys. 
3. Copy and store the secret API key to be used by the client application. Add this key to Azure Key Vault so that it can remain secure. 

* A Web App channel: This channel is automatically created when you create a bot. It is used for embedding HTML code within a web site. In this scenario, you are creating a desktop application. 
* A VNet: A VNet allows you to create a private network in Azure. You do not need a private network to deploy bots with Azure Bot Service and Azure Bot Framework.These bots are public. They are secured by secret API keys.
* Cognitive Services resource: Cognitive Services SDKs, APIs, and 
services help you perform Al without having to know data science skills. This is not necessary for allowing a client application to communicate with your bot. However, services such as Language Understanding (LUIS) can be integrated into bot code to help interpret user conversations. 
* QnA Maker. This service allows you to build a question and answer set by using a published knowledge base. You can integrate QnA Maker with your bot. 
* LUIS. This service helps a bot understand what a person is saying in their own words by using a combination of utterances, intents, and entities. An utterance is a phrase or sentence used by a user. An intent is a collection of utterances to indicate a function that the user is trying to perform. An entity is a known extracted word or phrase from an utterance. 
* Text Analytics: This service identifies key phrases and the language of text.
* *Translator Text: This service translates text from one language to another. 


## 4. Design the compute infrastructure to support a solution

<p><img align="center" src="https://github.com/msandfor/AI-100/blob/main/assets/azure-machine-learning-fpga-comparison.png"alt="Community photo"></p>
<p align="center"></p>

* N series: VMs in this series are GPU-enabled. They are ideal for
graphics intensive workloads, simulation, and deep learning.
* A series: This is an entry level VM for development and test
servers, low-traffic web servers, and small-to-medium databases. It is not ideal for deep learning models.
* D series: This is a general-purpose VM for enterprise applications 
and databases. It is not ideal for deep learning models.
* F series: This is a compute-optimized VM with a higher compute-
to-memory ratio. It is ideal for batch processing and gaming, but not for deep learning models.
* FPGA: This VM provides fast performance, and it is flexible and
configurable as your needs change over time. It is great for parallel machine learning training. It is faster than GPU. Supoorts AKS but not ACI

FPGAs contain an array of programmable logic blocks, and a hierarchy of reconfigurable interconnects. The interconnects allow these blocks to be configured in various ways after manufacturing. Compared to other chips, FPGAs provide a combination of programmability and performance.

FPGAs make it possible to achieve low latency for real-time inference (or model scoring) requests. Asynchronous requests (batching) aren't needed. Batching can cause latency, because more data needs to be processed. Implementations of neural processing units don't require batching; therefore the latency can be many times lower, compared to CPU and GPU processors.

You can reconfigure FPGAs for different types of machine learning models. This flexibility makes it easier to accelerate the applications based on the most optimal numerical precision and memory model being used. Because FPGAs are reconfigurable, you can stay current with the requirements of rapidly changing AI algorithms.

Microsoft Azure is the world's largest cloud investment in FPGAs. Microsoft uses FPGAs for deep neural networks (DNN) evaluation, Bing search ranking, and software defined networking (SDN) acceleration to reduce latency, while freeing CPUs for other tasks.

FPGAs on Azure are based on Intel's FPGA devices, which data scientists and developers use to accelerate real-time AI calculations. This FPGA-enabled architecture offers performance, flexibility, and scale, and is available on Azure.

Azure FPGAs are integrated with Azure Machine Learning. Azure can parallelize pre-trained DNN across FPGAs to scale out your service. The DNNs can be pre-trained, as a deep featurizer for transfer learning, or fine-tuned with updated weights.

* ASIC: This VM providers faster performance than FPGA, but it is 
not flexible and configurable. Not supported by AKS.
GPU: This VM provides slower performance than FPGA. It is intended for fast parallel image rendering. This processor is popular for Al computations and parallel image rendering.
* CPU: This VM provides the slowest performance. It is intended for
general purpose processing, not graphics processing.

AKS: This service allows you to deploy a Kubernetes cluster to the cloud. A Kubernetes cluster consists of nodes and pods. A node is either a virtual machine (VM) or physical machine. A pod is an application-specific logical host that contains different application containers, each with its own IP address and port space. AKS supports real-time inference, or model scoring. It also supports Graphical Processing Unit (GPU) and FGPA. It supports GPU but that requires you to deploy your model as a web service.

FGPA processors are flexible and configurable over time, and they are faster than GPU. GPI-J processors are good for fast parallel image rendering.

ACI does not support FGPA or GPU. It is useful for testing and debugging CPU based workloads that require less than 48GB of RAM.

Machine Learning Compute: This service allows you to run batch scoring on a serverless compute infrastructure. It supports GPU but not FPGA or real-time scoring.

## 5. Design for data governance, compliance, integrity, and security
Always encrypted: This security solution encrypts data at the client application before it leaves the user device. The data stays encrypted during transmission to the database server, and remains encrypted at the server. This is referred to as encryption at the client.

Encryption in Motion: TLS and SSL secure data during transmission.

TDE: Encrypts the entire database at the server, including the transaction logs. It does not prevent data from being compormised if the desktop computer is compromised.