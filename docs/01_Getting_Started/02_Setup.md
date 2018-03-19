## **Exercise 0:** Before the workshop

**Duration:** 45 mins

**Synopsis:** In this exercise, you will set up your environment for use in the rest of the hands-on lab. 

_**You should follow all the steps provided in this section to prepare your environment before attending the hands-on lab.**_

### **Task 1:** Deploy HDInsight cluster, Azure ML, and Storage Accounts to Azure

1. Click the **Deploy to Azure** link below, and you will be taken to the Azure portal, and presented with a form for a new custom deployment (which uses an Azure Resource Management (ARM) template from a GitHub repository). You will be presented with a blade to provide some custom parameters as show in the screenshot below.

    [Deploy to Azure](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FZoinerTejada%2Fmcw-big-data-and-visualization%2Fmaster%2FTemplates%2FTemplate-BigDataLab.json)

2.	In the Custom deployment blade that appears, enter the following values:

    * Subscription: Select your subscription

    * Resource group: Use and existing Resource group, or create a new one by entering a unique name, such as “bigdatalab-[your intials or first name]”.

    * Location: Select a location for the Resource group. Recommend using East US, East US 2, West Central US, or West US 2, as some resources, such as Data Factory, are only available in those regions.

    * App name: Enter a unique name, such as your initials or first name. This value must be between 3 and 10 characters long, and should not contain any special characters. Note the name, as you will need to use it in your Lab VM deployment in Task 3 as well.

    * Cluster Login User Name: Enter a name, or accept the default. Note all references to this in the lab use the default user name, demouser, so if you change it, please note it for future reference throughout the lab.

    * Cluster Login Password: Enter a password, or accept the default. Note all references to this in the lab use the default password, **Password.1!!**, so if you change it, please note it for future reference throughout the lab.

    * Check the box to agree to the terms.

    * Select Purchase.

    <img src="../images/select_purchase_custom_deployment.jpg" class="block"/>

3.	The deployment will take about 15 minutes to complete. 
4.	Wait for the deployment to complete before attempting to deploy the Lab Virtual Machine in Task 3, as it depends on the Virtual Network created by this deployment. In the meantime, you can move on to the next task, Task 2, while this deployment is ongoing.


### **Task 2:** Register for a trial API account at WeatherUnderground.com

To retrieve the 10-day hourly weather forecast, you will use an API from WeatherUnderground.com. There is a free developer version that provides you access to the API you need for this hands-on lab.

1.	Navigate to http://www.wunderground.com/weather/api/.

2.	Select Explore My Options.

    <img src="../images/wu_explore_options.jpg" class="block"/>

3.	On the Get Your API Key page, select **Anvil Plan**. 

    <img src="../images/wu_select_anvil_plan.jpg" class="block"/>

4.	Scroll down until you see the area titled How much will you use our service? Ensure **Developer** is selected.

    <img src="../images/wu_select_developer.jpg" class="block"/>

5.	Select **Purchase Key**.

    <img src="../images/wu_purchase_key.jpg" class="block"/>

6.	Complete the Create an Account form by providing your email address and a password, and agreeing to the terms. 

7.	Select Sign up for free.

    <img src="../images/wu_sign_up_free.jpg" class="block"/>

8.	In a few moments you should receive a confirmation email at the email address you provided. Select the **Validate Your Email** link found within the email.

    <img src="../images/wu_validate_email.jpg" class="block"/>

9.	Once you have validated your email, go back to the Get Your API Key page, re-select Anvil and select Purchase Key.

10.	Complete the brief contact form. When answering where will the API be used, select **Website**. For Will the API be used for commercial use, select **No**. Select **Purchase Key**.

    <img src="../images/wu_select_purchase_key.jpg" class="block"/>

11. You should be taken to a page that displays your key, similar to the following:

    <img src="../images/wu_display_key.jpg" class="block"/>

12.	Take note of your API Key. It is available from the text box labeled **Key ID**.

13.	To verify that your API Key is working, **modify the following URL** to include your API Key: **http://api.wunderground.com/api/<YOURAPIKEY>/hourly10day/q/SEATAC.json**.

14.	Open your modified link in a browser, you should get a JSON result showing the 10-day, hourly weather forecast for the Seattle-Tacoma International Airport

    <img src="../images/wu_test_api_key.jpg" class="block"/>

### **Task 3:** Deploy Lab Virtual Machine (Lab VM) to Azure

1. Click the **Deploy to Azure** link below, and you will be taken to the Azure portal, and presented with a form for a new custom deployment (which uses an ARM template from a GitHub repository). You will be presented with a blade to provide some custom parameters as show in the screenshot below. 

    [Deploy to Azure](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FZoinerTejada%2Fmcw-big-data-and-visualization%2Fmaster%2FTemplates%2FTemplate-BigDataLabVM.json)

2.	In the Custom deployment blade that appears, enter the following values:
    *	Subscription: Select your subscription

    *	Resource group: Choose **Use Existing**, and select the same resource group you used when deploying your HDInsight cluster and Azure ML workspace, above.

    *	Location: The location should be automatically selected to be the same as your Resource Group.

    *	App name: **IMPORTANT:** You must enter the **same App name** you used in the deployment above in Task 1.

    *	VM User Name: Enter a name, or accept the default. Note all references to this in the lab use the default user name, **demouser**, so if you change it, please note it for future reference throughout the lab.

    *	VM Password: Enter a password, or accept the default. Note all references to this in the lab use the default password, **Password.1!!**, so if you change it, please not it for future reference throughout the lab.

    *	Check the box to agree to the terms.

    *	Select **Purchase**. 

    <img src="../images/select_purchase_custom_deployment_vm.jpg" class="block"/>

3.	The deployment will take about 10 minutes to complete.


### **Task 4:** Install Power BI Desktop on the Lab VM

1.	Connect to the Lab VM. (If you are already connected to your Lab VM, skip to Step 7.

2.	From the left side menu in the Azure portal, click on **Resource groups**, then enter your resource group name into the filter box, and select it from the list. 

    <img src="../images/install_pbi_select_resource_group.jpg" class="block"/>

3.	Next, select your lab virtual machine from the list.

    <img src="../images/install_pbi_select_lab_vm.jpg" class="block"/>

4. On your Lab VM blade, select Connect from the top menu.

    <img src="../images/install_pbi_connect_vm.jpg" class="block"/>

5.	Download and open the RDP file.

6.	Select **Connect**, and enter the following credentials (or the non-default credentials if you changed them):

*   User name: demouser
*	Password: Password.1!!

7.	In a web browser on the Lab VM navigate to the Power BI Desktop download page (https://powerbi.microsoft.com/en-us/desktop/). 

8.	Select the **Download Free** link in the middle of the page

    <img src="../images/install_pbi_download_free.jpg" class="block"/>

9.	Run the installer.
10.	Select Next on the welcome screen. 

    <img src="../images/install_pbi_welcome_screen.jpg" class="block"/>

11.	Accept the license agreement, and select **Next**. 

    <img src="../images/install_pbi_accept_license.jpg" class="block"/>

12.	Leave the default destination folder, and select **Next**. 

    <img src="../images/install_pbi_destination_folder.jpg" class="block"/>

13.	Make sure the **Create a desktop shortcut** box is checked, and select **Install**. 

    <img src="../images/install_pbi_select_install.jpg" class="block"/>

14.	**Uncheck** Launch Microsoft Power BI Desktop, and select **Finish**. 

    <img src="../images/install_pbi_finish.jpg" class="block"/>


### **Task 5:** Install an SSH client

In this task, you will download, and install the Git Bash SSH client. This will be used to interact with the HDInsight cluster.

1.	On your Lab VM, open a browser, and navigate to https://git-scm.com/downloads to download Git Bash. 

    <img src="../images/download_git_bash.jpg" class="block"/>

2.	Select the **Download 2.xx.x for Windows** button.

3.	Run the downloaded installer, selecting **Next** on each screen to accept the defaults.

4.	On the last screen, select **Install** to complete the installation.

    <img src="../images/install_git_bash.jpg" class="block"/>

5.	When the install is complete, **uncheck View Release Notes**, and select **Finish**.

    <img src="../images/install_git_bash_finish.jpg" class="block"/>

