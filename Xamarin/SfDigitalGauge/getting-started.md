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

Alternatively, if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies found in the installation folders, typically
{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib
Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder
{download location}\syncfusionessentialstudio-version\lib
You can then add the assembly references to the respective projects as shown below

**PCL Project**

pcl\Syncfusion.SfDigitalGauge.XForm.dll

**Android Project**

android\Syncfusion.SfDigitalGauge.Andriod.dll

android\Syncfusion.SfDigitalGauge.xForms.Andriod.dll

**IOS (Classic) Project**

ios\Syncfusion.SfDigitalGauge.iOS.dll

ios\Syncfusion.SfDigitalGauge.xForms.iOS.dll

ios\Syncfusion.SfDigitalGauge.XForm.dll

**IOS (Unified) Project**

ios-unified\Syncfusion.SfDigitalGauge.iOS.dll

ios-unified\Syncfusion.SfDigitalGauge.xForms.iOS.dll

ios-unified\Syncfusion.SfDigitalGauge.XForm.dll

**Windows Phone Project**

wp8\Syncfusion.SfDigitalGauge.WP8.dll

wp8\Syncfusion.SfDigitalGauge.xForms.WinPhone.dll

## Add and Configure the DigitalGauge

* Adding reference to digitalGauge.

{% highlight c# %}

	using Syncfusion.SfDigitalGauge.XForms;

{% endhighlight %}

* Create an instance of SfDigitalGauge.

{% highlight c# %}

	SfDigitalGauge sfDigitalGauge=new SfDigitalGauge();
	SetContentView(countryAutoComplete);

{% endhighlight %}

## Configure the properties of DigitalGauge.

{% highlight c# %}

	SfDigitalGauge sfDigitalGauge = new SfDigitalGauge ();
	sfDigitalGauge.Value =  DateTime.Now.ToString ("HH mm ss");;
	sfDigitalGauge.CharacterHeight = 50;
	sfDigitalGauge.CharacterWidth= 25;
	sfDigitalGauge.SegmentStrokeWidth = 3;
	sfDigitalGauge.CharacterType = CharacterType.SegmentSeven;
	sfDigitalGauge.DimmedSegmentAlpha = 30;
	sfDigitalGauge.BackgroundColor = Color.FromRgb (235, 235, 235);
	sfDigitalGauge.CharacterStrokeColor = Color.FromRgb (20,108,237);
	sfDigitalGauge.DimmedSegmentColor = Color.FromRgb (20,108,237);

{% endhighlight %}


