---
layout: post
title: Xamarin.Forms Chart Data Point Selection
description: How to select the data point in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Data Point Selection

You can select a data point by tapping on it. To enable the selection feature, set [`EnableDataPointSelection`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~EnableDataPointSelection.html#) property as `true` for [`Series`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html). 

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

* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~SelectedDataPointIndex.html#) – used to programmatically select a data point.
* [`SelectedDataPointColor`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~SelectedDataPointColor.html#) – used to change the selected data point color.

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

The [`SelectionChanging`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SelectionChanging_EV.html) event is triggered before the data point is selected. You can restrict a data point from being selected, by canceling this event, by setting [Cancel](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionChangingEventArgs~Cancel.html#) property in the event argument to true. The argument contains the following information,

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedSeries.html#) – used to get the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedDataPointIndex.html#) – used to get the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~PreviousSelectedIndex.html#) – used to get the previous selected data point index.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionChangingEventArgs~Cancel.html#) – used to set the value indicating whether the selection should be canceled.

**SelectionChanged**

The [`SelectionChanged`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SelectionChanged_EV.html) event triggered after a data point is selected. The argument contains the following information,

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedSeries.html#) - Gets the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedDataPointIndex.html#) - Gets the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~PreviousSelectedIndex.html#) - Gets the previous selected data point index.

## Methods

**OnSelectionChanging**

The [`OnSelectionChanging`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionBehavior~OnSelectionChanging.html) method of chart selection behavior is used to perform the operations, before the data point is selected, by extending the [`ChartSelectionBehavior`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionBehavior.html) class. This method argument contains the following information:

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedSeries.html#) - Gets the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedDataPointIndex.html#) - Gets the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~PreviousSelectedIndex.html#) - Gets the previous selected data point index.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionChangingEventArgs~Cancel.html#) -Sets the value that indicates whether the selection should be canceled.

{% highlight c# %}

public class ChartSelectionBehaviorExt : ChartSelectionBehavior
{
   protected override void OnSelectionChanging(ChartSelectionChangingEventArgs args)
   {
            var selectedSeres = args.SelectedSeries;
            var dataPointIndex = args.SelectedDataPointIndex;
            var previousSelectedIndex = args.PreviousSelectedIndex;
   }
}

{% endhighlight %}

**OnSelectionChanged**

The [`OnSelectionChanged`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionBehavior~OnSelectionChanged.html) method of the[`ChartSelectionBehavior`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionBehavior.html) is used to perform the operations after a data point is selected. This method argument contains the following information:

* [`SelectedSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedSeries.html#) - Gets the series of selected data point.
* [`SelectedDataPointIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~SelectedDataPointIndex.html#) - Gets the selected data point index.
* [`PreviousSelectedIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionEventArgs~PreviousSelectedIndex.html#) - Gets the previous selected data point index.

{% highlight c# %}

public class ChartSelectionBehaviorExt : ChartSelectionBehavior
{
        
        protected override void OnSelectionChanged(ChartSelectionEventArgs args)
        {
            var selectedSeries = args.SelectedSeries;
            var dataPointIndex = args.SelectedDataPointIndex;
            var previousSelectedIndex = args.PreviousSelectedIndex;
        }
}

{% endhighlight %}
