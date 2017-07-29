---
layout: post
title: Download and Installation | Xamarin Forms | Syncfusion
description: Download and Installation
platform: xamarin
control: Download and Installation
documentation: ug
---

# Download and Installation

## Install from Xamarin Component Store

Refer to [this](https://developer.xamarin.com/guides/cross-platform/xamarin-studio/components_walkthrough/) article to know how to add a Xamarin Component Store component to Xamarin.Forms application.

## Install Syncfusion’s NuGet package in Xamarin Studio/ Visual Studio for MAC

Following are the step by step instructions for configuring Syncfusion NuGet packages within Xamarin studio,

1. Click on the drop-down tool at the right corner of the Packages item in your project, then select Add Packages…

   ![](images/img1.png)

2. Next, in the drop-down that appears in the left corner of Add Packages window, select Configure Sources.

   ![](images/img2.png)

3. Next, click on the Add button in the window that appears now. Enter the following details in the Add Package Source dialog.

    *	**Name** – enter the name (For Ex., Syncfusion)
    *	**URL** – enter the following URL - http://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin/

    Now click Add Source and then click OK.

    N> If you have already downloaded the NuGet package from Syncfusion website, enter the local path in the **URL** field. 

    ![](images/img3.png)

4. Next, open Add Packages window by following step 1 and 2, then select Syncfusion (The package name specified in Step 3) as the source from the drop-down that appears at the top-left corner of the window.  You can now select from the list of Syncfusion’s components displayed in the window.

   ![](images/img4.png)

## Configuring Syncfusion NuGet Packages in Visual Studio 

Syncfusion Xamarin NuGet packages are available [here](http://nuget.syncfusion.com/package/xamarin).

### NuGet Configuration  

The steps to install the Syncfusion Xamarin NuGet Packages in Visual Studio are as follows,

1. **Syncfusion NuGet Manager** is allows you to **add** the Syncfusion NuGet sources (for available platforms) to NuGet Package Manager. Download the [Syncfusion NuGet Manager](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SyncfusionNugetManager-1610952973.zip) utility.
2. Extract zip file and run the SyncfusionNuGetManager.exe
3. Syncfusion NuGet Manager Window will be opened.
4. Select the platform **Xamarin** from **“Select platforms to add”** (Left side of the window) column and click **Add>>** button. Then click **Configure** button.

   ![](images/Syncfusion_NuGet_Manager_img1.jpg)

5. Once Syncfusion NuGet Manager added the Syncfusion NuGet sources, the changes will be reflected in package sources of your Visual Studio. 

   ![](images/Syncfusion_NuGet_Manager_img2.jpg)

**Note:** Get the more details about Syncfusion NuGet Manager utility from [here](https://help.syncfusion.com/extension/syncfusion-nuget-packages/syncfusion-nuget-manager).

#### NuGet Package Manager settings

The steps to configure the Syncfusion Xamarin NuGet Packages in Visual Studio are as follows,

1. In Visual Studio, navigate to `Tools | NuGet Package Manager | Package Manager Settings`, the options dialog will appear on the screen as shows below,

   ![](images/NuGetConfig1.jpeg)

2. Select `NuGet Package Manager | Package Sources` and click `Add` button to add the `Package Name` and `Package Source` of Syncfusion NuGet Packages.    

   **Name**: Name of the package that listed in available package sources  
   **Source**: Syncfusion Xamarin NuGet Package feed URL 
   [http://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin/](http://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin/)
    
   ![](images/NuGetConfig2.jpeg)

   N> The `Source` text box in the above image denotes the location of the NuGet packages and the `Name` section, allows you to provide a unique name for NuGet Packages Source.
   
I> Syncfusion other platforms NuGet packages feed links are available [here](http://nuget.syncfusion.com/)

### NuGet Installation

Syncfusion Xamarin NuGet can install once configured the package source. The NuGet installation steps as below,

1. Once configured the Package source with Syncfusion NuGet Packages, right click on project and choose `Manage NuGet Packages | Online | <Package Source Name>`.

   ![](images/NuGetConfig3.jpeg)

2. The NuGet Packages are listed which are available in package source location. Install the required packages to your application by clicking `Install` button.

   N> NuGet packages can be install directly through the **command line** (Package Manager Console). Further details click [here](http://help.syncfusion.com/extension/syncfusion-nuget-packages/nuget-install-and-configuration#install-from-package-manager-console).

### Updating a NuGet Package

Using the `Manage NuGet Packages` in Visual Studio, NuGet packages can be update.
 
1. Right click on Project and Navigate to the `Manage NuGet Packages` and click on the `Updates` tab to check for updates.

2. Select the `Updates -> <Syncfusion Package Source>`. Refer to the following screenshot for more information.

   ![](images/NuGetConfig4.jpeg)

3. If there is a new version of NuGet you will see it in the list of available updates.

4. Select NuGet Package in the list and click `Update`. When the update is complete, close and re-open all open instances of Visual Studio.

   N> By clicking `Update All` button, all NuGet packages are getting update. When the update is complete, close and re-open all open instances of Visual Studio.


## Configuring Syncfusion NuGet packages from command line in Linux/MAC

### NuGet Configuration

1.	Download the latest NuGet executable from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).  
 
2.	Open the downloaded executable location in command window and run the following command,

    mono nuget.exe Sources Add –Name [Source name] –Source [source location]

      Ex: mono nuget.exe Add –Name “Syncfusion Source” –Source “http://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin/"
                                                                                  
3.	Once the Source gets added successfully the confirmation message will be shown like below.

    For Linux OS :

    ![](images/NuGetConfig5.jpeg)

    For MAC OS :
     
    ![](images/NuGetConfig6.jpeg)
     
### NuGet Installation

Once the NuGet source has been added, then install the NuGet package which is available in that source by using following command.

mono nuget.exe install [Package name] 

For Ex: mono nuget.exe install “Syncfusion.Xamarin.Calculate" 
     
For Linux OS :

![](images/NuGetConfig7.jpeg)

For MAC OS :

![](images/NuGetConfig8.jpeg)


## Download directly from Website

You can also download the complete Xamarin.Forms component from [here](http://www.syncfusion.com/products/xamarin). You may be asked to choose the windows installer or zip file to download.

**Windows** **Installer** **(****exe****)**

The following procedure illustrates how to install the installer of Syncfusion Xamarin components in Windows.

1. Double-click the Syncfusion Essential Studio for Xamarin Setup file. The Self-Extractor wizard opens and extracts the package automatically.
2. Enter User Name, Organization and Unlock Key in the corresponding text boxes provided.
3. Click Next.
4. After reading the terms, click "I accept the terms and conditions" check box.
5. Click Next and choose the installation location and samples installation.
6. To install it in the displayed default location, click Install.
7. Click Finish. The library and samples locations are launched automatically.

## Exploring the package


You can find the following folders when extracting the downloaded zip package or from the installed location in Windows.

* **Lib** - Contains Syncfusion assemblies for Xamarin.Forms, Xamarin.Android and Xamarin.iOS.
* **Samples** - Contains demo samples for Xamarin.Forms, Xamarin.Android and Xamarin.iOS.

## Add reference to the project


You can then add the assembly references to the respective projects. The following is the location where you can locate assemblies for Chart control and you can find assemblies for the other controls also from the same location.

**PCL** **project**

pcl\Syncfusion.SfChart.XForms.dll

**Android** **project**

android\Syncfusion.SfChart.Android.dll

android\Syncfusion.SfChart.XForms.Android.dll

android\Syncfusion.SfChart.XForms.dll

**iOS****(****Classic****)** **project**

iOS\Syncfusion.SfChart.iOS.dll

iOS\Syncfusion.SfChart.XForms.iOS.dll

iOS\Syncfusion.SfChart.XForms.dll

**iOS****(****Unified****)** **project**

ios-unified\Syncfusion.SfChart.iOS.dll

ios-unified\Syncfusion.SfChart.XForms.iOS.dll

ios-unified\Syncfusion.SfChart.XForms.dll

**UWP** **project**

uwp\Syncfusion.SfChart.UWP.dll

uwp\Syncfusion.SfChart.XForms.UWP.dll

uwp\Syncfusion.SfChart.XForms.dll

After you have added assemblies to the respective projects, you have to follow an additional step for loading our components in UWP and iOS projects. 

The following is an example for Chart component. create an instance of the SfChartRenderer in MainPage constructor of the UWP project as follows.

{% highlight C# %}

public MainPage() 
{
     new SfChartRenderer();
     ...
}

{% endhighlight %}

Create an instance of SfChartRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options) 
{
   ... 
   new SfChartRenderer (); 
   ... 
}

{% endhighlight %}

N> If you do not add the above line, controls will not be loaded in UWP and iOS platforms, and it will look blank. 