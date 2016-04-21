---
layout: post
title: Getting Started with Syncfusion RangeSlider control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion RangeSlider control for Xamarin.Forms platform
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Getting Started

This section explains you the steps to configure a RangeSlider control in a real-time scenario and also provides a walk-through on some of the customization features available in RangeSlider control.

![](images/RangeSlider.png)

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

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfRangeSlider.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfRangeSlider.Android.dll<br/>android\Syncfusion.SfRangeSlider.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfRangeSlider.iOS.dll<br/>ios-unified\Syncfusion.SfRangeSlider.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfRangeSlider.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfRangeSlider.XForms.dll<br/>wp8\Syncfusion.SfRangeSlider.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfRangeSlider.XForms.dll<br/>wp81\Syncfusion.SfRangeSlider.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfRangeSlider.UWP.dll<br/>uwp\Syncfusion.SfRangeSlider.XForms.dll<br/>uwp\Syncfusion.SfRangeSlider.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the RangeSlider custom renderer as shown below. 

Create an instance of SfRangeSliderRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 

{% highlight C# %}

public MainPage()

{

    new SfRangeSliderRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfRangeSliderRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfRangeSliderRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the RangeSlider

* Adding reference to RangeSlider.

{% highlight c# %}

	using Syncfusion.SfRangeSlider.XForms;

{% endhighlight %}

* Create an instance of SfRangeSlider.

{% highlight c# %}

	SfRangeSlider rangeSlider=new SfRangeSlider();
	this.Content = rangeSlider;
	
{% endhighlight %}

## Setting Range

The `RangeStart` and `RangeEnd` properties can be set to denote the start range and end range values while dual thumb is used. 

N> The `ShowRange` property is used to switch between a single thumb and double thumb. 

{% highlight c# %}

	rangeSlider.RangeEnd=20; 
	rangeSlider.RangeStart=4;
	rangeSlider.ShowRange=true; 

{% endhighlight %}

## Restricting Values

Set the minimum and maximum value for the slider by using the `Minimum` and `Maximum` properties in the RangeSlider.

{% highlight c# %}

	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=24; 

{% endhighlight %}

## Adding Snapping Mode

The movement of the thumb can be varied in different ways. This is achieved by setting the `SnapsTo` property.

{% highlight c# %}

	rangeSlider.SnapsTo=SnapsTo.Ticks; 
	rangeSlider.StepFrequency=6;

{% endhighlight %}







    
                                    
