---
layout: post
title:  "Schedule Azure WebJobs using Azure Logic Apps"
author: harsh
categories: [ ]
image: assets/images/10012019/image8.png
featured: false
---

### Introduction: 
In this article, we will see how to migrate Azure WebJobs from Azure Scheduler to Azure Logic Apps. As we all know that Azure Scheduler will become obsolete on 31st December 2019, after which all Scheduler job collections and jobs will stop running and they will be deleted from the system. In order to continue to use jobs, we must move Azure Schedulers to Azure Logic Apps as soon as possible. Azure Logic Apps have numerous features which are as below:-

1.  Uses a visual designer and connectors to integrate with more than 200 different services, including Azure Blob storage, Azure Service Bus, Microsoft Outlook, and SAP. 
2.	Manages each scheduled workload as a first-class Azure resource. 
3.	Runs multiple one-time jobs using a single logic app. 
4.	Sets schedules that automatically adjust to daylight saving time.
5.	For more details about its features and usage please refer to the below article.

[Migrate Azure Scheduler jobs to Azure Logic Apps](https://docs.microsoft.com/en-us/azure/scheduler/migrate-from-scheduler-to-logic-apps)

### Before going further, Let’s know something Azure WebJobs:
WebJobs is a feature of [Azure App Service](https://docs.microsoft.com/azure/app-service/) that enables you to run a program or script in the same context as a web app, API app, or mobile app. There is no additional cost to use WebJobs. For more detail please refer to the below article. 

[Run Background tasks with WebJobs in Azure App Service](https://docs.microsoft.com/en-us/azure/app-service/webjobs-create)

### Now, we will see step by step, how to schedule Azure WebJobs using Azure Logic Apps.

Step1: Create and deploy an on-demand (triggered) job under Azure App Service. [Click here](https://docs.microsoft.com/en-us/azure/app-service/webjobs-create) to learn how to create and deploy a WebJob. 