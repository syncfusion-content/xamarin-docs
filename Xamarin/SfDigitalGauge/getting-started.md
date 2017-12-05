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

## Adding SfDigitalGauge Reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfdigitalgauge) link to know about the assemblies required for adding DigitalGauge to your project.

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. We need to create an instance of the `SfDigitalGaugeRenderer` in iOS and UWP projects as shown in this [KB article.](https://www.syncfusion.com/kb/7144)

I> For UWP alone, one more additional step is required if the project is built in release mode with .NET Native tool chain enabled. You can refer the [KB article](https://www.syncfusion.com/kb/7149) for more details.


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

	<gauge:SfDigitalGauge x:Name="digital" />
	
{% endhighlight %}

{% highlight C# %}

	SfDigitalGauge digital = new SfDigitalGauge(); 

{% endhighlight %}

{% endtabs %}

## Set Value

SfDigitalGauge provides option to display special characters or display values through the `Value` property.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digital" Value="1 2 3 4" />

{% endhighlight %}

{% highlight C# %}

    digital.Value =  "1 2 3 4";

{% endhighlight %}

{% endtabs %}

## Set Segments

The Digital Characters can be drawn in 4 different segments.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digital" Value="1 2 3 4" CharacterType="SegmentSeven" />

{% endhighlight %}

{% highlight c# %}

	digital.Value = "1 2 3 4";
	digital.CharacterType = CharacterType.SegmentSeven;

{% endhighlight %}

{% endtabs %}

## Configuring properties

Character Height, Width and Stroke Thickness which is used to display the Characters can be customized as in the below code snippets.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digital" SegmentStrokeWidth="3" CharacterHeight="50" CharacterWidth="25" CharacterType="SegmentSeven" DisabledSegmentAlpha="30" />

{% endhighlight %}

{% highlight c# %}

	SfDigitalGauge digital = new SfDigitalGauge ();
	digital.Value ="1 2 3 4";
	digital.CharacterHeight = 50;
	digital.CharacterWidth= 25;
	digital.SegmentStrokeWidth = 3;
	digital.CharacterType = CharacterType.SegmentSeven;
	digital.DisabledSegmentAlpha = 30;
	digital.BackgroundColor = Color.FromRgb (235, 235, 235);
	digital.CharacterStrokeColor = Color.FromRgb (20,108,237);
	digital.DisabledSegmentColor = Color.FromRgb (20,108,237);

{% endhighlight %}

{% endtabs %}


![](Getting-Started_images/gettingstarted.png)