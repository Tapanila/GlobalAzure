# Creating web app
### Objectives
  
 After completing this lab, you will be able to:

- Create a new web app.

- Deploy a web app.

- Manage web apps.

## Exercise 1: Creating web apps
  
### Scenario
  
You must set up a test web app in Azure. As the first step in the setup process, you want to create a new web app. Later in this lab, you will deploy this web app to the test web app. 

The main tasks for this exercise are as follows:

1. Create a web app

2. Add a deployment slot

3. Configure deployment credentials

#### Task 1: Create a web app
  
1. Connect to Virtual Machine running on Azure that you created on Lab 1. 

2. Open Internet Explorer, browse to the Azure portal, and then sign in using the Microsoft account.

3. To create a new web app, use the following information:


  - App name: _any unique valid name_

  - Resource Group: **globalazure**

  - Web Hosting Plan Name: **WebAppStandardPlan**

  - Location: _an Azure region near you_

  - Pricing tier: **S1 Standard**

  - Application Insights: _leave at its default value_


#### Task 2: Add a deployment slot
  
1. In the Azure portal, add a new deployment slot to the web app that you created in the first task, using the following information:

  - Name: **Staging**

  - Configuration Source: _choose the web app you created in Task 1_
  
2. Choose Deployment Credentials and set the following deployment credentials for the web app

  - FTP/Deployment User Name: _a unique name_

  - Password: **Pa55w.rd**

> **Result**: After completing this exercise, you should have created a new web app in the Azure portal, and configured the new web app with deployment slots and deployment credentials.


## Exercise 2: Deploying a web app
  
### Scenario
  
Now that you created a web app in Azure, and added a deployment slot for the web app, you can publish the internally developed web app that the A. Datum web-development team supplied. In this exercise, you will use a publishing profile in Visual Studio 2015 to connect to the new web app and deploy the web content. 

The main tasks for this exercise are as follows:

1. Download web application source code

2. Obtain a publishing profile

3. Deploy a web app

#### Task 1: Download web application source code

1. Download the zip containing source code https://github.com/Tapanila/GlobalAzure/raw/master/Lab%202%20-%20Creating%20web%20app/Lab%202%20-%20Creating%20web%20app.zip

2. Extract the zip file

#### Task 2: Obtain a publishing profile
  
1. From the Azure portal, download the publish profile for the Web app you created in Exercise 1.

2. Open the web-application that you downloaded on Task 1 \\AdatumWebsite\\AdatumWebsite.sln in Visual Studio 2015

3. Start debugging the web application, examine the contents, and then close Internet Explorer.

> **Note:** When you start the web application in Visual Studio, the web app runs in IIS Express on your local workstation.


#### Task 3: Deploy a web app
  
1. In Visual Studio, start the Publish Wizard for the **AdatumWebsite** project, and then import the **.PublishSettings** file that you downloaded in task 1 of this exercise.

2. Verify that the publish settings file includes correct connection information.

3. Ensure that the Release configuration is used for the published web app.

4. Preview the file changes, and then **Publish** the new website to Azure.
> **Note:** The publish operation may take approximately two to three minutes. When the operation is complete, Microsoft Edge opens and displays the new web app hosted in Azure.

5. Verify that A. Datum's web app is open in Microsoft Edge, and then verify the web app's current address.

6. Close Microsoft Edge.

7. Leave Visual Studio open.


> **Result**: After completing this exercise, you should have deployed a web app hosted in Azure. 


## Exercise 3: Managing web apps
  
### Scenario
  
 The web-deployment team created an updated style sheet for the A. Datum's test web app. You have to demonstrate how you can deploy these changes to a staging slot, and then test them, before you deploy to the production A. Datum web app. In this exercise, you will upload the new web app to the staging slot that you created in Exercise 1, and you then will swap the new version of the web app into the production slot.

The main tasks for this exercise are as follows:

1. Deploy a web app for staging

2. Swap deployment slots

3. Roll back a deployment



#### Task 1: Deploy a web app for staging
  
1. In the Azure portal, download a publishing profile for the Staging slot for your web app.

2. Open the project you downloaded on Task 1 \\NewAdatumWebsite\\AdatumWebsite.sln in Visual Studio 20

3. Start the web app publishing process and import the staging publishing profile that you downloaded in the first step.

4. Validate the connection, and then choose the Release configuration.

5. Publish the new web app to the Staging slot.

6. Close Microsoft Edge.

7. Leave Visual Studio open.



#### Task 2: Swap deployment slots
  
1. In Internet Explorer, in the Azure portal, navigate to the web app that you created in Exercise 1.

2. From the Azure portal, use the **URL** link for your web app to open it in another Internet Explorer tab.

3. Notice that the color scheme has not changed, because the Web app with the new color scheme is still in the staging slot. Close the Internet Explorer tab displaying the A. Datum web app.

4. From the web app blade in the Azure portal, swap the staging and production web-app slots.

5. When the swap completes, use the **URL** link again to browse to the web app and notice that the color scheme has changed.

6. Close the Internet Explorer tab that displays the A. Datum's web app.



#### Task 3: Roll back a deployment
  
1. In the Azure portal, swap the staging and production slots again.
> **Note:** By swapping the slots a second time, you simulate a deployment rollback.

2. When the swap is complete, browse to the web app. Notice that the color scheme has reverted to the original one.

3. Close the Internet Explorer tab displaying the A. Datum web app.


> **Result**: After completing this exercise, you should have an updated web app in the staging slot and have tested the slot swap functionality.


©2016 Microsoft Corporation. All rights reserved.

The text in this document is available under the [Creative Commons Attribution 3.0 License](https://creativecommons.org/licenses/by/3.0/legalcode "Creative Commons Attribution 3.0 License"), additional terms may apply.  All other content contained in this document (including, without limitation, trademarks, logos, images, etc.) are **not** included within the Creative Commons license grant.  This document does not provide you with any legal rights to any intellectual property in any Microsoft product. You may copy and use this document for your internal, reference purposes.

This document is provided "as-is." Information and views expressed in this document, including URL and other Internet Web site references, may change without notice. You bear the risk of using it. Some examples are for illustration only and are fictitious. No real association is intended or inferred. Microsoft makes no warranties, express or implied, with respect to the information provided here.

  
