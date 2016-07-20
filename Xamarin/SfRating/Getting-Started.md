---

layout: post
title: Getting Started with Syncfusion Rating control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion Rating control for Xamarin.Forms platform.
platform: Xamarin
control: Rating
documentation: ug

---

# Getting Started

This section explains you the steps to configure a SfRating control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRating control.

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

{% tabs %}

{% highlight PCL %}

pcl\Syncfusion.SfRating.XForms.dll

{% endhighlight %}

{% highlight Android %}

android\Syncfusion.SfRating.Android.dll
android\Syncfusion.SfRating.XForms.Android.dll
android\Syncfusion.SfRating.XForms.dll
	
{% endhighlight %}

{% highlight iOS %}

iOS-unified\Syncfusion.SfRating.iOS.dll
iOS-unified\Syncfusion.SfRating.XForms.iOS.dll
iOS-unified\Syncfusion.SfRating.XForms.dll

{% endhighlight %}


{% highlight Windows Phone %}

**Windows Phone 8**

wp8\Syncfusion.SfInput.WP8.dll
wp8\Syncfusion.SfShared.WP8.dll
wp8\Syncfusion.SfRating.XForms.dll
wp8\Syncfusion.SfRating.XForms.WinPhone.dll

**Windows Phone 8.1**

wp81\Syncfusion.SfInput.WP.dll
wp81\Syncfusion.SfShared.WP.dll
wp81\Syncfusion.SfRating.XForms.dll
wp81\Syncfusion.SfRating.XForms.WinPhone.dll

{% endhighlight %}

{% highlight WinRT %}

winrt\Syncfusion.SfInput.WinRT.dll
winrt\Syncfusion.SfShared.WinRT.dll
winrt\Syncfusion.SfRating.XForms.dll
winrt\Syncfusion.SfRating.XForms.WinRT.dll

{% endhighlight %}

{% highlight UWP %}

uwp\Syncfusion.SfInput.UWP.dll
uwp\Syncfusion.SfShared.UWP.dll
uwp\Syncfusion.SfRating.XForms.dll
uwp\Syncfusion.SfRating.XForms.UWP.dll

{% endhighlight %}

{% endtabs %}

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the rating custom renderer as shown below. 

Create an instance of SfRatingRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 
{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfRatingRenderer();
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfRatingRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfRatingRenderer ();
}
	

{% endhighlight %}

{% endtabs %}

## Add and Configure the SfRating

The SfRating control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfRating and configure its elements.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfRating.XForms;

{% endhighlight %}

{% highlight xaml %}

	<xmlns:rating="clr-namespace:Syncfusion.SfRating.XForms;assembly=Syncfusion.SfRating.XForms"/>

{% endhighlight %}

{% endtabs %}

* Now add the SfRating control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight C# %}

	SfRating rating = new SfRating(); 

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" />
	
{% endhighlight %}

{% endtabs %}


## Setting Value

* The `Value` property sets the display value of the SfRating. 

N> By default, property value is 0.

{% tabs %}

{% highlight C# %}

    rating.Value=3;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" Value="3" />
	
{% endhighlight %}

{% endtabs %}

## Precision

* To enable full, half and exact values of rating, set the `Precision` property.

{% tabs %}

{% highlight C# %}

    rating.Precision = Precision.Standard;

{% endhighlight%}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" Precision="Standard" />
	
{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)








