---
layout: post
title: Xamarin.Forms | Chart Series Features
description: How to add multiple series and combination series in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Chart Series

## Multiple Series

You can add multiple series to `Series` property of `SfChart` class.

{% highlight xml %}
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

{% highlight xml %}
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

{% highlight xml %}
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

## Grouping Stacked Series

You can add multiple groups of stacking series using `GroupingLabel` property of stacked series, and each group can contain multiple stacking series.

{% highlight xml %}
[XAML]

<chart:SfChart>
...

	<chart:StackingColumnSeries ItemsSource ="{Binding Data1}" GroupingLabel="GruopOne" Label="Google" XBindingPath="Month" YBindingPath="Value"/>

	<chart:StackingColumnSeries ItemsSource ="{Binding Data2}" GroupingLabel="GruopOne" Label="Bing" XBindingPath="Month" YBindingPath="Value"/>

	<chart:StackingColumnSeries ItemsSource ="{Binding Data3}" GroupingLabel="GruopTwo" Label="Yahoo" XBindingPath="Month" YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

StackingColumnSeries stackingColumnSeries1 = new StackingColumnSeries() 
{ 
	ItemsSource = Data1, 
	GroupingLabel = "GroupOne",
	Label = "Google",
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

StackingColumnSeries stackingColumnSeries2 = new StackingColumnSeries() 
{ 
	ItemsSource = Data2, 
	GroupingLabel = "GroupOne",
	Label = "Google",
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

StackingColumnSeries stackingColumnSeries3 = new StackingColumnSeries() 
{ 
	ItemsSource = Data3,
	GroupingLabel = "GroupTwo",
	Label = "Yahoo",
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

chart.Series.Add(stackingColumnSeries1);
chart.Series.Add(stackingColumnSeries2);
chart.Series.Add(stackingColumnSeries3);

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Chatseries-clubbed/grouping.png](chartseries_images/chartseries_img4.png)