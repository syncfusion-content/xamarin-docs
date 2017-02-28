---
layout: post
title: Getting Started with Syncfusion SfBusyIndicator control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion SfBusyIndicator control for Xamarin.Forms platform
platform: Xamarin
control: BusyIndicator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfBusyIndicator control in a real-time scenario and also provides a walk-through on some of the customization features available in SfBusyIndicator control.

## Add SfBusyIndicator reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfchart) link to know about the assemblies required for adding Busyindicator to your project.

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
    new SfBusyIndicatorRenderer ();
}	

{% endhighlight %}

{% endtabs %}

## Create a Simple SfBusyIndicator 

The SfBusyIndicator control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfBusyIndicator and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"/>
	
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
	x:Class="GettingStarted.CarouselControlPage">
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
public partial class CarouselControlPage : ContentPage
{
	public CarouselControlPage()
	{
		InitializeComponent();

		SfBusyIndicator busyindicator = new SfBusyIndicator();

		this.Content = busyindicator;
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
	x:Class="GettingStarted.CarouselControlPage">
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
	public partial class CarouselControlPage : ContentPage
	{
		public CarouselControlPage()
		{
			InitializeComponent();

			SfBusyIndicator busyindicator = new SfBusyIndicator();
			busyindicator.AnimationType = AnimationTypes.Battery;
			busyindicator.ViewBoxWidth = 150;
			busyindicator.ViewBoxHeight = 150;
			busyindicator.TextColor = Color.Maroon;
			this.Content = busyindicator;
		}
	}
}

{% endhighlight %}

{% endtabs %}


![](images/Busyindicator.png)