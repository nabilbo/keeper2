Welcome

## How To Run This Sample



### Step 1: Clone or download this repository
From your shell or command line:  `git clone https://github.com/nabilbo/keeper.git`


### Step 2: Register the Outlook App with your Azure AD tenant

* 1.Sign in to the Azure management portal.
* 2.Click on Active Directory in the left hand nav.
* 3.Click the directory tenant where you wish to register the sample application.
* 4.Click the Applications tab.
* 5.In the drawer, click Add.
* 6.Click "Add an application my organization is developing".
* 7.Enter a friendly name for the application, for example `TheFilesKeeper-OutlookApp`, select "Web Application and/or Web API", and click next.
* 8.For the sign-on URL, enter the base URL for the sample, which is by default  `https://localhost:44305/` .
* 9.For the App ID URI, enter  `https://<your_tenant_name>/TheFilesKeeper-OutlookAapp`, replacing  <your_tenant_name>  with the name of your Azure AD tenant.
* 10.While still in the Azure portal, click the Configure tab of your application.
* 11.Find the Client ID value and copy it to the clipboard.
* 12. Download the Manifest file
* 13. Edit the Manifest File to Enable the OAuth2 implicit grant : search for the  oauth2AllowImplicitFlow  property. You will find that it is set to  false ; change it to  true  and save the file.
* 14. Upload the modified Manifest file.

All done! Before moving on to the next step, you need to find the Client ID of your application.

### Step 3 : Register the Web Api Sample with your Azure AD tenant

The same as Step 2 except for steps **7, 8, 9** and **13** :
* 7.Enter a friendly name for the application, for example `TheFilesKeeper-WebAPI`, select "Web Application and/or Web API", and click next.
* 8.For the sign-on URL, enter the base URL for the sample, which is by default  `https://localhost:44318/` .
* 9.For the App ID URI, enter  `https://<your_tenant_name>/TheFilesKeeper-WebAPI`, replacing  <your_tenant_name>  with the name of your Azure AD tenant.
* 13.Edit the Manifest File to Enable the OAuth2 implicit grant : search for the  oauth2AllowImplicitFlow  property. You will find that it is set to  false ; change it to  true  and save the file. You have also to declare the Web Api Sample as ressource for the Outlook App : Edit 'KnowClientApplications' section to add the Outlook App Client ID (Step 2.11). For example :   `"knownClientApplications": ["1caf8bf7-7a79-4e6e-9309-637372852ca6"],`



### Step 4: Configure the Visual Studio Solution.

* 1. Open the visual studio solution : `[VS_SOLUTION]\TheFilesKeeper.Outlook.App\TheFilesKeeper.Outlook.App.sln`
* 2. Edit the config.js `[VS_SOLUTION]\TheFilesKeeper.Outlook.App\TheFilesKeeper.Outlook.AppWeb\Common\config.js`
to run this sample, you only need to modify the lines flaged **"edit here"**


```javascript
/* The Files Keeper App configuration */

// STORAGE_PREFIX : prefix used to cache app data and to identify storage URI.
// if you change this value, don't forget to also change RegExValue on the Outlook app manifest.xml file.
var STORAGE_PREFIX = "keeper"; 

// OUTLOOK_APP_CLIENT_ID : Outlook App Client ID eg : 'f997c817-0695-4e70-87df-3e9e9e04649a' 
// this Client ID was created at the Step 2.11. 
OUTLOOK_APP_CLIENT_ID = '00000000-0000-0000-0000-000000000000';  /////////  => edit here

// BACKEND_URI eg : '"https://mytenant.onmicrosoft.com/TheFilesKeeper-WebAPI".
// this URI was created at the Step 3.9.
BACKEND_URI= "https://xxxxxxxxxxxxxxxxxxxxx.onmicrosoft.com/TheFilesKeeper-WebAPI";  /////////  => edit here

// BACKEND_CLIENT_ID : Web API Sample Client ID eg : 'f997c817-0695-4e70-87df-3e9e9e04649a' 
// This Client ID was created at the Step 3.11
BACKEND_CLIENT_ID = '00000000-0000-0000-0000-000000000000';  /////////  => edit here

//ENDPOINTS : Service api endpoints
var ENDPOINTS = {
    "https://localhost:44318/": BACKEND_URI,
};

//STS_ENDPOINT : Service api STS_ENDPOINT eg : https://query.microsoft.com/
var STS_ENDPOINT = "https://localhost:44318/api/azure/keystone"; 
```

3. Run the app **F5**. Thats All !
