---
layout : post
title : Getting Started with Syncfusion Carousel control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion Carousel control for Xamarin.Forms platform.
platform : Xamarin
control : Carousel
documentation : ug
---

# Getting Started

This section explains you the steps to configure a Carousel control in a real-time scenario and also provides a walk-through on some of the customization features available in Carousel control.

![](images/gettingstarted.png)

## Referencing Essential Studio components in your solution

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
<td>pcl\Syncfusion.SfCarousel.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfCarousel.Android.dll<br/>android\Syncfusion.SfCarousel.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfCarousel.iOS.dll<br/>ios-unified\Syncfusion.SfCarousel.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfCarousel.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfCarousel.XForms.dll<br/>wp8\Syncfusion.SfCarousel.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfCarousel.XForms.dll<br/>wp81\Syncfusion.SfCarousel.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfCarousel.XForms.dll<br/>winrt\Syncfusion.SfCarousel.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfCarousel.UWP.dll<br/>uwp\Syncfusion.SfCarousel.XForms.dll<br/>uwp\Syncfusion.SfCarousel.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the carousel custom renderer as shown below. 

Create an instance of SfCarouselRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% highlight C# %}

public MainPage()

{

    new SfCarouselRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfCarouselRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfCarouselRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the Carousel

The Carousel control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a Carousel and configure its elements,

* Adding reference to carousel.

{% highlight C# %}

	using Com.Syncfusion.Carousel; 

{% endhighlight %}


* Create an instance for SfCarousel.

{% highlight C# %}

	SfCarousel sfCarousel=new SfCarousel();
	this.Content=sfCarousel;

{% endhighlight %}

## Setting Offset

Set the Offset property to specify the distance between the items in Carousel panel.

{% highlight C# %}

	SfCarousel sfCarousel = new SfCarousel();
	sfCarousel.SelectedIndex=2;
	sfCarousel.Offset=20;

{% endhighlight %}


## Setting Rotation Angle

Set the RotationAngle property to decide the angle in which items should be rotated.

{% highlight C# %}

	SfCarousel sfCarousel = new SfCarousel();
	sfCarousel.SelectedIndex=2;
	sfCarousel.Offset=20;
	SfCarousel.RotationAngle = 45;

{% endhighlight %}


