---

layout: post
title: Getting Started with Syncfusion Rating control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion Rating control for Xamarin.Forms platform.
platform: Xamarin
control: Rating
documentation: ug

---

# Getting Started

This section explains you the steps to configure a rating control in a real-time scenario and also provides a walk-through on some of the customization features available in Rating control.

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
<td>pcl\Syncfusion.SfRating.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfRating.Android.dll<br/>android\Syncfusion.SfRating.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Classic)</td>
<td>ios\Syncfusion.SfRating.iOS.dll<br/>ios\Syncfusion.SfRating.XForms.iOS.dll<br/>ios\Syncfusion.SfRating.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfRating.iOS.dll<br/>ios-unified\Syncfusion.SfRating.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfRating.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfRating.XForms.dll<br/>wp8\Syncfusion.SfRating.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfRating.XForms.dll<br/>wp81\Syncfusion.SfRating.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfRating.XForms.dll<br/>winrt\Syncfusion.SfRating.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfRating.UWP.dll<br/>uwp\Syncfusion.SfRating.XForms.dll<br/>uwp\Syncfusion.SfRating.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the rating custom renderer as shown below. 

Create an instance of SfRatingRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 

{% highlight C# %}

public MainPage()

{

    new SfRatingRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfRatingRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfRatingRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the Rating

The Rating control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a Rating and configure its elements,

* Adding reference to rating.

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfRating.XForms;

{% endhighlight %}

{% highlight xaml %}

	xmlns:rating="clr-namespace:Syncfusion.SfRating.XForms;assembly=Syncfusion.SfRating.XForms"

{% endhighlight %}

{% endtabs %}

* Create an instance for rating control.

{% tabs %}

{% highlight C# %}

	SfRating rating = new SfRating(); 

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating />
	
{% endhighlight %}

{% endtabs %}


## Setting Value

* The `Value` property sets the display value of the rating. 

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

![](images/standard.jpg)








