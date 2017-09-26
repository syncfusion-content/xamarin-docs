---
layout: post
title: Download and Installation in Mac | Xamarin Forms | Syncfusion
description: Download and Installation in Mac
platform: xamarin
control: Download and Installation 
documentation: ug
---

# Mac

## Install NuGet from NuGet Package Manager

### Configuring and Installing Syncfusion NuGet Packages in Visual Studio

Syncfusion Xamarin NuGet packages are available [here](http://nuget.syncfusion.com/package/xamarin).

Following are the step by step instructions for configuring Syncfusion NuGet packages within Visual studio,

1. Right click on the Packages folder in the project and then select Add Packages…

   ![](images/img1.png)

2. Next, in the drop-down that appears in the left corner of Add Packages window, select Configure Sources.

   ![](images/img2.png)

3. Next, click on the Add button in the window that appears now. Enter the following details in the Add Package Source dialog.

    *	**Name** – enter the name (For Ex., Syncfusion Xamarin Packages)
    *	**Location** – enter the following URL - http://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin/

    Now click Add Source and then click OK.

    N> If you have already downloaded the NuGet package from Syncfusion website, enter the local path in the **Location** field.

    ![](images/img3.png)

4. Next, open Add Packages window by following step 1, then select Syncfusion Xamarin Packages (The package name specified in Step 3) as the source from the drop-down that appears at the top-left corner of the window.  You can now select from the list of Syncfusion’s components displayed in the window.

5. You need to do this in all the projects such as PCL, XForms.Droid, XForms.iOS.

    ![](images/img4.png)

### Updating a NuGet Package

Right click on the Packages folder in the individual projects, then select Update. This will update the NuGet package to the available latest version. You can double click Add Packages and choose the specific version for the package for which you want to update. You need to do this in all the projects such as PCL, XForms.Droid, XForms.iOS.

![](images/img5.png)

## Download directly from website

You can also download the complete Xamarin.Forms component from [here](https://www.syncfusion.com/downloads/latest-version).

**MAC Installer (pkg)**

The following procedure illustrates how to install the installer of Syncfusion Xamarin components in Mac.

1. Double-click the Syncfusion Essential Studio for Xamarin Setup file. The Self-Extractor wizard opens, click continue.
2. After reading the terms in Software License Agreement, click continue.
3. Click Agree in the dialog box that appears to continue the installation.
4. Select a destination to install the software and click continue.
5. Choose the installation location and samples installation.
6. To install it in the displayed default location, click Install.
7. Click Close. The NuGet and samples locations are launched automatically.

### Explore the libraries package

You can find the Syncfusion libraries, samples and NuGet when extracting the downloaded zip package or from the installed location in Mac.

{Essential studio installed location}\Syncfusion\Essential Studio\15.3.0.29\Xamarin

For example,

* **lib** - /Users/labuser/Documents/Syncfusion/15.3.0.29/Xamarin/lib
* **sample** - /Users/labuser/Documents/Syncfusion/15.3.0.29/sample
* **nuget** - /Users/labuser/Documents/Syncfusion/15.3.0.29/nuget

For configuring this NuGet, please refer [this](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac#configuring-and-installing-syncfusion-nuget-packages-in-visual-studio) section.

### Add reference to the project

You can then add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS. You can find the dependencies for each control from this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies).

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. For example, if we are using SfKanban, we need to call the Init method of SfKanbanRenderer as shown in this [KB article](https://www.syncfusion.com/kb/7171).

## Install NuGet from command line

### NuGet Configuration

1. Download the latest NuGet executable from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).

2. Open the downloaded executable location in command window and run the following command,

   mono nuget.exe Sources Add –Name [Source name] –Source [source location]

   Ex: mono nuget.exe Sources Add –Name “Syncfusion Xamarin Packages” -Source “http://nuget.syncfusion.com/nuget_xamarin/nuget/getsyncfusionpackages/xamarin/”

3. Once the Source gets added successfully the confirmation message will be shown like below.

    ![](images/img6.jpg)

### NuGet Installation

Once the NuGet source has been added, then install the NuGet package which is available in that source by using following command.

mono nuget.exe install [Package name]

For Ex: mono nuget.exe install “Syncfusion.Xamarin.Calculate” 

![](images/img7.jpg)

## Install from Xamarin Component Store

Refer to [this](https://developer.xamarin.com/guides/cross-platform/xamarin-studio/components_walkthrough/) article to know how to add a Xamarin Component Store component to Xamarin.Forms application.
