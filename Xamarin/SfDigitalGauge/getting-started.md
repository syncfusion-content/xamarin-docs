---
layout: post
title: Getting Started with Syncfusion DigitalGauge control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion digitalGauge control for Xamarin.Forms platform
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfDigitalGauge control in a real-time scenario and also provides a walk-through on some of the customization features available in it.

## Add SfDigitalGauge

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
<td>android\Syncfusion.SfGauge.Android.dll<br/>android\Syncfusion.SfGauge.XForms.Android.dll<br/>android\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfGauge.iOS.dll<br/>iOS-unified\Syncfusion.SfGauge.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfGauge.XForms.dll<br/>wp8\Syncfusion.SfGauge.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfGauge.XForms.dll<br/>wp81\Syncfusion.SfGauge.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfGauge.XForms.dll<br/>winrt\Syncfusion.SfGauge.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfGauge.XForms.dll<br/>uwp\Syncfusion.SfGauge.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the DigitalGauge custom renderer as shown below. 

Create an instance of SfDigitalGaugeRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfDigitalGaugeRenderer();
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfDigitalGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfDigitalGaugeRenderer ();
}	

{% endhighlight %}

{% endtabs %}

The SfDigitalGauge control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfDigitalGauge and configure its elements.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:gauge="clr-namespace:Syncfusion.SfGauge.XForms;assembly=Syncfusion.SfGauge.XForms"/>

{% endhighlight %}

{% highlight C# %}

	using Syncfusion.SfGauge.XForms; 

{% endhighlight %}

{% endtabs %}

* Now add the SfDigitalGauge control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" />
	
{% endhighlight %}

{% highlight C# %}

	SfDigitalGauge digitalgauge = new SfDigitalGauge(); 

{% endhighlight %}

{% endtabs %}

## Set Value

SfDigitalGauge provides option to display special characters or display values through the `Value` property.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" Value="1 2 3 4" />

{% endhighlight %}

{% highlight C# %}

    digitalgauge.Value =  "1 2 3 4";

{% endhighlight %}

{% endtabs %}

## Set Segments

The Digital Characters can be drawn in 4 different segments.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" Value="1 2 3 4" CharacterType="SegmentSeven" />

{% endhighlight %}

{% highlight c# %}

	digitalgauge.Value = "1 2 3 4";
	digitalgauge.CharacterType = CharacterType.SegmentSeven;

{% endhighlight %}

{% endtabs %}

## Configuring properties

Character Height, Width and Stroke Thickness which is used to display the Characters can be customized as in the below code snippets.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" SegmentStrokeWidth="3" CharacterHeight="50" CharacterWidth="25" CharacterType="SegmentSeven" DisabledSegmentAlpha="30" />

{% endhighlight %}

{% highlight c# %}

	SfDigitalGauge digitalgauge = new SfDigitalGauge ();
	digitalgauge.Value ="1 2 3 4";
	digitalgauge.CharacterHeight = 50;
	digitalgauge.CharacterWidth= 25;
	digitalgauge.SegmentStrokeWidth = 3;
	digitalgauge.CharacterType = CharacterType.SegmentSeven;
	digitalgauge.DisabledSegmentAlpha = 30;
	digitalgauge.BackgroundColor = Color.FromRgb (235, 235, 235);
	digitalgauge.CharacterStrokeColor = Color.FromRgb (20,108,237);
	digitalgauge.DisabledSegmentColor = Color.FromRgb (20,108,237);

{% endhighlight %}

{% endtabs %}


![](Getting-Started_images/gettingstarted.png)