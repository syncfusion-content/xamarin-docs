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

{% highlight xaml %}
[XAML]

<chart:SfChart.Series>
<chart:LineSeries ItemsSource="{Binding Data}" XBindingPath="Month"
YBindingPath="Vaue" IsTransposed="True"/>
</chart:SfChart.Series>


{% endhighlight %}

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...	

LineSeries lineSeries = new LineSeries();
lineSeries.XBindingPath = "Month";
lineSeries.YBindingPath = "Value";
]lineSeries.ItemsSource = Data;
lineSeries.IsTransposed = true;
chart.Series.Add(lineSeries);


{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Chatseries-clubbed/multiple.png](chartseries_images/verticalchart.png)