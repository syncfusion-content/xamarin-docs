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

* When your underlying data object implements INotifyPropertyChanged, you need to enable the ListenPropertyChange property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, ListenPropertyChange is set to false in order to avoid the event registration unnecessarily.

N>If you have minimal set of data points, the recommended approach is to use normal line series to visualize those data using line chart. Because the normal line series has provisions to customize the color and shape of individual line.
