---
layout: post
title: Linear Tick Settings in LinearGauge
description: Learn how to define settings of linear ticks in LinearGauge
platform: Xamarin.Forms
control: LinearGauge
documentation: ug
---
# LinearTickSettings

Ticks are categorized into two types: major and minor. These ticks are arranged with respect to the specified frequency i.e., Interval of the linear scale. The minor ticks are displayed using the 
MinorTicksPerInterval property.

{% tabs %}

{% highlight C# %}

	LinearTickSettings minor = new LinearTickSettings ();
	minor.Length = 10;
	minor.Color = Color.FromRgb (175, 175, 175);
	minor.Thickness = 1;
	scale.MinorTickSettings = minor;
	//Major Ticks setting
	LinearTickSettings major = new LinearTickSettings ();
	major.Length = 10;
	major.Color = Color.FromRgb (175, 175, 175);
    major.Thickness = 1;
    scale.MajorTickSettings = major; 
	
{% endhighlight %}

{% highlight xaml %}

	<gauge:LinearTickSettings x:Name="minor" Length="10" Thickness="1" MinorTickSettings="minor" />
	
{% endhighlight %}

{% endtabs %}


![](images/LinearTickSettings.png)

