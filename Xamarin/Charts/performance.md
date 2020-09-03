---
layout: post
title: Performance Line Syncfusion.Xamarin.Forms Chart
description: Performance in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Performance

Following are the key points that can be used to boost the performance of the chart when there is a need to plot high volume data.

* When there are large number of points to load in line series, you can use [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html#) series instead of [`LineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.LineSeries.html#). To renderer a fast line chart, create an instance of [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html#) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeriesCollection.html#) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#).

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

<chart:FastLineSeries ItemsSource ="{Binding Data}" XBindingPath="XValue" YBindingPath="YValue"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

FastLineSeries fastLineSeries = new FastLineSeries() 
{ 
	
	ItemsSource = Data, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue"
	
};

chart.Series.Add(fastLineSeries);

{% endhighlight %}

{% endtabs %}

N>If you have minimal set of data points, the recommended approach is to use normal line series to visualize those data using line chart. Because the normal line series has provisions to customize the color and shape of individual line.

* Instead of enabling data markers and labels when there are large number of data points, you can use [`Trackball`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartTrackballBehavior.html#) to view the point information.

* The default stroke width of the [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html) is 2, reducing this to 1 will improve the performance. Refer the following code snippet to configure the stroke width of FastLineSeries.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

<chart:FastLineSeries ItemsSource ="{Binding Data}" XBindingPath="XValue" YBindingPath="YValue" StrokeWidth="1"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

FastLineSeries fastLineSeries = new FastLineSeries() 
{ 
	
	ItemsSource = Data, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue",
	StrokeWidth = 1  
	
};

chart.Series.Add(fastLineSeries);

{% endhighlight %}

{% endtabs %}

* When the underlying data object implements INotifyPropertyChanged, you need to enable the [`ListenPropertyChange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_ListenPropertyChange) property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, [`ListenPropertyChange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_ListenPropertyChange) is set to false in order to avoid the event registration unnecessarily.

* Whenever there is a new data point is added to the [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_ItemsSource) property of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html), the chart will be refreshed with new data point if the [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_ItemsSource) property contains `ObservableCollection`. In order to avoid the chart rendering for each update in [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_ItemsSource), you can suspend the chart using [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_SuspendSeriesNotification) method of chart and the [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_ResumeSeriesNotification)should be called once the required data points are added to the collection and the chart should be refreshed with data points that have been added between these two method calls.

{% tabs %} 

{% highlight c# %}

Chart.SuspendSeriesNotification();

// ...

// Add the data points to ItemsSource property.

// ...

Chart.ResumeSeriesNotification();

{% endhighlight %}

{% endtabs %}

Similarly, you can use [`SuspendNotification`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_SuspendNotification) and [`ResumeNotification`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_ResumeNotification) methods of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html) to suspend and resume the update of the respective series.

{% tabs %} 

{% highlight c# %}

series.SuspendNotification();

// ...

// Add the data points to ItemsSource property.

// ...

series.ResumeNotification();

{% endhighlight %}

{% endtabs %}