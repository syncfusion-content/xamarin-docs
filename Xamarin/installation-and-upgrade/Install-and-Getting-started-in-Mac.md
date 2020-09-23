---
layout: post
title: Install and Getting Started Syncfusion component in Mac.
description: The following section will explain about the Overview and Installation process of Xamarin application in Visual Studio for Mac.
platform: Xamarin
control: Syncfusion Controls
documentation: ug
---

# Overview of Syncfusion components Installation in Mac

The Syncfusion Essential Studio allows you to create the Xamarin application in Visual Studio for Mac with the Syncfusion components.

## Create a new project

To create a Syncfusion Xamarin application by adding the required Syncfusion NuGet based on the control chosen.

![Project Creation](Images/project-creation.png)

In Visual Studio MAC, Go to File-> New Project

## Mac Build and Installation

The following procedure illustrates how to install Xamarin Mac installer.

1.Double-click the Syncfusion Xamarin Mac Installer(.pkg) file. The Installer Wizard opens. Click Continue.

![continue](Images/continue.JPG)

2.Software License Agreement window opens. Click Continue.

![License Agreement](Images/license-agreement.JPG)

3.Confirmation window will be displayed for the License Agreement. Click Agree.

![License Confirmation](Images/license-confirmation.JPG)

> Note

unlock key is not required for installing the Mac installer. Syncfusion Mac installer can be used for developing purposes without registering the Unlock key.

4.Destination Select windows opens. Click Continue.

![Destination](Images/destination.JPG)

5.Installation Type window opens. Click Install.

![Install Location](Images/install-location.JPG)

6.Authentication window opens. Provide the password and click Install Software.

![Install Software](Images/install-software.PNG)

7.Installation will be started in your machine.

![Installation Progress](Images/installation-progress.JPG)


8.Completed screen will be displayed once the installation is finished. Click Close to exit the installation wizard.

![Installation Completed](Images/installation-completed.JPG)

By default, Mac installer will install the files in following location.

Location: {Documents}\Syncfusion\ {version}\ {platform}

![Default Location](Images/default-location.PNG)

### Explore the libraries package

You can find the Syncfusion libraries, samples and NuGet from the installed location in Mac.
{Essential Studio installed location}\Syncfusion\Essential Studio{version}\Xamarin
•	“ Lib ” folder - eg, /Users/labuser/Documents/Syncfusion/16.2.0.41/Xamarin/lib
It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.
•	“Nuget” folder - eg, /Users/labuser/Documents/Syncfusion/16.2.0.41/nuget
It contains the above libraries as NuGet packages. The same NuGet packages also can be configured from online nuget.org.
•	“sample” folder - e.g., /Users/labuser/Documents/Syncfusion/16.2.0.41/sample
It contains the sample applications for our controls in Xamarin.iOS, Xamarin.Android, and Xamarin.Forms platforms in iOS, Android, and Forms folders, respectively.
The “Forms” directory includes,
•	Individual control sample folders: It contains the samples for individual controls such as SfChart, SfDataGrid, etc. Since they represent the individual controls, these samples are light-weighted. You can check the samples for your required controls alone faster with minimum deployment time.
•	“nuget” folder: It contains the compiled assemblies of the above samples as NuGet package. It is referred in the common sample browser as explained in the next step.
•	“SampleBrowser” folder: It contains common sample browser, which refers the individual control’s samples as NuGet package. Run this to see the demo samples of all the controls in single application.
•	It also contains showcase samples such as Patient Monitor, Server Monitor, and Invoice.
Add reference to the project
You can then add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS. You can find the dependencies for each control from this following [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies) link.


## Creating a New Xamarin Visual Studio MAC project for a Control 

1.Firstly, create a new project in Visual Studio MAC, using File-> New Project.

2.Choose Blank Forms App under Xamarin.Forms category under the Multi platform sub-heading.

![Blank Forms App](Images/blank-forms-app.PNG)

3.Enter the Application Name as required and click Next.

> Note

Make sure both Android and iOS target platforms are clicked and shared code is .NETStandard.

![Application Name](Images/application-name.PNG)

4.Choose the location where the created project needs to be stored for future reference and then Click Create.

![Select Location](Images/select-location.PNG)

5.Option 1: Right click solution -> Click Manage NuGet packages.

> Note

You can follow the [NuGet Packages](https://help.syncfusion.com/xamarin/visual-studio-integration/nuget-packages) to use the NuGet-Syncfusion Xamarin Controls/Components.


![Add Package](Images/addpackages.PNG)

Select the packages required to be added and click Add Packages
Now select all projects in the solution in the appeared dialog box and Click OK.

![Select Package](Images/select-package.PNG)

To successfully add the packages, Click Accept for the license acceptance for the added packages in solution

![Accept NuGet Package](Images/accept-nuget-package.PNG)

Now, your new project with required packages have been created successfully.
6.Option 2: 
You can add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS from the MAC build installed location in your machine. You can find the dependencies for each control from this link.
You can find the Syncfusion libraries, samples and NuGet from the installed location in Mac.

{Essential Studio installed location}\Syncfusion\Essential Studio{version}\Xamarin
•	“Lib ” folder - e.g., /Users/labuser/Documents/Syncfusion/16.2.0.41/Xamarin/lib
It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.


## Deploying a new control in a created project in MAC

1.Add the required code for control in PCL project.

For example, For SfAutocomplete, refer  [this](https://help.syncfusion.com/xamarin/autocomplete/getting-started#initializing-autocomplete) link.

Import the SfAutocomplete namespace in respective page and initialize the autocomplete using the code below.

![Autocomplete Code](Images/autocomplete-code.PNG)

refer [this](https://help.syncfusion.com/xamarin/autocomplete/populating-data) link to learn more about the options available in SfAutocomplete to populate data.

2.Additional step for iOS

We need to add Renderer for each control added in our project by adding Renderer in AppDelegate class in  iOS project

> Note

If you are adding the reference from toolbox, this step is not needed.

Here, Create an instance of `SfAutocompleteRenderer` in FinishedLaunching overridden method of an AppDelegate class in iOS project as shown below:

![Renderer Code](Images/renderer-code.PNG)

The complete Getting Started sample is available in [this](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoComplete312348434.zip) link.

3.Right click the iOS/ Android project-> Select Set As Startup Project in Debug/Release mode. Build and Run the project in any platform as desired.	

Thus, you can create Xamarin Visual Studio MAC project for any Syncfusion Xamarin control using the above guidelines.