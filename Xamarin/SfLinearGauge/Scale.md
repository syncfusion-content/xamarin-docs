---
layout: post
title: Scale of LinearGauge in Xamarin.Forms
description: Learn how to set maximum and minim value of lineargauge.
platform: Xamarin.Android
control: LinearGauge
documentation: ug
---

# Scale

Main Scale is the linear scale that integrates ticks, labels and scale bar to specify the basic look and feel of the Linear Gauge. It defines the overall minimum and maximum values, along with the frequency of labels and ticks through the interval of the scale. It can contain multiple ranges within a scale. It also contains one or more pointers to point out the measures of the linear scale.

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