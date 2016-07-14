---
layout: post
title: Linear Tick Settings in LinearGauge
description: Learn how to define settings of linear ticks in LinearGauge
platform: Xamarin
control: LinearGauge
documentation: ug
---
# Configuring Ticks and Labels

## Settings Ticks 

Ticks are categorized into two type as major and minor. These ticks are arranged with respect to the specified frequency i.e., Interval of the linear scale. The minor ticks are displayed using the 
`MinorTicksPerInterval` property.

{% tabs %}

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

{% highlight xaml %}

	<gauge:LinearTickSettings x:Name="minor" Length="5" Thickness="1" MinorTickSettings="minor" />
	
{% endhighlight %}

{% endtabs %}


![](images/LinearTickSettings.png)

## Setting Value and Label

LinearScale is used to set the Labels, Values and Ticks to specify the basic look and feel of the SfLinearGauge. It defines the overall minimum and maximum values, along with the frequency of labels and ticks through the interval of the scale. It can contain multiple ranges within a scale. It also contains one or more pointers to point out the measures of the linear scale.

{% tabs %}

{% highlight C# %}

	ObservableCollection<LinearScale> scales = new ObservableCollection<LinearScale> ();
	LinearScale scale=new LinearScale();
	scale.MinimumValue=0;
	scale.MaximumValue=100;
	scale.Interval=20;
	scale.ScaleBarLength=100;
	scale.ScaleBarColor= Color.FromRgb (250, 236, 236);
	scale.LabelColor = Color.FromRgb (84, 84, 84); 
	scale.MinorTicksPerInterval = 1;
	scale.ScaleBarSize = 13;
	scale.ScalePosition = ScalePosition.BackWard;	
	sfLinearGauge.Scales=scale;
	
{% endhighlight %}

{% highlight xaml %}

	<gauge:LinearScale x:Name="scale" MinimumValue="0" MaximumValue="100" Interval="20" ScaleBarLength="100" ScaleBarColor="Color.Red" MinorTicksPerInterval="1" ScaleBarSize="13" ScalePosition="Backward" />
	
{% endhighlight %}

{% endtabs %}

![](images/Scale.png)
