---
layout: post
title: Linear Tick Settings in LinearGauge
description: Learn how to define settings of linear ticks in LinearGauge
platform: Xamarin
control: LinearGauge
documentation: ug
---

# Settings Ticks 

Ticks are categorized into two type as major and minor. These ticks are arranged with respect to the specified frequency i.e., Interval of the linear scale. The minor ticks are displayed using the 
`MinorTicksPerInterval` property.

{% tabs %}

{% highlight xaml %}

	<gauge:LinearTickSettings x:Name="minor" Length="5" Thickness="1" MinorTickSettings="minor" />
	
{% endhighlight %}

{% highlight C# %}

	LinearTickSettings minor = new LinearTickSettings ();
	minor.Length = 5;
	minor.Color = Color.FromRgb (152, 152, 0);
	minor.Thickness = 1;
	scale.MinorTickSettings = minor;
	//Major Ticks setting
	LinearTickSettings major = new LinearTickSettings ();
	major.Length = 10;
	major.Color = Color.FromRgb (229, 0, 0);
    major.Thickness = 1;
    scale.MajorTickSettings = major; 
	
{% endhighlight %}

{% endtabs %}


![](images/LinearTickSettings.png)

