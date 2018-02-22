---
layout: post
title: Performance Line Chart
description: Performance in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Performance

* When there are large number of points to load in line series, you can use [`FastLineSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.FastLineSeries.html#) series instead of [`LineSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.LineSeries.html#). To renderer a fast line chart, create an instance of [`FastLineSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.FastLineSeries.html#) and add to the [`Series`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeriesCollection.html#) collection property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html#).

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

* Instead of enabling data markers and labels when there are large number of data points, you can use [`Trackball`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior.html#) to view the point information.

##Add range of points dynamically

Whenever you add a data point to the ItemsSource dynamically, the corresponding data will be updated inside the chart series synchronously. This operation will be happening for each data point that you add subsequently. You can avoid this by calling the [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SuspendSeriesNotification.html) method of chart before adding the range of data points and calling the [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ResumeSeriesNotification.html) to update all the data points that have been added between these two method calls.

{% highlight c# %}

 	Chart.SuspendSeriesNotification();

		// ...

		// Add multiple data points.

		// ...

	Chart.ResumeSeriesNotification();

{% endhighlight %}

As similarly, you can use [`SuspendNotification`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~SuspendNotification.html) and [`ResumeNotification`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~ResumeNotification.html) methods in the chart series to update the all the data points that have been added between these two method calls.

{% highlight c# %}

 	series.SuspendNotification();

		// ...

		// Add multiple data points.

		// ...

	series.ResumeNotification();

{% endhighlight %}