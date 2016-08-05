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

## Add BusyIndicator

You can then add the assembly references to the respective projects as shown below

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfBusyIndicator.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfBusyIndicator.Android.dll<br/>android\Syncfusion.SfBusyIndicator.XForms.Android.dll<br/>android\Syncfusion.SfBusyIndicator.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfBusyIndicator.iOS.dll<br/>iOS-unified\Syncfusion.SfBusyIndicator.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfBusyIndicator.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfBusyIndicator.WP8.dll<br/>wp8\Syncfusion.SfBusyIndicator.XForms.dll<br/>wp8\Syncfusion.SfBusyIndicator.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfBusyIndicator.WP.dll<br/>wp81\Syncfusion.SfBusyIndicator.XForms.dll<br/>wp81\Syncfusion.SfBusyIndicator.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfBusyIndicator.WinRT.dll<br/>winrt\Syncfusion.SfBusyIndicator.XForms.dll<br/>winrt\Syncfusion.SfBusyIndicator.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfBusyIndicator.UWP.dll<br/>uwp\Syncfusion.SfBusyIndicator.XForms.dll<br/>uwp\Syncfusion.SfBusyIndicator.XForms.UWP.dll</td>
</tr>
</table>

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

SfBusyIndicator provides 10 predefined animation types like Ball, Battery, Globe and so on. User can select any one of the animation types using `AnimationType`property.

Following example depicts the battery type animation for SfBusyIndicator. 

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