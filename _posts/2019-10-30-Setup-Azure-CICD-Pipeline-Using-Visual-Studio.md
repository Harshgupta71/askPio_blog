---
layout: post
title:  "Setup Azure CI/CD Pipelines using Visual Studio"
author: harsh
categories: [ ]
image: assets/images/10162019/image16.png
featured: false
---

### Introduction: 
We are going to see how to configure Azure DevOps CI/CD and setup Azure Pipeline using visual studio. 
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
