# logic_app_dev_vs_code
This project belongs to Azure Logic Apps - Standard subscription project configuration in visual studio code. 


Description: In this article, we can learn about how to setup visual studio code setup for azure logic app standard and configure the sample logic app for quick run
Pre-requisites:
1.	Azure Subscription.
2.	Visual Studio Code
Download & Install Visual Studio Code:
Where to visit to install visual studio code?
Visit official Visual Studio Code website and download the installer for your operating (Windows, macOS, or Linux). Once downloaded, run the installer and follow the on-screen instructions to complete the installation process.
Step 1: Goto https://code.visualstudio.com/ website and selecting Download for Windows download button for installer setup on my windows machine.

![image info](./Images/1.png)


Step 2: Once installer setup is completed, we need to click on Extensions section which is left side of the window and below screenshot for quick reference.


![image info](./Images/2.png)


Now type Azure Standard Logic Apps in the extensions search bar to view the Azure standard logic app extension will be visible as shown below.

![image info](./Images/3.png)

Step 3.Select the ‘Azure Logic Apps (Standard)’ extension and click on install button which is shown below, then automatically supported extensions also installed without any prompt.

![image info](./Images/4.png)

Step 4.If you select a single extension i.e., ‘Azure Logic Apps (Standard)’, then the rest of the required extensions will be installed without any user consent, so make sure when you’re downloading the right extension for your logic app development in the visual studio code.

![image info](./Images/C.png)


Now Azure Menu snippet will be visible as shown below, In the workspace section, thereis an Azure logic app symbol to create a new project or workspace or workflows or deploy logic app as shown in the below screenshot. Select Create a new project option to create a sample project for your development.

![image info](./Images/5.png)

Select Stateful workflow for sample workflow creation and continue,


What is workflow?

Utilize this tool to outline the various stages of your business operations through an intuitive graphical interface. Visualize, design, build, automate and deploy business processes as a series of steps.

![image info](./Images/6.png)

Now type workflow name as per your requirement and I entered as a hello_world for workflow name as shown below.

![image info](./Images/7.png)


Now if you see below screenshot, Sample folder structure will be created along with workflow. Make sure below folders are created without any issues on the access level over your build machine(laptop).


![image info](./Images/8.png)

Now right-click on workflow.json and select the ‘Open Designer’ option to view the workflow designer and to support the workflow designer in your local machine there is a workflow-runtime folder that will help us to view all our workflows in the designer mode.


![image info](./Images/9.png)

Now the empty designer view is opened as shown below, Click on the ‘Add a trigger’ option to add your workflow triggers.

![image info](./Images/10.png)


# How many type of triggers are available in Azure Logic Apps (Standard) ?

#### 1. Poll triggers: These triggers are helps us to poll the service in specified frequency and all polling configuration needs to setup when we are choosing the poll service like SFTP file triggers, Blob triggers, SAP Message queue triggers, SQL table poll trigger etc.

#### 2. Push trigger: This will listen the data when a new event to happen or some another service will trigger this endpoint etc.

#### 3. Recurrence trigger: These triggers are act as schedulers, it will trigger or start process of your workflow on prescribed schedule.


![image info](./Images/11.png)

Our plan is to build a sample http service in Azure Logic Apps Standard, So type http in the search textbox and select a ‘When a HTTP request is received’ trigger for your workflow.

![image info](./Images/12.png)


Now, HTTP trigger will be added to your workflow and if you find right side popup window, there was multiple options will be visible and we can ignore for now.

![image info](./Images/13.png)

![image info](./Images/14.png)

Now, click on ‘+’ symbol again to add response task in next step of the workflow.


![image info](./Images/15.png)



Enter response in the search box and select ‘Response’ action.


![image info](./Images/16.png)

Now give 200 as a response status code.

1xx: Informational:Communicates transfer protocol-level information.

2xx: Success: Indicates that the client’s request was accepted successfully.

3xx: Redirection:Indicates that the client must take some additional action in order to complete their request.

4xx: Client Error:This category of error status codes points the finger at clients.

5xx: Server Error:The server takes responsibility for these error status codes.


![image info](./Images/17.png)

Now go to ‘Run’ Menu option select ‘Start Debugging’ to run your azure logic app standard in your local machine as a local host.

![image info](./Images/18.png)

On the initial run on your local system, default azure rite files will created as shown in below screenshot and please be patient for first run, it will take some time to create a supported files & load into the project.

![image info](./Images/19.png)

On successful build for your azure logic app workflows, function host will be initiated to activate your workflows endpoints as REST API’s (If you created a HTTP trigger workflow).

![image info](./Images/20.png)

Now go to your workflow folder, right click on workflow.json file and click on ‘Overview’ option.


![image info](./Images/21.png)

Now Azure Logic App workflow call back url will be visible as shown in below and try to copy to run it in the POSTMAN tool for initial test.

![image info](./Images/22.png)

Open POSTMAN tool, create a sample request and past azure logic app workflow callback url into url section, change the method type to ‘POST’ and click on ‘Send’ button as shown in below.

If you observe parameters sections, there is a sig key is the major thing to handle authentication for your logic app workflows.

![image info](./Images/23.png)

Once POSTMAN hit is completed, you will get 200 OK response.

Goto ‘Headers’ section in the response and take the value from x-ms-workflow-run-id, this Run id will play a major role to verify the logs on your transaction or process execution over the logic app workflow.

For each transaction or process execution, new run id will be generated and that will be logged in Azure portal level when your app is deployed into Azure Logic App service and using callback url from cloud service. If you’re using local host these run id’s history will be stored in local machine but not in the cloud.

![image info](./Images/25.png)

Now goto overview of your workflow again, check the logs which will be displayed with Run Id’s as show in below. In search window, paste your run id and click on highlighted run which is matched for your search.


![image info](./Images/26.png)

Log history will be visible as shown in below screenshot.

![image info](./Images/27.png)

![image info](./Images/28.png)



