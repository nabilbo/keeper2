## TheFilesKeeper


## How To Run This Sample



### Step 1: Clone or download this repository
From your shell or command line:  git clone https://github.com/keeper


### Step 2: Register the Outlook App with your Azure Active Directory tenant

* 1.Sign in to the Azure management portal.
* 2.Click on Active Directory in the left hand nav.
* 3.Click the directory tenant where you wish to register the sample application.
* 4.Click the Applications tab.
* 5.In the drawer, click Add.
* 6.Click "Add an application my organization is developing".
* 7.Enter a friendly name for the application, for example "TheFilesKeeper-OutlookApp", select "Web Application and/or Web API", and click next.
* 8.For the sign-on URL, enter the base URL for the sample, which is by default  https://localhost:44305/ .
* 9.For the App ID URI, enter  https://<your_tenant_name>/TheFilesKeeper-OutlookAapp, replacing  <your_tenant_name>  with the name of your Azure AD tenant.
* 10.Edit 

All done! Before moving on to the next step, you need to find the Client ID of your application.
* 11.While still in the Azure portal, click the Configure tab of your application.
* 12.Find the Client ID value and copy it to the clipboard.


### Step 3 : Register the Web Api Sample with your Azure Active Directory tenant

The same as Step 2 for the beginin :
* 7.Enter a friendly name for the application, for example "TheFilesKeeper-WebAPI", select "Web Application and/or Web API", and click next.
* 8.For the sign-on URL, enter the base URL for the sample, which is by default  https://localhost:44318/ .
* 9.For the App ID URI, enter  https://<your_tenant_name>/TheFilesKeeper-WebAPI, replacing  <your_tenant_name>  with the name of your Azure AD tenant.
* 10.Edit 

All done! Before moving on to the next step, you need to find the Client ID of your application.
* 11.While still in the Azure portal, click the Configure tab of your application.
* 12.Find the Client ID value and copy it to the clipboard.


### Step 3: Enable the OAuth2 implicit grant for your application
By default, applications provisioned in Azure AD are not enabled to use the OAuth2 implicit grant. In order to run this sample, you need to explicitly opt in.

* 1.From the former steps, your browser should still be on the Azure management portal - and specifically, displaying the Configure tab of your application's entry.
* 2.Using the Manage Manifest button in the drawer, download the manifest file for the application and save it to disk.
* 3.Open the manifest file with a text editor. Search for the  oauth2AllowImplicitFlow  property. You will find that it is set to  false ; change it to  true  and save the file.
* 4.Using the Manage Manifest button, upload the updated manifest file. Save the configuration of the app.
