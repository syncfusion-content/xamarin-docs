---
layout: post
title: Xamarin.Forms Chart Data Point Selection
description: How to select the data point in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Data Point Selection

You can select a data point by tapping on it. To enable the selection feature, set `EnableDataPointSelection` property as `true` for series. 

{% tabs %} 

{% highlight xaml %}

<chart:ColumnSeries EnableDataPointSelection="True" ItemsSource ="{Binding Data}" XBindingPath="Month" YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries() 
{ 
	
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 

};

columnSeries.EnableDataPointSelection = true;

{% endhighlight %}

{% endtabs %}

![](selection_images/selection_img1.png)

Following properties are used to configure the selection feature,

* `SelectedDataPointIndex` – used to programmatically select a data point.
* `SelectedDataPointColor` – used to change the selected data point color.

{% tabs %} 

{% highlight xaml %}

<chart:ColumnSeries EnableDataPointSelection="True" SelectedDataPointIndex="2" SelectedDataPointColor="Red" ItemsSource ="{Binding Data}" />

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries();

columnSeries.SelectedDataPointIndex = 2;

columnSeries.SelectedDataPointColor = Color.Red;

{% endhighlight %}

{% endtabs %}

![](selection_images/selection_img2.png)

N> For Accumulation series like pie, doughnut, pyramid and funnel, when you select a data point, the corresponding legend item also will be selected.

## Events

**SelectionChanging**

This event is triggered before the data point is selected. You can restrict a data point from being selected, by cancelling this event, by setting `Cancel` property in the event argument to true. The argument contains the following information,

* `SelectedSeries` – used to get the series of selected data point.
* `SelectedDataPointIndex` – used to get the selected data point index.
* `PreviousSelectedIndex` – used to get the previous selected data point index.
* `Cancel` – used to set the value indicating whether the selection should be cancelled.

**SelectionChanged**

This event triggered after a data point is selected. The argument contains the following information,

* `SelectedSeries` – used to get the series of selected data point.
* `SelectedDataPointIndex` – used to get the selected data point index.
* `PreviousSelectedIndex` – used to get the previous selected data point index.