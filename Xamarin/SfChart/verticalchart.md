---
layout: post
title: Vertical Chart
description: How to show cartesian series vertically in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---


# Vertical Chart

Vertical chart is used to show the cartesian series vertically, which helps to view the data in different
perceptive.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.Series>

	<chart:LineSeries ItemsSource="{Binding Data}" XBindingPath="Month"
					  YBindingPath="Value" IsTransposed="True"/>

</chart:SfChart.Series>


{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...	

LineSeries lineSeries = new LineSeries();
lineSeries.XBindingPath = "Month";
lineSeries.YBindingPath = "Value";
]lineSeries.ItemsSource = Data;
lineSeries.IsTransposed = true;
chart.Series.Add(lineSeries);


{% endhighlight %}

{% endtabs %}

![](chartseries_images/verticalchart.png)