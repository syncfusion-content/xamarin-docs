---
layout: post
title: Getting Started with TreeView for Xamarin.Forms | Syncfusion
description: User guide explains needed references, adding control to app, binding data and etc with demo app. 
platform: xamarin
control: SfTreeView
documentation: ug
---

# Getting Started

This section provides a quick overview for getting started with the SfTreeView for Xamarin.Forms. Walk through the entire process of creating an app with SfTreeView.

## Assembly Deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the {Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib installation folder.

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Refer [control dependencies](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sftreeview) section to get the list of assemblies or NuGet package needs to be added as reference to use the SfTreeView control in any application.

N> Assemblies can be found in an unzipped package location in Mac.

### Adding TreeView Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfTreeView to your project, open the NuGet package manager in Visual Studio, and search for [syncfusion.xamarin.SfTreeView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfTreeView/), and then install it. 

![](SfListView_images/SfListView_AddListView.png)

To know more about obtaining our components, refer to these links: [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). Also, if you prefer to manually refer the assemblies instead of NuGet, refer to this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sftreeview) to know about the dependent assemblies for SfTreeView. 

I> After adding the reference, an additionally need to initialize the renderer for [iOS](https://help.syncfusion.com/xamarin/treeview/getting-started#ios) and [UWP](https://help.syncfusion.com/xamarin/treeview/getting-started#universal-windows-platform-uwp) projects.  

I> For UWP alone, one more additional step is required if the project is built in release mode with .NET Native tool chain enabled. You can refer to the [KB article](https://www.syncfusion.com/kb/8476/how-to-overcome-the-crash-system-reflection-missingmetadataexception-when-usedotnetnativetoolchain-is) for more details.

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the SfTreeView on Each Platform

To use this control inside an application, each platform application must initialize the SfTreeView renderer. This initialization step varies from platform to platform, and is discussed in the following sections:

### Android

The Android launches the SfTreeView without any initialization, and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the SfTreeView in iOS, call the `SfTreeViewRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization, and before the LoadApplication is called as demonstrated in the following code example:

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    SfTreeViewRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

### Universal Windows Platform (UWP)

To launch the SfTreeView in UWP, call the `SfTreeViewRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called as demonstrated in the following code example:

{% tabs %}
{% highlight c# %}
public MainPage()
{
    …
    SfTreeViewRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

### ReleaseMode Issue in UWP Platform

The known Framework issue in UWP platform is the custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfTreeView assemblies in `App.xaml.cs` in UWP project as in the following code snippet:

{% tabs %}
{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    …

    rootFrame.NavigationFailed += OnNavigationFailed;
        
    // you'll need to add `using System.Reflection;`
    List<Assembly> assembliesToInclude = new List<Assembly>();

    //Now, add all the assemblies your app uses
    assembliesToInclude.Add(typeof(SfTreeViewRenderer).GetTypeInfo().Assembly);

    // replaces Xamarin.Forms.Forms.Init(e);        
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        
    …     
}
{% endhighlight %}
{% endtabs %}