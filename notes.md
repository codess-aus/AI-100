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

Utterances: An utterance is input from the user that your app needs to interpret.
Intents: An intent represents a task or action the user wants to do. It's a purpose or goal expressed in a user's utterance.
Entities: An entity represents a word or phrase inside the utterance that you want to extract.

Azure Stream Analytics: is a real-time analytics and complex event-processing engine that is designed to analyze and process high volumes of fast streaming data from multiple sources simultaneously. Patterns and relationships can be identified in information extracted from a number of input sources including devices, sensors, clickstreams, social media feeds, and applications. These patterns can be used to trigger actions and initiate workflows such as creating alerts, feeding information to a reporting tool, or storing transformed data for later use. Also, Stream Analytics is available on Azure IoT Edge runtime, enabling to process data on IoT devices.

The following scenarios are examples of when you can use Azure Stream Analytics:

Analyze real-time telemetry streams from IoT devices
Web logs/clickstream analytics
Geospatial analytics for fleet management and driverless vehicles
Remote monitoring and predictive maintenance of high value assets
Real-time analytics on Point of Sale data for inventory control and anomaly detection

Stream Analytics has first-class integration with four kinds of resources as inputs:

Azure Event Hubs
Azure IoT Hub
Azure Blob storage
Azure Data Lake Storage Gen2