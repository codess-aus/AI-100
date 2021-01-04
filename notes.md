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

LUIS:

LUIS makes use of three key aspects for understanding language:

* Utterances: An utterance is input from the user that your app needs to interpret.
* Intents: An intent represents a task or action the user wants to do. It's a purpose or goal expressed in a user's utterance.
* Entities: An entity represents a word or phrase inside the utterance that you want to extract.

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

