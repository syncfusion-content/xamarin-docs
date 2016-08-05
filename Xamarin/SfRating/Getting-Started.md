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

## Add SfRating

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
<td>android\Syncfusion.SfRating.Android.dll<br/>android\Syncfusion.SfRating.XForms.Android.dll<br/>android\Syncfusion.SfRating.XForms.dll</td>
</tr>
<tr>
<td>iOS (Classic)</td>
<td>iOS\Syncfusion.SfRating.iOS.dll<br/>iOS\Syncfusion.SfRating.XForms.iOS.dll<br/>iOS\Syncfusion.SfRating.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfRating.iOS.dll<br/>iOS-unified\Syncfusion.SfRating.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfRating.XForms.dll</td>
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
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfRating.XForms.dll<br/>uwp\Syncfusion.SfRating.XForms.UWP.dll</td>
</tr>
</table>

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

The SfRating control is configured entirely in C# code or by using XAML markup. The following steps explains how to create a SfRating and configure its elements.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:rating="clr-namespace:Syncfusion.SfRating.XForms;assembly=Syncfusion.SfRating.XForms"/>

{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfRating.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfRating control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" />
	
{% endhighlight %}

{% highlight C# %}

	SfRating rating = new SfRating(); 

{% endhighlight %}

{% endtabs %}

## Set Number of Rating Items

Number of rating items which are to be displayed can be customized in SfRatingControl. User may wants to create the rating application with 5 items as follows.  

N> The default property value is 5.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ItemCount="5" />
	
{% endhighlight %}

{% highlight C# %}

	rating.ItemCount=5;

{% endhighlight %}

{% endtabs %}

## Set Value

Display value can be set in SfRating control which is selected among the items. The following example shows the display value of 3 with 5 rating items. 

N> By default, property value is 0.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" Value="3" />
	
{% endhighlight %}

{% highlight C# %}

    rating.Value=3;

{% endhighlight %}

{% endtabs %}

## Precision

SfRating control provides option to rate the items in full, half and exact value. This can be set through `Precision` property.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" Precision="Standard" />
	
{% endhighlight %}

{% highlight C# %}

    rating.Precision = Precision.Standard;

{% endhighlight%}

{% endtabs %}

![](images/gettingstarted.png)








