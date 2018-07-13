---
layout: post
title: Download and Installation in Windows | Xamarin Forms | Syncfusion
description: Download and Installation in Windows
platform: xamarin
control: Download and Installation
documentation: ug
---

# Windows


## Download directly from website

You can also download the complete Xamarin.Forms component from [here](https://www.syncfusion.com/downloads/latest-version). You may be asked to choose the windows installer or zip file to download.

**Windows Installer (exe)**

The following procedure illustrates how to install the installer of Syncfusion Xamarin components in Windows.

1. Double-click the Syncfusion Essential Studio for Xamarin Setup file. The Self-Extractor wizard opens and extracts the package automatically.
2. Enter User Name, Organization and Unlock Key in the corresponding text boxes provided.
3. Click Next.
4. After reading the terms, click “I accept the terms and conditions” check box.
5. Click Next and choose the installation location and samples installation.
6. To install it in the displayed default location, click Install.
7. Click Finish. The **NuGet and samples** locations are launched automatically.

### Explore the libraries package

You can find the Syncfusion libraries, samples and NuGet from the installed location in Windows.

{Essential Studio installed location}\Syncfusion\Essential Studio\15.3.0.29\Xamarin

* **"lib"** folder - e.g., C:\Program Files (x86)\Syncfusion\Essential Studio\15.4.0.17\Xamarin\lib

   It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.
   
* **"nuget"** folder - e.g., C:\Users\Public\Documents\Syncfusion\15.4.0.17\Xamarin\nuget

   It contains the above libraries as NuGet packages. The same NuGet packages also can be configured from online [nuget.org](https://api.nuget.org/v3/index.json).
   
* **"sample"** folder - e.g., C:\Users\Public\Documents\Syncfusion\15.4.0.17\Xamarin\sample

   It contains the sample applications for our controls in Xamarin.iOS, Xamarin.Android, and Xamarin.Forms platforms in iOS, Android, and Forms folders, respectively.

The "Forms" directory includes,

* Individual control sample folders: It contains the samples for individual controls such as SfChart, SfDataGrid, etc. Since they represent the individual controls, these samples are light-weighted. You can check the samples for your required controls alone faster with minimum deployment time.

* “nuget” folder: It contains the compiled assemblies of the above samples as NuGet package. It is referred in the common sample browser as explained in the next step.

* “SampleBrowser” folder: It contains common sample browser, which refers the individual control's samples as NuGet package. Run this to see the demo samples of all the controls in single application.

* It also contains showcase samples such as Patient Monitor, Server Monitor, and Invoice.

### Add reference to the project

You can then add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS and XForms.UWP. You can find the dependencies for each control from this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies).

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. For example, if we are using SfKanban, we need to call the Init method of SfKanbanRenderer as shown in this [KB article](https://www.syncfusion.com/kb/7171).

I> For UWP alone, one more additional step is required if the project is built in release mode with .NET Native tool chain enabled. For example, if we are using SfKanban, you can refer the [KB article](https://www.syncfusion.com/kb/7170) for more details.