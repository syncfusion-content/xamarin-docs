---
layout: post
title: Getting Started with Xamarin Busy Indicator Control | Syncfusion
description: Learn how to get started with the Syncfusion Xamarin Busy Indicator (SfBusyIndicator) control, including its features and setup.
platform: Xamarin
control: SfBusyIndicator
documentation: ug
---

# Getting Started with Xamarin Busy Indicator (SfBusyIndicator)

## Introduction

This guide outlines how to configure and integrate the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) in real-time applications, highlighting customization options available within the control.
## Assembly Deployment

After installing [Essential Studio® for Xamarin](https://www.syncfusion.com/downloads/xamarin), locate the required assemblies in the installation directory under {Syncfusion Essential Studio Installed location} \Essential Studio\\{Version #}\Xamarin\lib.

Example: `C:\Program Files (x86)\Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib`

N> On a Mac, assemblies can be found in the unzipped package location: Documents/Syncfusion/{Version #}/Xamarin/lib.

## Adding SfBusyIndicator Reference

The [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) reference can be added using the following methods:

**Method 1: NuGet Package Manager**
Syncfusion Xamarin components are available on [nuget.org](https://www.nuget.org/). To add SfBusyIndicator, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfBusyIndicator](https://www.nuget.org/packages/Syncfusion.Xamarin.SfBusyIndicator), and install it.

![Adding SfBusyIndicator reference](images/Adding SfBusyIndicator reference.png)

N> Ensure that the same version of the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) NuGet package is installed across all projects.

**Method 2: Xamarin Toolbox**
The Syncfusion Xamarin Toolbox allows you to drag the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) control directly onto your XAML page. It will automatically install the required NuGet packages and add the necessary namespace. Refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox) for installation details.

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfBusyIndicator assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfBusyIndicator.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfBusyIndicator.Android.dll<br/>Syncfusion.SfBusyIndicator.XForms.Android.dll<br/>Syncfusion.SfBusyIndicator.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfBusyIndicator.iOS.dll<br/>Syncfusion.SfBusyIndicator.XForms.iOS.dll<br/>Syncfusion.SfBusyIndicator.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfBusyIndicator.UWP.dll<br/>Syncfusion.SfBusyIndicator.XForms.UWP.dll<br/>Syncfusion.SfBusyIndicator.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](hhttps://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the SfBusyIndicator on each platform

To use [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) inside an application, each platform application must initialize the SfBusyIndicator renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and UWP

The Android and UWP launches the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) in iOS, need to create an instance of SfBusyIndicatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
	global::Xamarin.Forms.Forms.Init();

	new SfBusyIndicatorRenderer();

	LoadApplication(new App());

	return base.FinishedLaunching(app, options);
}

{% endhighlight %}

{% endtabs %}

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) assemblies in `App.xaml.cs` in UWP project as like in below code snippet.

{% tabs %}

{% highlight C# %}

// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
…

	rootFrame.NavigationFailed += OnNavigationFailed;
		
	// you'll need to add `using System.Reflection;`
	List<Assembly> assembliesToInclude = new List<Assembly>();

	//Now, add all the assemblies your app uses
	assembliesToInclude.Add(typeof(SfBusyIndicatorRenderer).GetTypeInfo().Assembly);

	// replaces Xamarin.Forms.Forms.Init(e);        
	Xamarin.Forms.Forms.Init(e, assembliesToInclude);
		
…     
}
{% endhighlight %}

{% endtabs %}

## Create a Simple SfBusyIndicator 

The [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	
{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfBusyIndicator.XForms; 

{% endhighlight %}

{% endtabs %}

* Now add the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <busyindicator:SfBusyIndicator x:Name="busyindicator" />
    </ContentPage.Content>
</ContentPage>
   
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfBusyIndicator busyIndicator = new SfBusyIndicator();
            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Setting Animation Type

[`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) provides 15 predefined animation types like [`Ball`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Ball),[`Battery`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Battery), [`Globe`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Globe) and so on. User can select any one of the animation types using [`AnimationType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_AnimationType) property.

Following example depicts the battery type animation for [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html). 

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <busyindicator:SfBusyIndicator x:Name="busyindicator" 
                                       AnimationType="Battery" 
                                       ViewBoxWidth = "150" 
                                       ViewBoxHeight="150" 
                                       TextColor="Maroon" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfBusyIndicator busyIndicator = new SfBusyIndicator()
            {
                AnimationType = AnimationTypes.Battery,
                ViewBoxHeight = 150,
                ViewBoxWidth = 150,
                TextColor = Color.Maroon
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## EnableAnimation

[`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) provides options to enable or disable animation of the Busy Indicator. Animation can be enabled or disabled using the [`EnableAnimation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_EnableAnimationProperty) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <busyindicator:SfBusyIndicator x:Name="busyindicator" 
                                       AnimationType="Battery" 
                                       ViewBoxWidth = "150" 
                                       ViewBoxHeight="150"
                                       EnableAnimation="True"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfBusyIndicator busyIndicator = new SfBusyIndicator()
            {
                AnimationType = AnimationTypes.Ball,
                ViewBoxHeight = 150,
                ViewBoxWidth = 150,
                EnableAnimation = true
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![OverView image for BusyIndicator](images/Busyindicator.png)

You can find the complete getting started sample from this [link.](https://github.com/SyncfusionExamples/xamarin.forms-busyindicator)