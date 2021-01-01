# Implement and monitor AI solutions (25-30%)
Implement an AI workflow
* develop AI pipelines
* manage the flow of data through the solution components
* implement data logging processes
* define and construct interfaces for custom AI services
* create solution endpoints
* develop streaming solutions
Integrate AI services and solution components
* configure prerequisite components and input datasets to allow the consumption of
Azure Cognitive Services APIs
* configure integration with Azure Cognitive Services
* configure prerequisite components to allow connectivity to the Microsoft Bot Framework
* implement Azure Cognitive Search in a solution
Monitor and evaluate the AI environment
* identify the differences between KPIs, reported metrics, and root causes of the
differences
* identify the differences between expected and actual workflow throughput
* maintain an AI solution for continuous improvement
* monitor AI components for availability
* recommend changes to an AI solution based on performance data

Example: You deploy an Azure Machine Learning model to an Azure Kubernetes Service (Al(S) cluster. The model runs 10 times daily. You need to determine the accuracy of each model run.

Solution: Configure Azure Monitor for Containers.
Azure Monitor for containers allows you to monitor processor and
memory metrics. It does not allow you to monitor Machine Learning model runs. You should enable Application Insights diagnostics to monitor model runs.

Solution: Modify the model's scoring file and AKS configuration file to enable data collection.
The model scoring file allows you to add code to declare data collection variables. The AKS configuration file allows you to enable data collection.

Solution: Enable Application Insights diagnostics
In the Azure Portal for your Machine Learning work space, you can enable Application Insights diagnostics. Application Insights allows applications, websites, and services to send telemetry data to Azure in real time. This includes Machine Learning model runs.


You and your team are developing an Al solution that integrates with Azure Search. The solution allows customers to search for vehicles by speaking to an app. You create an Azure Search Index that stores vehicles. 

You have the following code to test the search functionality:

var client = new SearchlndexClient(searchServiceName, searchlndexName, new SearchCredentials(apiKey));
var params = new SearchParameters(){Select=new[]{"Vin", "Model"}};
var results = client.Documents.Search("M8", params);
return results;

You need to ensure that the code works as intended.
What does this code do?

* It returns the Vin and Model fields of all documents in the index that have the term M8.
* It returns all documents where M8 is present in either the Vin or Model fields.
* It returns the Vin and Model fields where they have non-empty strings or the term M8.
* It returns all documents where the Vin and Model fields have non-empty strings or the term M8.

It returns the Vin and Model fields of all documents in the index that have the term "8. The Search method of the SearchlndexClient class accepts two parameters: a parameter that specifies the text to be searched, and a parameter that specifies a SearchParameters instance representing search parameters. Search parameters include filters and fields to be returned from the search. If the first parameter's value is * this means to search for everything. The Select property of the SearchParameters class represents an array
of fields to be returned, which are Vin and Model in this scenario.

You and your team are developing an Al solution that integrates with Azure Search. It allows users to search for vehicles by speaking into an app. You have the following code to test the search functionality:
var client = new SearchlndexClient(searchServiceName, searchlndexName, new SearchCredentials(apiKey));
var params = new SearchParameters(){Select=new[]{"Vin"}};
var results = client.Documents.Search("M8", params);

You need to ensure that the code works as intended.
What does this code do?

Choose the correct answer:
* It returns the Vin field of all vehicles where the Vin field contains the word M8.
* It returns the Vin field of all vehicles where any field contains the word M8.
* It returns all fields of all vehicles where any field contains the word M8.
* It returns all fields of all vehicles where the Vin field contains the word M8.

It returns the Vin field of all vehicles where any field contains the word M8. 

The Search method of the SearchlndexClient class accepts two parameters: a parameter that specifies the text to be searched, and a parameter that specifies a SearchParameters instance representing search parameters. Search parameters include filters and fields to be returned from the search. If the first parameter's value is * , this means to search for everything. The Select property of the SearchParameters class represents an array of fields to be returned, which is only Vin in this scenario.

You are implementing an Al solution that uses a bot built with Azure Bot Framework and a knowledge base built with QnA Maker. You need to gather all the information required by the bot to access the knowledge base. Which three configuration parameters should you gather?

You need to configure the bot with the App service endpoint, the knowledge base ID, and the knowledge base endpoint key. 

The app service endpoint specifies the URL of the App Service that hosts the QnA Maker API. Whenever you deploy QnA Maker, it automatically creates an App Service in Azure. 

The knowledge base ID represents the knowledge base that contains the questions and answers. This ID is a GUID that you can find in the QnA Maker portal. 

The knowledge base endpoint key is a secret key used to access the knowledge base remotely. You can also find this in the QnA Maker portal. 

You do not need to configure the bot with a Search service name or Search index name. Although QnA Maker uses a Search service an index, the bot does not need to know this information. The web API that represents the QnA Maker service API needs Search service information. You do not need to configure the bot with a bot messaging endpoint. The bot messaging endpoint represents the URL of the code representing the bot's API. The bot channel registration needs to know the bot messaging endpoint.

You deploy a bot by using Azure Bot Service and Azure Bot Framework. The bot will allow shoppers to find products and information about those products in local stores. You want to collect the following key performance indicator (KPI) data from the bot: 
• The number of shoppers connected 
• The number of messages sent and received 
• The different ways the shoppers are using the bot, such as through Skype, e-mail, or an iframe on a website 

You want to configure Bot Analytics to collect this data. 
What should you do?

* Create a Stream Analytics job that uses SQL-based queries to access shopper, message, and channel data.
* Create an Application Insights resource and configure the bot's settings with the instrumentation key, application ID, and API Key.
* Create an Event Hubs resource and enable Capture.
* Create a Machine Learning experiment and use the Train Model module to look at shoppers, messages, and channels.

You should create an Application Insights resource and configure the bot's settings with the instrumentation key, application ID, and API Key. Bot Analytics is an extension of Application Insights that allows applications to send telemetry data in real time to the cloud. By configuring the bot's settings with these parameters, you allow bot telemetry data to be sent to Azure, and you allow the Bot Analytics page in the Azure portal to read this telemetry data. 

You should not create a Machine Learning experiment and use the Train Model module to look at shoppers, messages, and channels. A Machine Learning experiment allows you to creates models to predict trends based on historical data. The Train Model module uses a classification or regression model to run algorithms against data. 

You should not create a Stream Analytics job that uses SQL-based queries to access shopper, message, and channel data. Stream Analytics is a real-time analytics and event processing service that analyzes high volumes of streaming data.

You should not create an Event Hubs resource and enable Capture. Event Hubs allows you to process fast streaming events in real-time from applications, websites, and IOT devices. Enabling Capture allows you to automatically send those events to a Blob storage account or a Data Lake storage account.

You implement a pipeline for an Azure Machine Learning experiment. The purpose of the experiment is to predict test scores. You need to determine the relative difference between the actual and the predicted values. Your solution must not require you to write code. Which module should you use to visualize and view the difference?

You should use the Evaluate Model module. This module calculates metrics for the differences between the predicted and actual values. One of these metrics is relative absolute error (RAE), which is the relative difference between the predicted and actual values.

There are three ways to use the Evaluate Model module:

* Generate scores over your training data, and evaluate the model based on these scores
* Generate scores on the model, but compare those scores to scores on a reserved testing set
* Compare scores for two different but related models, using the same set of data

You should not use the Train Model module. Its purpose is to train a classification or regression model. Training uses specific algorithms to make predicted values based on an input data set. 

You should not use the Create R Model module. This module requires you to write R scripts to perform training and scoring (prediction).

You should not use the Score Model module. This module makes predictions from a trained classification or regression model.

After you have generated a set of scores using Score Model:

* To generate a set of metrics used for evaluating the model’s accuracy (performance). you can connect the scored dataset to Evaluate Model,
* Right-click the module and select Visualize to see the a sample of the results.
* Save the results to a dataset.

The score, or predicted value, can be in many different formats, depending on the model and your input data:

* For classification models, Score Model outputs a predicted value for the class, as well as the probability of the predicted value.
* For regression models, Score Model generates just the predicted numeric value.
* For image classification models, the score might be the class of object in the image, or a Boolean indicating whether a particular feature was found.

You deploy a Machine Learning model to an Azure Kubernetes Service (Al(S) cluster. You modify the score.py file with the following code:

from azureml.core.webservice import Webservice
service= Webservice(ws, "sample-ml-service");

You need to complete the code to log only custom traces.
Which code segment should you use?

service.update(collect model data=False);
service.update(enable_app_insights=True);
service.deploy_configuration(collect model data=True);
service.deploy_configuration(collect model data=True, enable_app_insights=False);

You should use the following code segment:

service.update(enable_app_insights=True);

This code enables Application Insights. This service is a feature of Azure Monitor that allows websites, applications, and other resources to send telemetry data to the cloud in real time.

You should not use the following code segment:
service.deploy_configuration(collect_model_data=True, enable_app_insights=False);
The deploy_configuration method creates a deployment configuration. The problem with this code is that Application Insights is disabled (enable_app_insights=False). This prevents the service from logging custom traces.

You should not use the following code segment:
service.update(collect_model data-False);
This code disables model collection, which is correct because only custom traces should be logged. However, it does not specify a value for enable_app_insights, which causes the default value of False to be used. This effectively disables Application Insights.

You should not use the following code segment:
service.deploy_configuration(collect_model_data=True);
This code enables model collection, which causes data other than custom traces to be logged. It also does not specify a value for enable_app_insights, which causes the default value of False to be used. This effectively disables Application Insights.