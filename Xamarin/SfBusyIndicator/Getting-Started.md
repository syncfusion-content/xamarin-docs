---
layout: post
title: Getting Started for Syncfusion.Xamarin.Forms BusyIndicator
description: A quick tour to initial users on Syncfusion SfBusyIndicator control for Xamarin.Forms platform
platform: Xamarin
control: BusyIndicator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfBusyIndicator control in a real-time scenario and also provides a walk-through on some of the customization features available in SfBusyIndicator control.

## Add SfBusyIndicator reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfbusyindicator) link to know about the assemblies required for adding Busyindicator to your project.

## Launching the SfBusyIndicator on each platform

To use SfBusyIndicator inside an application, each platform application must initialize the SfBusyIndicator renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and  UWP

The Android and UWP launches the SfBusyIndicator without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

### iOS

To launch SfBusyIndicator in iOS, need to create an instance of SfBusyIndicatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.

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

The above problem can be resolved by initializing the SfBusyIndicator assemblies in `App.xaml.cs` in UWP project as like in below code snippet.

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

## Create a Simple SfBusyIndicator 

The SfBusyIndicator control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfBusyIndicator and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	
{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfBusyIndicator.XForms; 

{% endhighlight %}

{% endtabs %}

* Now add the SfBusyIndicator control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	x:Class="GettingStarted.BusyIndicatorPage">
<ContentPage.Content>
 <syncfusion:SfBusyIndicator x:Name="busyindicator" />	
</ContentPage.Content>
</ContentPage>
   
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
public partial class BusyIndicatorPage : ContentPage
{
	public BusyIndicatorPage()
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

SfBusyIndicator provides 15 predefined animation types like Ball, Battery, Globe and so on. User can select any one of the animation types using `AnimationType`property.

Following example depicts the battery type animation for SfBusyIndicator. 

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	x:Class="GettingStarted.BusyIndicatorPage">
<ContentPage.Content>
 <syncfusion:SfBusyIndicator x:Name="busyindicator" AnimationType="Battery" ViewBoxWidth = "150" ViewBoxHeight="150" TextColor="Maroon" />	
</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;
namespace GettingStarted
{
	public partial class BusyIndicatorPage : ContentPage
	{
		public BusyIndicatorPage()
		{
			InitializeComponent();

			SfBusyIndicator busyIndicator = new SfBusyIndicator();
			busyIndicator.AnimationType = AnimationTypes.Battery;
			busyIndicator.ViewBoxWidth = 150;
			busyIndicator.ViewBoxHeight = 150;
			busyIndicator.TextColor = Color.Maroon;
			this.Content = busyIndicator;
		}
	}
}

{% endhighlight %}

{% endtabs %}

![OverView image for BusyIndicator](images/Busyindicator.png)

You can find the complete getting started sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted232240292.zip)