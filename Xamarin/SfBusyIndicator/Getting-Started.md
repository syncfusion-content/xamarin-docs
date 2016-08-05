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

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below


### PCL 
pcl\Syncfusion.SfBusyIndicator.XForms.dll

### Android 
android\Syncfusion.SfBusyIndicator.Android.dll
android\Syncfusion.SfBusyIndicator.XForms.Android.dll
android\Syncfusion.SfBusyIndicator.XForms.dll

### iOS 
iOS-unified\Syncfusion.SfBusyIndicator.iOS.dll
iOS-unified\Syncfusion.SfBusyIndicator.XForms.iOS.dll
iOS-unified\Syncfusion.SfBusyIndicator.XForms.dll

### Windows Phone
wp8\Syncfusion.SfBusyIndicator.WP8.dll
wp8\Syncfusion.SfBusyIndicator.XForms.dll
wp8\Syncfusion.SfBusyIndicator.XForms.WinPhone.dll

### Windows Phone 8.1
wp81\Syncfusion.SfBusyIndicator.WP.dll
wp81\Syncfusion.SfBusyIndicator.XForms.dll
wp81\Syncfusion.SfBusyIndicator.XForms.WinPhone.dll

### WinRT 
winrt\Syncfusion.SfBusyIndicator.WinRT.dll
winrt\Syncfusion.SfBusyIndicator.XForms.dll
winrt\Syncfusion.SfBusyIndicator.XForms.WinRT.dll

### UWP 
uwp\Syncfusion.SfBusyIndicator.UWP.dll
uwp\Syncfusion.SfBusyIndicator.XForms.dll
uwp\Syncfusion.SfBusyIndicator.XForms.UWP.dll

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the SfBusyIndicator custom renderer as shown below. 

Create an instance of SfBusyIndicatorRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfBusyIndicatorRenderer();
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfBusyIndicatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfBusyIndicatorRenderer ();
}	

{% endhighlight %}

{% endtabs %}

## Add BusyIndicator

The following steps helps to add a SfBusyIndicator control through code.

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

   	<xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"/>
	<ContentPage.Content>
		<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="Battery" />
	</ContentPage.Content>
	
{% endhighlight %}

{% highlight c# %}

    using Syncfusion.SfBusyIndicator.XForms;
	SfBusyIndicator busyindicator = new SfBusyIndicator();
	this.Content=busyindicator;
	
{% endhighlight %}

{% endtabs %}

## Setting Animation Type

SfBusyIndicator provides an attached property `AnimationType` that helps to set anyone of the 10 predefined animation types. 

{% tabs %}

{% highlight xaml %}

   	<xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"/>
	<ContentPage.Content>
		<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="Battery" ViewBoxWidth = "150" ViewBoxHeight="150" Color="Maroon"/>
	</ContentPage.Content>	
	
{% endhighlight %}

{% highlight c# %}

    using Syncfusion.SfBusyIndicator.XForms; 	
	SfBusyIndicator busyindicator = new SfBusyIndicator();
	this.Content=busyindicator;
	busyindicator.AnimationType = AnimationTypes.Battery;
        busyindicator.ViewBoxWidth = 150;
        busyindicator.ViewBoxHeight = 150;
        busyindicator.Color = Color.Maroon;


{% endhighlight %}

{% endtabs %}


![](images/Busyindicator.png)