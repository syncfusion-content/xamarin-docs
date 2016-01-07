---

layout: post
title: Getting Started with Syncfusion Rating control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion Rating control for Xamarin.Forms platform.
platform: Xamarin.Forms
control: Rating
documentation: ug

---



# Getting Started

This section explains you the steps to configure a rating control in a real-time scenario and also provides a walk-through on some of the customization features available in Rating control.

## Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

PCL Project

pcl\Syncfusion.SfRating.XForm.dll

Android Project

android\Syncfusion. SfRating.Andriod.dll

android\Syncfusion. SfRating.xForms.Andriod.dll

IOS (Classic) Project

iOS\Syncfusion. SfRating.iOS.dll

iOS\Syncfusion. SfRating.xForms.iOS.dll

iOS\Syncfusion. SfRating.XForm.dll

IOS (Unified) Project

iOS-unified\Syncfusion.SfRating.iOS.dll

iOS-unified\Syncfusion.SfRating.xForms.iOS.dll

iOS-unified\Syncfusion.SfRating.XForm.dll

Windows Phone Project

wp8\Syncfusion.SfRating.WP8.dll

wp8\Syncfusion.SfRating.xForms.WinPhone.dll


## Add and Configure the Rating

The Rating control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a Rating and configure its elements,

* Create an instance for rating control.

{% highlight C# %}

	SfRating sfRating = new SfRating(); 

{% endhighlight %}

* Configure the properties of Rating.

{% highlight C# %}

	sfRating.ItemCount=5;

	sfRating.Precision=Precision.Standard;

	sfRating.ToolTipPlacement=ToolTipPlacement.None;

	sfRating.ItemSize=70;

{% endhighlight %}

![](images/gettingstarted.png)

## Setting Value

* The `Value` property sets the display value of the rating. 

N> By default, property value is 0.

{% highlight C# %}

    sfRating.Value=3;

{% endhighlight %}

## Precision

* To enable full, half and exact values of rating, set the `Precision` property.

{% highlight C#%}

    sfRating.Precision = Precision.Standard;

{% endhighlight%}

![](images/standard.jpg)








