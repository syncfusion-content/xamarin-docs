---
layout: post
title: Performance Line Chart
description: Performance in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Performance

* When there are large number of points to load in line series, you can use [`FastLineSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.FastLineSeries.html#) series instead of [LineSeries](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.LineSeries.html#). To renderer a fast line chart, create an instance of [FastLineSeries](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.FastLineSeries.html#) and add to the [Series](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeriesCollection.html#) collection property of [SfChart](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html#).

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

* Instead of enabling data markers and labels when there are large number of data points, you can use **Trackball** to view the point information.