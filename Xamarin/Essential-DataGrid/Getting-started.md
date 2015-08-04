---
layout: post
title: Getting-started
description: getting started
platform: xamarin
control: Control Name undefined
documentation: ug
---

### Getting started

This section provides a quick overview for working with Essential DataGridfor Xamarin.Android, Xamarin.Forms and Xamarin.iOS. After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\13.2.0.29\lib

![http://help.syncfusion.com/ug/android/ImagesExt/image19_8.png](Getting-started_images/Getting-started_img1.png)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

Essential DataGrid for Android

This topic describes about the assembly that is required in your Android application, when you use SfDataGrid.

Add the following assemblies to your Android project.

Syncfusion.Linq.Android.dll

Syncfusion.SfDataGrid.Android.dll

Syncfusion.GridCommon.Portable.dll



Essential DataGrid for iOS

This topic describes about the assembly that is required in your iOS application, when you use SfDataGrid.

Add the following assemblies to your iOS project.

Syncfusion.Linq.iOS.dll

Syncfusion.SfDataGrid.iOS.dll

Syncfusion.GridCommon.Portable.dll



Essential DataGrid for Xamarin.Forms

This topic describes the assembly required in your Forms application when you use the SfDataGrid.

Add the following assemblies to the respective projects as follows:

PCL project:

pcl\Syncfusion.Data.Portable.dll

pcl\Syncfusion.GridCommon.Portable.dll

pcl\Syncfusion.SfDataGrid.XForms.dll

Android project:

android\Syncfusion.SfDataGrid.XForms.Android.dll

iOS project:

pcl\Syncfusion.GridCommon.Portable.dll

ios\Syncfusion.SfDataGrid.XForms.iOS.dll

WindowsPhone project:

wp8\Syncfusion.SfDataGrid.XForms.WinPhone.dll

Currently, an additional step is required for Windows Phone and iOS projects. You need to initialize the DataGrid renderer. Call the SfDataGridRenderer.Init() in the MainPage constructor of the Windows Phone project as follows.

{% highlight c# %}

public MainPage()

{

    …
    SfDataGridRenderer.Init();

    …

}



{% endhighlight %}

Call the SfDataGridRenderer.Init() in the FinishedLaunching overridden method of the AppDelegate class in the iOS Project as follows.

{% highlight c# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    …
    SfDataGridRenderer.Init();

    …

}



{% endhighlight %}



