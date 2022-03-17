---
layout: post
title: Install and Getting Started Syncfusion component in Mac.
description: The following section will explain about the Overview and Installation process of Xamarin application in Visual Studio for Mac.
platform: Xamarin
control: Syncfusion Controls
documentation: ug
---

# Syncfusion Xamarin Mac Installation

The Syncfusion Essential Studio allows you to create the Xamarin application in Visual Studio for Mac with the Syncfusion components.

## How to download Xamarin Mac installer?

1. Essential Studio Xamarin Mac installer can be downloaded from your account’s [download](https://help.syncfusion.com/common/essential-studio/download) section. You can download trial\licensed Mac installer based on your license.

2. In the downloads page, click the "Mac" button and download the required Essential Studio Xamarin Mac installer.

   ![Download Page](Mac-Installer_images/Mac_Download.png)  


## Steps to resolve the warning message in Catalina OS or later

   While running Essential Studio Xamarin Mac Installer on Catalina MacOS or later, the below alert will be displayed.

   ![Alert Image](Mac-Installer_images/Mac_Catalina_MacOS_Alert.png)  
     
   If you receive this alert, follow the below steps for the easiest solution.   

   1.	Right-click the downloaded pkg file.
   2.	Select the "Open With" option and choose "Installer (Default)".
   3.	Installer window will be opened.

## Step-by-Step Installation

The steps below show how to install the Essential Studio Xamarin Mac installer. 

1. Open Syncfusion Essential Studio Xamarin Mac Installer(.pkg) file. The Installer Wizard opens. Click Continue.

   ![continue](Images/continue.JPG)

2. The Software License Agreement wizard will appear. Click the Continue button.

   ![License Agreement](Images/license-agreement.JPG)

3. The License Agreement's Confirmation window will appear. If you have read the Software License Agreement, click **Agree**.

   ![License Confirmation](Images/license-confirmation.JPG)

   N> The Unlock key is not required to install the Mac installer. The Syncfusion Essential Studio Xamarin Mac installer can be used for development purposes without registering the Unlock key.

4. The Destination select wizard will appear. You can choose which disc to install the Syncfusion Essential Studio for Xamarin installer on here.

   ![Destination](Images/destination.JPG)

5. The Installation Type wizard will appear. Click Install to begin the standard installation of the Syncfusion Essential Studio Xamarin Mac installer.

   ![Install Location](Images/install-location.JPG)

6. The Authentication window will appear. To begin the installation, enter the Mac machine's password and click **Install Software**.

   ![Install Software](Images/install-software.PNG)

7. The installation process will begin on your machine. 

   ![Installation Progress](Images/installation-progress.JPG)


8. Once the installation is complete, the completed screen will be displayed. To exit the installation wizard, click Close. 

   ![Installation Completed](Images/installation-completed.JPG)

   By default, Mac installer will install the files in following location.

   Location: {Documents}\Syncfusion\ {version}\ {platform}

   ![Default Location](Images/default-location.PNG)
   
### Add reference to the project

You can then add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS. You can find the dependencies for each control from this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies).

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. For example, if we are using SfKanban, we need to call the Init method of SfKanbanRenderer as shown in this [KB article](https://www.syncfusion.com/kb/7171).

### Explore the libraries package

You can find the Syncfusion libraries, samples and NuGet from the installed location in Mac.

{Essential Studio installed location}\Syncfusion\Essential Studio{version}\Xamarin

* “ Lib ” folder - eg, /Users/labuser/Documents/Syncfusion/16.2.0.41/Xamarin/lib
It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.

* “Nuget” folder - eg, /Users/labuser/Documents/Syncfusion/16.2.0.41/nuget
It contains the above libraries as NuGet packages. The same NuGet packages also can be configured from online nuget.org.

* “sample” folder - e.g., /Users/labuser/Documents/Syncfusion/16.2.0.41/sample
It contains the sample applications for our controls in Xamarin.iOS, Xamarin.Android, and Xamarin.Forms platforms in iOS, Android, and Forms folders, respectively.

The **“Forms”** directory includes,

* **Individual control sample folders:** It contains the samples for individual controls such as SfChart, SfDataGrid, etc. Since they represent the individual controls, these samples are light-weighted. You can check the samples for your required controls alone faster with minimum deployment time.
* **“nuget” folder:** It contains the compiled assemblies of the above samples as NuGet package. It is referred in the common sample browser as explained in the next step.
* **“SampleBrowser” folder:** It contains common sample browser, which refers the individual control’s samples as NuGet package. Run this to see the demo samples of all the controls in single application.
* It also contains showcase samples such as Patient Monitor, Server Monitor, and Invoice.

### Add reference to the project

You can then add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS. You can find the dependencies for each control from [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies) link.


## Creating a New Xamarin Visual Studio MAC project for a Control 

1. Firstly, create a new project in Visual Studio MAC, using File-> New Project.

2. Choose Blank Forms App under Xamarin.Forms category under the Multi platform sub-heading.

   ![Blank Forms App](Images/blank-forms-app.PNG)

3. Enter the Application Name as required and click Next.

   N> Make sure both Android and iOS target platforms are clicked and shared code is .NETStandard.

   ![Application Name](Images/application-name.PNG)

4. Choose the location where the created project needs to be stored for future reference and then Click Create.

   ![Select Location](Images/select-location.PNG)

5. **Option 1:** Right click solution -> Click Manage NuGet packages.

   N> You can follow the [NuGet Packages](https://help.syncfusion.com/xamarin/visual-studio-integration/nuget-packages) to use the NuGet-Syncfusion Xamarin Controls/Components.


   ![Add Package](Images/addpackages.PNG)

   Select the packages required to be added and click Add Packages
   
   Now select all projects in the solution in the appeared dialog box and Click OK.

   ![Select Package](Images/select-package.PNG)

   To successfully add the packages, Click Accept for the license acceptance for the added packages in solution

   ![Accept NuGet Package](Images/accept-nuget-package.PNG)

   Now, your new project with required packages have been created successfully.

6. **Option 2:** 
   You can add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS from the MAC build installed location in your machine. You can find the dependencies for each control from this link.
   
   You can find the Syncfusion libraries, samples and NuGet from the installed location in Mac.

   {Essential Studio installed location}\Syncfusion\Essential Studio{version}\Xamarin

   “Lib ” folder - e.g., /Users/labuser/Documents/Syncfusion/16.2.0.41/Xamarin/lib

   It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.


## Deploying a new control in a created project in MAC

1. Add the required code for control in PCL project.

   For example, For SfAutocomplete, refer  [this](https://help.syncfusion.com/xamarin/autocomplete/getting-started#initializing-autocomplete) link.

   Import the SfAutocomplete namespace in respective page and initialize the autocomplete using the code below.

   ![Autocomplete Code](Images/autocomplete-code.PNG)

   refer [this](https://help.syncfusion.com/xamarin/autocomplete/populating-data) link to learn more about the options available in SfAutocomplete to populate data.

2. Additional step for iOS

   We need to add Renderer for each control added in our project by adding Renderer in AppDelegate class in  iOS project

   N> If you are adding the reference from toolbox, this step is not needed.

   Here, Create an instance of `SfAutocompleteRenderer` in FinishedLaunching overridden method of an AppDelegate class in iOS project as shown below:

   ![Renderer Code](Images/renderer-code.PNG)

   The complete Getting Started sample is available in [this](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoComplete312348434.zip) link.

3. Right click the iOS/ Android project-> Select Set As Startup Project in Debug/Release mode. Build and Run the project in any platform as desired.	

   Thus, you can create Xamarin Visual Studio MAC project for any Syncfusion Xamarin control using the above guidelines.