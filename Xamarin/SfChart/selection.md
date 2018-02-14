---
layout: post
title: Xamarin.Forms Chart Data Point Selection
description: How to select the data point in Essential Xamarin.Forms chart
platform: xamarin
control: Chart
documentation: ug
---

# Data Point Selection

You can select a data point by tapping it. To enable the selection feature, set the [`EnableDataPointSelection`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~EnableDataPointSelection.html#) property to `true` for [`Series`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html). 

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

The following properties are used to configure the selection feature:

* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~SelectedDataPointIndex.html#)—Used to select a data point programmatically.
* [`SelectedDataPointColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~SelectedDataPointColor.html#)—Used to change the selected data point's color.

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

N> For accumulation series (pie, doughnut, etc.), when you select a data point, the corresponding legend item also will be selected.

## Events

**SelectionChanging**

This event is triggered before a data point is selected. You can restrict a data point from being selected by canceling this event. To cancel this event, set the [Cancel](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionChangingEventArgs~Cancel.html#) property to true. This event contains the following informations:

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedSeries.html#)—Used to get the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedDataPointIndex.html#)—Used to get the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~PreviousSelectedIndex.html#)—Used to get the previous selected data point index.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionChangingEventArgs~Cancel.html#)—Used to set the value, which indicates whether the selection should be canceled.

**SelectionChanged**

This event is triggered after a data point has been selected. This event contains the following informations:

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedSeries.html#)—Used to get the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedDataPointIndex.html#)—Used to get the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~PreviousSelectedIndex.html#)—Used to get the previous selected data point index.