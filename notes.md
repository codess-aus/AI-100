# Notes

Text Moderation API:

* A list of potentially unwanted words found in the text.
* What type of potentially unwanted words were found.
* Possible personally identifiable information (PII) found in the text.

With the Text Moderation API, you can:

* Analyze text to look for unwanted content.
* Classify the potentially offensive content.
* Get insights into the potential PII that's being shared so that you can protect it.

The Text Analytics API is a cloud-based service that provides Natural Language Processing (NLP) features for text mining and text analysis, including:
* sentiment analysis, 
* opinion mining,
* key phrase extraction,
* language detection,
* named entity recognition.

The Text Analytics API is a cloud-based service that provides advanced natural language processing over raw text, and includes four main functions: sentiment analysis, key phrase extraction, named entity recognition, and language detection.

The Key Phrase Extraction API evaluates unstructured text, and for each JSON document, returns a list of key phrases. Key phrase extraction is useful if you need to quickly identify the main points in a collection of documents.

The Language Detection API evaluates text input and, for each document submitted, returns language identifiers with a score indicating the strength of the analysis. Text Analytics recognizes up to 120 languages.

This capability is useful for content stores that collect arbitrary text, where language is unknown. Another scenario could involve a chat bot. If a user starts a session with the chat bot, language detection can be used to determine which language they are using and allow you to configure your bot responses in the appropriate language.

Language detection can work with documents or single phrases. It's important to note that the document size must be under 5,120 characters. The size limit is per document and each collection is restricted to 1,000 items (IDs).

LUIS:

LUIS makes use of three key aspects for understanding language:

* Utterances: An utterance is input from the user that your app needs to interpret.
* Intents: An intent represents a task or action the user wants to do. It's a purpose or goal expressed in a user's utterance.
* Entities: An entity represents a word or phrase inside the utterance that you want to extract.

An entity extracts data from a user utterance at prediction runtime. An optional, secondary purpose is to boost the prediction of the intent or other entities by using the entity as a feature.

There are several types of entities:

Machine-learning entity - this is the primary entity. You should design your schema with this entity type before using other entities.
Non-machine-learning used as a required feature - for exact text matches, pattern matches, or detection by prebuilt entities.
Pattern.any - to extract free-form text such as book titles from a Pattern.

Utterances are the phrases that a users might enter when interacting with an app that is tied to your LUIS model. Your LUIS app will need to interpret these utterances and match them to the correct Intent. When entering your utterances, keep these aspects in mind:

Capture a variety of different examples, or alternative ways of saying the same thing
Vary the length of the utterances from short, to medium, to long
Vary the location of the noun or subject of the utterance. Place it at the beginning, the end, or somewhere in between
Use correct grammar and incorrect grammar in different utterances to offer good training data examples
Follow the guidance on the (good utterances)[https://docs.microsoft.com/en-us/azure/cognitive-services/luis/luis-concept-utterance] page

Azure Stream Analytics: is a real-time analytics and complex event-processing engine that is designed to analyze and process high volumes of fast streaming data from multiple sources simultaneously. Patterns and relationships can be identified in information extracted from a number of input sources including devices, sensors, clickstreams, social media feeds, and applications. These patterns can be used to trigger actions and initiate workflows such as creating alerts, feeding information to a reporting tool, or storing transformed data for later use. Also, Stream Analytics is available on Azure IoT Edge runtime, enabling to process data on IoT devices.

The following scenarios are examples of when you can use Azure Stream Analytics:

* Analyze real-time telemetry streams from IoT devices
* Web logs/clickstream analytics
* Geospatial analytics for fleet management and driverless vehicles
* Remote monitoring and predictive maintenance of high value assets
* Real-time analytics on Point of Sale data for inventory control and anomaly detection

Stream Analytics has first-class integration with four kinds of resources as inputs:

* Azure Event Hubs
* Azure IoT Hub
* Azure Blob storage
* Azure Data Lake Storage Gen2

(AKS). Azure Kubernetes Service is good for high-scale production deployments. Use Azure Kubernetes service if you need one or more of the following capabilities:

Fast response time
Autoscaling of the deployed service
Logging
Model data collection
Authentication
TLS termination
Hardware acceleration options such as GPU and field-programmable gate arrays (FPGA)

(ACI). Use Azure Container Instances if one of the following conditions is true:

You need to quickly deploy and validate your model. You do not need to create ACI containers ahead of time. They are created as part of the deployment process.
You are testing a model that is under development.

To deploy a model to Azure Container Instances, create a deployment configuration that describes the compute resources needed. For example, number of cores and memory. You also need an inference configuration, which describes the environment needed to host the model and web service.

ACI is suitable only for small models that are under 1 GB in size.
We recommend using single-node AKS to dev-test larger models.

how to use Azure Machine Learning to deploy a GPU-enabled model as a web service. The information in this article is based on deploying a model on Azure Kubernetes Service (AKS). The AKS cluster provides a GPU resource that is used by the model for inference.

Inference, or model scoring, is the phase where the deployed model is used to make predictions. Using GPUs instead of CPUs offers performance advantages on highly parallelizable computation.

For web service deployments, GPU inference is only supported on Azure Kubernetes Service. For inference using a machine learning pipeline, GPUs are only supported on Azure Machine Learning Compute.

FPGAs contain an array of programmable logic blocks, and a hierarchy of reconfigurable interconnects. The interconnects allow these blocks to be configured in various ways after manufacturing. Compared to other chips, FPGAs provide a combination of programmability and performance.

FPGAs make it possible to achieve low latency for real-time inference (or model scoring) requests. Asynchronous requests (batching) aren't needed. Batching can cause latency, because more data needs to be processed. Implementations of neural processing units don't require batching; therefore the latency can be many times lower, compared to CPU and GPU processors.

You can reconfigure FPGAs for different types of machine learning models. This flexibility makes it easier to accelerate the applications based on the most optimal numerical precision and memory model being used. Because FPGAs are reconfigurable, you can stay current with the requirements of rapidly changing AI algorithms.

Azure Machine Learning uses pipelines to create reproducible and easy-to-manage sequences of computation. It also offers a managed compute target (on which a pipeline computation can run) called Azure Machine Learning Compute for training, deploying, and scoring machine learning models.

Key phrase extraction Examples:

* integrate speech to text and analyze customer support calls to determine their most common issues with your products
* monitor social media feeds. Perhaps you are running a political campaign and want to see how the candidates are being perceived on social media. You can mine the posts on feeds, such as Twitter, and then extract key phrases from the tweets
* evaluate a set of documents for classified or sensitive information and decide whether to release them or not

