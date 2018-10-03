---
layout: post
title: Explore Libraries Package in Mac | Xamarin Forms | Syncfusion
description: Describes the steps about download and installation of Syncfusion Xamarin.Forms components in MAC machine. 
platform: xamarin
control: Explore Libraries Package 
documentation: ug
---

# Mac

## Explore the libraries package

You can find the Syncfusion libraries, samples and NuGet from the installed location in Mac.


* **"lib"** folder - e.g., /Users/labuser/Documents/Syncfusion/16.3.0.21/Xamarin/lib

   It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.

* **"nuget"** folder - e.g., /Users/labuser/Documents/Syncfusion/16.3.0.21/Xamarin/nuget

   It contains the above libraries as NuGet packages. The same NuGet packages also can be configured from online [nuget.org](https://api.nuget.org/v3/index.json).

* **"sample"** folder - e.g., /Users/labuser/Documents/Syncfusion/16.3.0.21/Xamarin/sample

   It contains the sample applications for our controls in Xamarin.iOS, Xamarin.Android, and Xamarin.Forms platforms in iOS, Android, and Forms folders, respectively.

The "Forms" directory includes,

* Demo samples for each control such as Charts, DataGrid, etc. All the samples can be deployed in Android, iOS, and UWP platforms. Additionally, Charts, DataGrid, and ListView samples can be deployed in macOS platform also.

* It also contains showcase samples such as Patient Monitor, Server Monitor, and Invoice.

### Add reference to the project

You can then add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS. You can find the dependencies for each control from this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies).

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. For example, if we are using SfKanban, we need to call the Init method of SfKanbanRenderer as shown in this [KB article](https://www.syncfusion.com/kb/7171).