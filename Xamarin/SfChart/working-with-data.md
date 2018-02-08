---
layout: post
title: Populating data
description: How to add data point to series in  Essential Xamarin.forms Chart.
platform: xamarin
control: Chart
documentation: ug
---

# Populating Data

Chart control can be configured with data points using the `ItemsSource` property of the `ChartSeries`. You can create data points using the following two ways.

## Chart data point	

One way is creating a collection of [ChartDataPoint](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataPoint.html#) objects, and assigning this collection to the `ItemsSource` property. Here, each `ChartDataPoint` object represents a data point in a chart series.

N> `ChartDataPoint` class has few overloaded constructors depending on the number of y-values required to plot a data point for a particular series type. For example, you can use a constructor with two parameters to instantiate a data point for `XYDataSeries` such as Line, Spline, and Pie, etc.

Following code snippet illustrates this,

{% highlight c# %}

public class DataModel
{
	
	public ObservableCollection<ChartDataPoint>  HighTemperature{ get; set; }

	public DataModel ()
	{
	
		HighTemperature = new ObservableCollection<ChartDataPoint> ();

		HighTemperature.Add (new ChartDataPoint ("Jan", 42));
		HighTemperature.Add (new ChartDataPoint ("Feb", 44));
		HighTemperature.Add (new ChartDataPoint ("Mar", 53));
		HighTemperature.Add (new ChartDataPoint ("Apr", 64));
		HighTemperature.Add (new ChartDataPoint ("May", 75));
		HighTemperature.Add (new ChartDataPoint ("Jun", 83));
		HighTemperature.Add (new ChartDataPoint ("Jul", 87));
		HighTemperature.Add (new ChartDataPoint ("Aug", 84));
		HighTemperature.Add (new ChartDataPoint ("Sep", 78));
		HighTemperature.Add (new ChartDataPoint ("Oct", 67));
		HighTemperature.Add (new ChartDataPoint ("Nov", 55));
		HighTemperature.Add (new ChartDataPoint ("Dec", 45));

	}

}

{% endhighlight %}

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.Series>

		<chart:ColumnSeries ItemsSource="{Binding HighTemperature}"/>

	</chart:SfChart.Series> 

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

//Adding the series to the chart and set the ItemsSource property

chart.Series.Add (new ColumnSeries () {
	
	ItemsSource = dataModel.HighTemperature

});

{% endhighlight %}

{% endtabs %}

## Custom object

Another way is assigning a collection of custom objects to the `ItemsSource` property. In this case, you should set the `XBindingPath` and `YBindingPath` properties of chart series with the property names of the custom object, which contains the x-value/category and y-value, respectively.

N> While using custom objects, `XBindingPath` property is required for all types of chart series. You should set the `YBindingPath` property only for the `XYDataSeries` types, which need single y-value for a data point, e.g., Line, Spline, Column, Bar, Pie, etc. For bubble series type, you should set both `YBindingPath` and `Size` properties since it requires two y-values to plot a single bubble data point. In financial series types such as Candle and HiLoOpenClose, you should set the `High`, `Low`, `Open`, and `Close` properties with the property names of a custom object, which contains respective values since the chart types require four y-values for a single data point.

{% highlight c# %}
[C#]

public class MonthDemand

{

	public MonthDemand(string demand, double year2010, double year2011)
	{

		this.Demand = demand;

		this.Year2010 = year2010;

		this.Year2011 = year2011;

	}

	public string Demand { get; set; }

	public double Year2010 { get; set; }

	public double Year2011 { get; set; }

}

public class DataModel
{
	
	public ObservableCollection<MonthDemand>  Demands{ get; set; }

	public DataModel ()
	{

		Demands = new ObservableCollection<MonthDemand>();

		Demands.Add(new MonthDemand("Jan", 42, 27));
		Demands.Add(new MonthDemand("Feb", 44, 28));
		Demands.Add(new MonthDemand("Mar", 53, 35));
		Demands.Add(new MonthDemand("Apr", 64, 44));
		Demands.Add(new MonthDemand("May", 75, 54));
		Demands.Add(new MonthDemand("Jun", 83, 63));
		Demands.Add(new MonthDemand("Jul", 87, 68));
		Demands.Add(new MonthDemand("Aug", 84, 66));
		Demands.Add(new MonthDemand("Sep", 78, 59));
		Demands.Add(new MonthDemand("Oct", 67, 48));
		Demands.Add(new MonthDemand("Nov", 55, 38));
		Demands.Add(new MonthDemand("Dec", 45, 29));

	}

}   

{% endhighlight %}

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

  <chart:SfChart.Series>

	  <chart:ColumnSeries ItemsSource="{Binding Demands}" XBindingPath="Demand" 
	 					  YBindingPath="Year2010"/>

  </chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Series.Add (new ColumnSeries () {
	
	ItemsSource = dataModel.Demands,

	XBindingPath = "Demand",

	YBindingPath = "Year2010"

});

{% endhighlight %}

{% endtabs %}