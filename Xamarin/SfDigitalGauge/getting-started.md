---
layout: post
title: Getting Started with Syncfusion DigitalGauge control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion digitalGauge control for Xamarin.Forms platform
platform: Xamarin.Forms
control: DigitalGauge
documentation: ug
---

# Getting Started

This section provides overview for working with Essential DigitalGauge for Xamarin.Forms. You can walk through the entire process of creating an DigitalGauge.

![](Getting-Started_images/DigitalGauge.png)

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
<td>pcl\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfGauge.Android.dll<br/>android\Syncfusion.SfGauge.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Classic)</td>
<td>ios\Syncfusion.SfGauge.iOS.dll<br/>ios\Syncfusion.SfGauge.XForms.iOS.dll<br/>ios\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfGauge.iOS.dll<br/>ios-unified\Syncfusion.SfGauge.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>WindowsPhone</td>
<td>wp8\Syncfusion.SfGauge.WP8.dll<br/>wp8\Syncfusion.SfGauge.XForms.dll<br/>wp8\Syncfusion.SfGauge.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WindowsPhone 8.1</td>
<td>wp81\Syncfusion.SfGauge.WP.dll<br/>wp81\Syncfusion.SfGauge.XForms.dll<br/>wp81\Syncfusion.SfGauge.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfGauge.WinRT.dll<br/>winrt\Syncfusion.SfGauge.XForms.dll<br/>winrt\Syncfusion.SfGauge.XForms.WinRT.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, WindowsPhone 8.1, WinRT and iOS projects. We need to create an instance of the digitalgauge custom renderer as shown below. 

Create an instance of SfDigitalGaugeRenderer in MainPage constructor of the Windows Phone , WindowsPhone 8.1 and WinRT project as shown 

{% highlight C# %}

public MainPage()

{

    new SfDigitalGaugeRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfDigitalGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfDigitalGaugeRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the DigitalGauge

The DigitalGauge control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a DigitalGauge and configure its elements,

* Create an instance for digitalgauge control.

{% highlight C# %}

	SfDigitalGauge sfdigitalgauge = new SfDigitalGauge(); 

{% endhighlight %}

* Configure the properties of DigitalGauge.

{% highlight c# %}

	SfDigitalGauge sfDigitalGauge = new SfDigitalGauge ();
	sfDigitalGauge.Value =  DateTime.Now.ToString ("HH mm ss");
	sfDigitalGauge.CharacterHeight = 50;
	sfDigitalGauge.CharacterWidth= 25;
	sfDigitalGauge.SegmentStrokeWidth = 3;
	sfDigitalGauge.CharacterType = CharacterType.SegmentSeven;
	sfDigitalGauge.DimmedSegmentAlpha = 30;
	sfDigitalGauge.BackgroundColor = Color.FromRgb (235, 235, 235);
	sfDigitalGauge.CharacterStrokeColor = Color.FromRgb (20,108,237);
	sfDigitalGauge.DimmedSegmentColor = Color.FromRgb (20,108,237);

{% endhighlight %}

## Setting Value

* The `Value` property sets the display value in the digitalgauge.

{% highlight C# %}

    sfDigitalGauge.Value =  DateTime.Now.ToString ("HH mm ss");

{% endhighlight %}