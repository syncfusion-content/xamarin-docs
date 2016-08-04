---
layout: post
title: Getting Started with Syncfusion RangeSlider control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion RangeSlider control for Xamarin.Forms platform
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfRangeSlider control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRangeSlider control.

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

pcl\Syncfusion.SfRangeSlider.XForms.dll

### Android 

android\Syncfusion.SfRangeSlider.Android.dll
android\Syncfusion.SfRangeSlider.XForms.Android.dll
android\Syncfusion.SfRangeSlider.XForms.dll
	
### iOS 

iOS-unified\Syncfusion.SfRangeSlider.iOS.dll
iOS-unified\Syncfusion.SfRangeSlider.XForms.iOS.dll
iOS-unified\Syncfusion.SfRangeSlider.XForms.dll

### Windows Phone

wp8\Syncfusion.SfInput.WP8.dll
wp8\Syncfusion.SfShared.WP8.dll
wp8\Syncfusion.SfRangeSlider.XForms.dll
wp8\Syncfusion.SfRangeSlider.XForms.WinPhone.dll

### Windows Phone 8.1

wp81\Syncfusion.SfInput.WP.dll
wp81\Syncfusion.SfShared.WP.dll
wp81\Syncfusion.SfRangeSlider.XForms.dll
wp81\Syncfusion.SfRangeSlider.XForms.WinPhone.dll

### UWP 

uwp\Syncfusion.SfInput.UWP.dll
uwp\Syncfusion.SfShared.UWP.dll
uwp\Syncfusion.SfRangeSlider.XForms.dll
uwp\Syncfusion.SfRangeSlider.XForms.UWP.dll

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the RangeSlider custom renderer as shown below. 

Create an instance of SfRangeSliderRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfRangeSliderRenderer();
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfRangeSliderRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfRangeSliderRenderer ();
}	

{% endhighlight %}

{% endtabs %}

## Add SfRangeSlider

The following steps helps to add a SfRangeSlider control through code.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:range="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"/>
	
{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfRangeSlider.XForms;

{% endhighlight %}

{% endtabs %}

* Now instantiate and add the SfRangeSlider control with a required optimal name.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeSlider"/>
	
{% endhighlight %}

{% highlight c# %}

	SfRangeSlider rangeSlider=new SfRangeSlider();
	this.Content = rangeSlider;
	
{% endhighlight %}

{% endtabs %}

## Set Range

SfRangeSlider provides option to set single thumb and double thumb. While setting the double thumb, each thumb value can be set using `RangeStart` and `RangeEnd` properties.

N> The `ShowRange` property is used to switch between a single thumb and double thumb. 

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" RangeEnd="20" RangeStart="4"  ShowRange="true"/>
	
{% endhighlight %}

{% highlight c# %}

SfRangeSlider rangeSlider=new SfRangeSlider();
	rangeSlider.RangeEnd=20; 
	rangeSlider.RangeStart=4;
	rangeSlider.ShowRange=true; 
	this.Content = rangeSlider;

{% endhighlight %}

{% endtabs %}

## Restricting Values

SfRangeSlider provides option to restrict slider range between minimum and maximum values. Following code explains how to set the range using `Minimum` and `Maximum` properties in the SfRangeSlider.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Minimum="0" Maximum="24"/>
	
{% endhighlight %}

{% highlight c# %}

SfRangeSlider rangeSlider=new SfRangeSlider();
	rangeSlider.RangeEnd=20; 
	rangeSlider.RangeStart=4;
	rangeSlider.ShowRange=true; 
	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=24; 
	this.Content = rangeSlider;
{% endhighlight %}

{% endtabs %}

## Adding Snapping Mode

The movement of the thumb can be varied in different ways. This is achieved by setting the `SnapsTo` property.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" SnapsTo="Ticks" StepFrequency="6"/>
	
{% endhighlight %}

{% highlight c# %}

SfRangeSlider rangeSlider=new SfRangeSlider();
	rangeSlider.RangeEnd=20; 
	rangeSlider.RangeStart=4;
	rangeSlider.ShowRange=true; 
	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=24; 
	rangeSlider.SnapsTo=SnapsTo.Ticks; 
	rangeSlider.StepFrequency=6;
	this.Content = rangeSlider;

{% endhighlight %}

{% endtabs %}  
                                    
