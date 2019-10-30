---
layout: post
title:  "Setup Azure CI/CD Pipelines using Visual Studio"
author: harsh
categories: [ ]
image: assets/images/10162019/image16.png
featured: false
---

### Introduction: 
Today, we are going to see how to configure Azure DevOps CI/CD and setup Azure Pipeline using visual studio. 

Not spending the time on what is Azure DevOps and its feature, we are directly moving to CI/CD. How can we configure this using visual studio? We will see this step by step. Once we set up the Azure Pipeline then on each check-in it will build the application and deploy the changes on App Service. 

In this article, we will see how to configure the CI/CD for a single project in one solution. In the next article, we will see how to configure the CI/CD for multiple projects in one solution. 
To know about Azure DevOps and its other features, you can refer to the below blog. 

[Introducing Azure DevOps](https://azure.microsoft.com/en-in/blog/introducing-azure-devops)

### Prerequisite:
For configuring the Azure DevOps CI/CD, you need the following tools. 
1.	Azure DevOps Account 
2.	Azure Portal Account
3.	Visual Studio 2012+(in my example I am using VS 2019) 

### Steps:
We will see how to configure CI/CD and setup Azure Pipeline using Azure DevOps. 

### Step 1:
Create a new project by using the Azure DevOps account. I am using Team Foundation version control, but you can use Git too.

![Create Project on Azure DevOps]({{ site.baseurl }}/assets/images/10162019/image1.png)
Create Project on Azure DevOps

### Step 2:
Configure the newly created project in Visual studio source control on your local system. 

![Configure Source Control]({{ site.baseurl }}/assets/images/10162019/image2.png)
Configure Source Control

### Step 3:
Create a new project with a solution in Visual Studio and add this in DevOps Source Control then check-in the changes. 

![Create a New Project with Solution]({{ site.baseurl }}/assets/images/10162019/image3.png)
Create a New Project with Solution

![Creating Project and Solution]({{ site.baseurl }}/assets/images/10162019/image4.png)
Creating Project and Solution

![Added project in Solution control ]({{ site.baseurl }}/assets/images/10162019/image5.png)
Added project in Solution control 

### Step 4:
Setup Azure Pipelines under the publish settings of your solution. 

![Setup Azure Pipeline]({{ site.baseurl }}/assets/images/10162019/image6.png)
Setup Azure Pipeline

### Step 5:
Wait for a few mins and then go the pipelines under Azure DevOps. You will see a new Pipeline created and the build of the project has started. 

![DevOps Pipeline Created]({{ site.baseurl }}/assets/images/10162019/image7.png)
DevOps Pipeline Created

### Step 6:
Check the Deployment Center on the Azure portal for your App Service, for which you have set up the Azure Pipeline in step 4.

![Azure App Deployment Center]({{ site.baseurl }}/assets/images/10162019/image8.png)
Azure App Deployment Center

### Step 7:
If there is no error in the build, then after some time your build has succeeded. It is taking a few mins. In my example, it takes up to 1min 21 sec. 

![Build Succeeded]({{ site.baseurl }}/assets/images/10162019/image9.png)
Build Succeeded

### Step 8:
As the build succeed the new release would be created and started pushing the release changes on App service. 

![Release the changes]({{ site.baseurl }}/assets/images/10162019/image10.png)
Release the changes

