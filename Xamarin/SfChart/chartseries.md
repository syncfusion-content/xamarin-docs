---
layout: post
title: Multiple series and combination of series
description: How to add multiple series and combination series in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Chart Series

## Multiple Series

You can add multiple series to `Series` property of `SfChart` class.

{% highlight xaml %}
[XAML]

<chart:SfChart>
...

	<chart:ColumnSeries ItemsSource ="{Binding Data }" XBindingPath="Country"
	 YBindingPath="Value"/>

	<chart:ColumnSeries ItemsSource ="{Binding Data1}" XBindingPath="Country"
	 YBindingPath="Value"/>

	<chart:ColumnSeries ItemsSource ="{Binding Data2}" XBindingPath="Country"
	 YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries() { ItemsSource = Data, XBindingPath = "Country", YBindingPath = "Value" };

ColumnSeries columnSeries1 = new ColumnSeries() { ItemsSource = Data1, XBindingPath = "Country", YBindingPath = "Value" };

ColumnSeries columnSeries2 = new ColumnSeries() { ItemsSource = Data2, XBindingPath = "Country", YBindingPath = "Value" };

chart.Series.Add(columnSeries);

chart.Series.Add(columnSeries1);

chart.Series.Add(columnSeries2);

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Chatseries-clubbed/multiple.png](chartseries_images/chartseries_img1.png)

## Combination Series

`SfChart` allows you to render the combination of different types of series.

{% highlight xaml %}
[XAML]

<chart:SfChart>
...

	<chart:ColumnSeries ItemsSource ="{Binding Data}" XBindingPath="Month" YBindingPath="Value"/>

	<chart:LineSeries ItemsSource ="{Binding Data1}" XBindingPath="Month" YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}
[C#]

SfChart chart = new SfChart();

...

ColumnSeries columnSeries = new ColumnSeries() { ItemsSource = Data, XBindingPath = "Month", YBindingPath = "Value" };

LineSeries lineSeries = new LineSeries() { ItemsSource = Data1, XBindingPath = "Month", YBindingPath = "Value" }; 

chart.Series.Add(columnSeries);

chart.Series.Add(lineSeries);

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Chatseries-clubbed/combinational.png](chartseries_images/chartseries_img2.png)

**Limitation of Combination Chart**

* Bar, StackingBar, and StackingBar100 cannot be combined with the other Cartesian type series.
* Cartesian type series cannot be combined with accumulation series (pie, doughnut, funnel, and pyramid).

When the combination of Cartesian and accumulation series types are added to the `Series` property, the series which are similar to the first series will be rendered and other series will be ignored. Following code snippet illustrates this.

{% highlight xaml %}
[XAML]

<chart:SfChart>
...

	<chart:LineSeries ItemsSource ="{Binding Data}" XBindingPath="Month" YBindingPath="Value"/>

	<chart:PieSeries ItemsSource ="{Binding Data1}" XBindingPath="Month" YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries() { ItemsSource = Data, XBindingPath = "Month", YBindingPath = "Value" };

PieSeries pieSeries = new PieSeries() { ItemsSource = Data1, XBindingPath = "Month", YBindingPath = "Value" };

chart.Series.Add(lineSeries);

chart.Series.Add(pieSeries);

{% endhighlight %}

![C:/Users/yuvaraj.palanisamy/Documents/My Received Files/limitation.png](chartseries_images/chartseries_img3.png)