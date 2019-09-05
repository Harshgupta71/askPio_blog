---
layout: post
title:  "Restart Azure Web App Using Azure Logic App"
author: harsh
categories: [ ]
image: assets/images/08292019/img8.png
---

### Introduction: 
In this article, we are going to see how to restart the Azure web app using Azure Logic App. I am considering that you know about the azure logic app. If you want to read more about, what is Azure logic app? How does it work? Then refer the below article. 
  https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-overview

### Prerequisite:
For Creating Logic App which will restart the Azure web app, you must need the following items and access. 
1.	Azure portal access where Azure web App is deployed. 
2.	Tenant Id of your azure account 
3.	Client_id 
4.	Client_secret 
5.	Azure Subscription Id
6.	Resource Group 
7.	App name 

### Steps: 
Restart Azure web app using Azure logic app will have three simple steps as shown below. 

![LogicApp]({{ site.baseurl }}/assets/images/08292019/img1.png)

We will discuss all these steps in detail in the following section. 

### Start Designing of the Azure Logic App: 
### Step 1: Get Access Token (HTTP)
First, we need to add the HTTP action in-order to generate and get the access token. This action is having a post method and required tenant_id, client_id, client_secret. 
```
"method": "POST"
"uri": "https://login.microsoftonline.com/{tenant_id}/oauth2/token"
"body": "grant_type=client_credentials&client_id={client_id} &client_secret{client_secret}&resource=https://management.core.windows.net/"
"Content-Type": "application/x-www-form-urlencoded"
}
```
![CodeView]({{ site.baseurl }}/assets/images/08292019/img2.png)

After execution, we will get a JSON result which will have a access_token value which is required to restart the app.

JSON result looks like as below 

![CodeView]({{ site.baseurl }}/assets/images/08292019/img3.png)

### Step 2: 
Parse the JSON and get the body and define the schema using Use sample payload to generate the schema. 

![CodeView]({{ site.baseurl }}/assets/images/08292019/img4.png)

### Step 3: 
Restart App (HTTP)

For this HTTP request, we need a subscription id, resource group and app name of azure web app. We need to pass the access_token from previous step in the Authorization field. 

```
"method": "POST"
"uri": "https://management.azure.com/subscriptions/{subscription_id}/resourceGroups/{resource_group}/providers/Microsoft.Web/sites/{webApp_name}/restart?api-version=2016-08-01"
"Authorization": "Bearer @{body('Parse_JSON')?['access_token']}",
"Content-Type": "application/json"
}
```

![CodeView]({{ site.baseurl }}/assets/images/08292019/img5.png)

### Run Logic App:
Your logic app is ready and now run this and see results in history.

![CodeView]({{ site.baseurl }}/assets/images/08292019/img6.png)

### The activity log of web app: 
Check the webApp activity log. You might need to wait for 1-2 mins in-order to update this. 

![CodeView]({{ site.baseurl }}/assets/images/08292019/img7.png)

### Expected Result: 
The Logic app has configured properly and worked as per expected. It is restarting the azure web app, we can configure this on-demand and set it scheduled. For on-demand, we can use email receiving event and restart it on receiving an email with a specific subject line. This is as given below.  

### Automate the Logic app on email receiving: 
To make this process automate, we can configure the above logic app on receiving an email with some defined text in the subject. Now whenever you will receive an email with defined subject then logic app will run automatically. 

![CodeView]({{ site.baseurl }}/assets/images/08292019/img8.png)

### Summary: 
In the above article, we see how to restart the azure web app using the logic app. We also see use email receiving an event to restart the app. Apart from the restart, we can perform many more operations like stop, start etc. For more trigger API's refer the below URL and configure those in the above logic app accordingly.  

https://docs.microsoft.com/en-us/rest/api/appservice/webapps/stop

