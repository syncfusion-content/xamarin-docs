---
layout: post
title: Syncfusion.Xamarin.Forms Chart types
description: This section explains the different types of charts, including Cartesian, Financial, Accumulation, PolarRadar and its properties.
platform: xamarin
control: Chart
documentation: ug
---

# Chart Types in Xamarin

## Line Chart

To render a [`Line chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/line-chart), create an instance of [`LineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.LineSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the line.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the line.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:LineSeries ItemsSource ="{Binding Data}" XBindingPath="Year"
	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries()
{
	ItemsSource = Data,
	XBindingPath = "Year",
	YBindingPath = "Value"
};
chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

![Line chart type in Xamarin.Forms](charttypes_images/charttypes_img1.png)

### Dashed Lines

[`StrokeDashArray`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.LineSeries.html#Syncfusion_SfChart_XForms_LineSeries_StrokeDashArray) property of the [`LineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.LineSeries.html) is used to render line series with dashes.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries ItemsSource ="{Binding Data}" XBindingPath="Month" YBindingPath="Value">
    <chart:LineSeries.StrokeDashArray>
        <x:Array Type="{x:Type x:Double}">
            <sys:Double>5</sys:Double>
            <sys:Double>6</sys:Double>
        </x:Array>
    </chart:LineSeries.StrokeDashArray>
</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries lineSeries = new LineSeries()
{
    ItemsSource = Data,
    XBindingPath = "Month",
    YBindingPath = "Value"
};

lineSeries.StrokeDashArray = new double[2] { 5, 6 };
chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

## Fast Line Chart

[`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html) is a line chart, but it loads faster than [`LineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.LineSeries.html). You can use this when there are large number of points to be loaded in chart. To render a fast line chart, create an instance of [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the fast line segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.

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

![FastLine chart type in Xamarin.Forms](charttypes_images/charttypes_img14.png)

### Dashed Lines

[`StrokeDashArray`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html#Syncfusion_SfChart_XForms_FastLineSeries_StrokeDashArray) property of the [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html) is used to render fast line series with dashes.

{% highlight c# %}
[C#]

FastLineSeries fastLineSeries = new FastLineSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};
fastLineSeries.StrokeDashArray = new double[2] { 2, 3 };

{% endhighlight %}

![Dashed lines support for FastLineSeries in Xamarin.Forms Chart](charttypes_images/charttypes_img15.png)

### EnableAntiAliasing 

Since [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html) can be loaded with a large number of points, the rendering of series should be smooth. This requirement can be achieved by setting [`EnableAntiAliasing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html#Syncfusion_SfChart_XForms_FastLineSeries_EnableAntiAliasing) property of [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastLineSeries.html) as false.

## Stacked Line Chart
To render a stacked line chart, create an instance of `StackingLineSeries` and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the stacked line appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the line.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the line.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.


{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingLineSeries ItemsSource ="{Binding Data1}" XBindingPath="XValue" YBindingPath="YValue"/>

	<chart:StackingLineSeries ItemsSource ="{Binding Data2}" XBindingPath="XValue" YBindingPath="YValue"/>

	<chart:StackingLineSeries ItemsSource ="{Binding Data3}" XBindingPath="XValue" YBindingPath="YValue"/>

	<chart:StackingLineSeries ItemsSource ="{Binding Data4}" XBindingPath="XValue" YBindingPath="YValue"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingLineSeries stackingLineSeries1 = new StackingLineSeries() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

StackingLineSeries stackingLineSeries2 = new StackingLineSeries() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

StackingLineSeries stackingLineSeries3 = new StackingLineSeries() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

StackingLineSeries stackingLineSeries4 = new StackingLineSeries() 
{ 
	ItemsSource = Data4, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

chart.Series.Add(stackingLineSeries1);
chart.Series.Add(stackingLineSeries2);
chart.Series.Add(stackingLineSeries3);
chart.Series.Add(stackingLineSeries4);

{% endhighlight %}

{% endtabs %}

### Dashed Stacked Lines

`StrokeDashArray` property of the `StackingLineSeries` is used to render stacked line series with dashes.

{% highlight c# %}
[C#]

StackingLineSeries stackingLineSeries1 = new StackingLineSerie()
{ 
	ItemsSource = Data1, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};
stackingLineSeries1.StrokeDashArray = new double[2] { 13, 4 };

StackingLineSeries stackingLineSeries2 = new StackingLineSerie()
{ 
	ItemsSource = Data1, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};
stackingLineSeries2.StrokeDashArray = new double[2] { 13, 4 };

StackingLineSeries stackingLineSeries3 = new StackingLineSerie()
{ 
	ItemsSource = Data1, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};
stackingLineSeries3.StrokeDashArray = new double[2] { 13, 4 };

StackingLineSeries stackingLineSeries4 = new StackingLineSerie()
{ 
	ItemsSource = Data1, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};
stackingLineSeries4.StrokeDashArray = new double[2] { 13, 4 };

{% endhighlight %}

## 100% Stacked Line Chart

To render a 100% stacked line chart, create an instance of `StackingLine100Series` and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the series appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the line.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the line.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* `StrokeDashArray` - used to change the dashes of the stacked line series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingLine100Series ItemsSource ="{Binding Data1}" XBindingPath="XValue" YBindingPath="YValue"/>

	<chart:StackingLine100Series ItemsSource ="{Binding Data2}" XBindingPath="XValue" YBindingPath="YValue"/>

	<chart:StackingLine100Series ItemsSource ="{Binding Data3}" XBindingPath="XValue" YBindingPath="YValue"/>

	<chart:StackingLine100Series ItemsSource ="{Binding Data4}" XBindingPath="XValue" YBindingPath="YValue"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingLine100Series stackingLine100Series1 = new StackingLine100Series() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

StackingLine100Series stackingLine100Series2 = new StackingLine100Series() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

StackingLine100Series stackingLine100Series3 = new StackingLine100Series() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

StackingLine100Series stackingLine100Series4 = new StackingLine100Series() 
{ 
	ItemsSource = Data4, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue" 
};

chart.Series.Add(stackingLine100Series1);
chart.Series.Add(stackingLine100Series2);
chart.Series.Add(stackingLine100Series3);
chart.Series.Add(stackingLine100Series4);

{% endhighlight %}

{% endtabs %}

## Area Chart

To render an [`Area chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/area-chart), create an instance of [`AreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AreaSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AreaSeries.html#Syncfusion_SfChart_XForms_AreaSeries_StrokeColor) – used to change the stroke color of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:AreaSeries ItemsSource ="{Binding Data}" XBindingPath="Year"
					  YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

AreaSeries areaSeries = new AreaSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};
chart.Series.Add(areaSeries);

{% endhighlight %}

{% endtabs %}

![Area chart type in Xamarin.Forms](charttypes_images/charttypes_img2.png)

## Spline Area Chart

To render a [`Spline Area chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/spline-area-chart), create an instance of [`SplineAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineAreaSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the spline area appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineAreaSeries.html#Syncfusion_SfChart_XForms_SplineAreaSeries_StrokeColor) – used to change the stroke color of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:SplineAreaSeries ItemsSource ="{Binding Data}" XBindingPath="Year"
	                       	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

SplineAreaSeries splineAreaSeries = new SplineAreaSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};
chart.Series.Add(splineAreaSeries);

{% endhighlight %}

{% endtabs %}

![SplineArea chart type in Xamarin.Forms](charttypes_images/charttypes_img3.png)

### Spline Rendering Types

[`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineAreaSeries.html#Syncfusion_SfChart_XForms_SplineAreaSeries_SplineType) allows you to change the spline area curve in series. 
The following types are used in [`SplineAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineAreaSeries.html) as 

 * [`Natural`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)
 * [`Monotonic`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)
 * [`Cardinal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)
 * [`Clamped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)

By default [`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineAreaSeries.html#Syncfusion_SfChart_XForms_SplineAreaSeries_SplineType) value is [`Natural`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html).

The following code shows how to set the [`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineAreaSeries.html#Syncfusion_SfChart_XForms_SplineAreaSeries_SplineType) value as [`Cardinal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)

{% tabs %}

{% highlight xaml%}

<chart:SfChart>
...

	<chart:SplineAreaSeries ItemsSource ="{Binding Data}" XBindingPath="Month"
	  					YBindingPath="Value" SplineType="Cardinal" />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

SplineAreaSeries splineAreaSeries = new SplineAreaSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value",
	SplineType = SplineType.Cardinal
};
chart.Series.Add(splineAreaSeries);

{% endhighlight %}

{% endtabs %}


## Step Area Chart

To render a [`Step Area chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/step-area-chart), create an instance of [`StepAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StepAreaSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) - used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) - used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StepAreaSeries.html#Syncfusion_SfChart_XForms_StepAreaSeries_StrokeColor) - used to change the stroke color of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

    <chart:StepAreaSeries ItemsSource ="{Binding Data}" XBindingPath="Year"
                            YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StepAreaSeries stepAreaSeries = new StepAreaSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Year", 
    YBindingPath = "Value" 
};
chart.Series.Add(stepAreaSeries);

{% endhighlight %}

{% endtabs %}

![StepArea chart type in Xamarin.Forms](charttypes_images/StepArea.png)

## Range Area Chart

To render a [`Range Area chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/range-area-chart), create an instance of [`RangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeAreaSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

Since the [`RangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeAreaSeries.html) requires two Y values for a point, your data should contain high and low values. High and low value specifies the maximum and minimum range of the point.

There are two ways you can provide data to range area chart,

1.You can use [`ChartDataPoint's`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint__ctor_System_IComparable_System_Double_System_Double_) three parameter constructor to pass [`XValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_XValue), [`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_High) and [`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Low) values to [`RangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeAreaSeries.html),

{% highlight c# %}
[C#] 

SfChart chart = new SfChart();
...

ObservableCollection<ChartDataPoint> data = new ObservableCollection<ChartDataPoint>()
{
     new ChartDataPoint("Jan/10", 30, 18),
     new ChartDataPoint("Feb/10", 24, 12),
     new ChartDataPoint("Mar/10", 29, 15),
     new ChartDataPoint("Apr/10", 24, 10),
     new ChartDataPoint("May/10", 30, 18),
     new ChartDataPoint("Jun/10", 24, 10),
};

RangeAreaSeries rangeAreaSeries = new RangeAreaSeries()
{
     ItemsSource = data
};

chart.Series.Add(rangeAreaSeries);

{% endhighlight %}

2.Or else you can use [`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeSeriesBase.html#Syncfusion_SfChart_XForms_RangeSeriesBase_High) and [`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeSeriesBase.html#Syncfusion_SfChart_XForms_RangeSeriesBase_Low) properties of [`RangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeAreaSeries.html) to map the high and low values from custom object to chart.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...
    <chart:SfChart.Series>
        <chart:RangeAreaSeries ItemsSource="{Binding RangeAreaData}" XBindingPath="Name" High="High" Low="Low"/>
    </chart:SfChart.Series>
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

RangeAreaSeries rangeAreaSeries = new RangeAreaSeries()
{
     ItemsSource = RangeAreaData,
     XBindingPath = "Name",
     High = "High",
     Low = "Low"
};
chart.Series.Add(rangeAreaSeries);

{% endhighlight %}

{% endtabs %}

You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeAreaSeries.html#Syncfusion_SfChart_XForms_RangeAreaSeries_StrokeColor) – used to change the stroke color of the series.

![RangeArea chart type in Xamarin.Forms](charttypes_images/RangeArea.png)

## Spline Range Area Chart

To render a [`Spline Range Area chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/spline-range-area-chart), create an instance of the [`SplineRangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineRangeAreaSeries.html), and add that instance to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

Since the [`SplineRangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineRangeAreaSeries.html) requires two Y values for a point, data should contain high and low values. The high and low values specify the maximum and minimum ranges of a point.

The data can be provided to a spline range area chart by using the following two ways:

1.Using the [`ChartDataPoint’s`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint__ctor_System_IComparable_System_Double_System_Double_) three parameter constructor to pass [`XValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_XValue), [`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_High), and [`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Low) values to the [`SplineRangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineRangeAreaSeries.html).

{% highlight c# %}
[C#] 

SfChart chart = new SfChart();
...

ObservableCollection<ChartDataPoint> data = new ObservableCollection<ChartDataPoint>()
{
     new ChartDataPoint("Jan", 30, 18),
     new ChartDataPoint("Feb", 24, 12),
     new ChartDataPoint("Mar", 29, 15),
     new ChartDataPoint("Apr", 24, 10),
     new ChartDataPoint("May", 30, 18),
     new ChartDataPoint("Jun", 24, 10),
};

SplineRangeAreaSeries splineRangeAreaSeries = new SplineRangeAreaSeries() 
{
	ItemsSource = data 
};

chart.Series.Add(splineRangeAreaSeries);

{% endhighlight %}

2.Or else, using the [`high`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeSeriesBase.html#Syncfusion_SfChart_XForms_RangeSeriesBase_High) and [`low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeSeriesBase.html#Syncfusion_SfChart_XForms_RangeSeriesBase_Low) properties of [`SplineRangeAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineRangeAreaSeries.html) to map the high and low values from custom object to chart.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart> 
... 
	<chart:SfChart.Series> 
		<chart:SplineRangeAreaSeries ItemsSource="{Binding SplineRangeAreaData}" XBindingPath="Name" High="High" Low="Low"/> 
	</chart:SfChart.Series> 
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart(); 
...

SplineRangeAreaSeries splineRangeAreaSeries = new SplineRangeAreaSeries() 
{ 
	ItemsSource = SplineRangeAreaData, 
	XBindingPath = "Name", 
	High = "High", 
	Low = "Low" 
}; 

chart.Series.Add(splineRangeAreaSeries);

{% endhighlight %}

{% endtabs %}

![SplineRangeArea chart type in Xamarin.Forms](charttypes_images/SplineRangeArea.png)

### Spline Rendering Types

[`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineRangeAreaSeries.html#Syncfusion_SfChart_XForms_SplineRangeAreaSeries_SplineType) property allows you to change the spline range area curve in series.

The following types can be used for SplineRangeAreaSeries
*	Natural 
*	Monotonic
*	Cardinal
*	Clamped

By default [`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineRangeAreaSeries.html#Syncfusion_SfChart_XForms_SplineRangeAreaSeries_SplineType) value is Natural.

The following code shows how to set the [`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineRangeAreaSeries.html#Syncfusion_SfChart_XForms_SplineRangeAreaSeries_SplineType) value as Cardinal.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
… 
   <chart:SplineRangeAreaSeries ItemsSource="{Binding SplineRangeAreaData}" XBindingPath="Name" High="High" Low="Low" SplineType="Cardinal"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SplineRangeAreaSeries splineRangeAreaSeries = new SplineRangeAreaSeries
            {
                ItemsSource = SplineRangeAreaData,
                XBindingPath = "Name",
                High = "High",
                Low = "Low",
                SplineType = SplineType.Cardinal
            };

            chart.Series.Add(splineRangeAreaSeries);
			
{% endhighlight %}

{% endtabs %}

## Stacked Area Chart

To render a [`Stacked Area chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/stacked-area-chart), create an instance of [`StackingAreaSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingAreaSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the stacked area appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingSeriesBase.html#Syncfusion_SfChart_XForms_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingAreaSeries ItemsSource ="{Binding Data1}" XBindingPath="Year" 
							  YBindingPath="Value"/>

	<chart:StackingAreaSeries ItemsSource ="{Binding Data2}" XBindingPath="Year" 
							  YBindingPath="Value"/>

	<chart:StackingAreaSeries ItemsSource ="{Binding Data3}" XBindingPath="Year" 
							  YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingAreaSeries stackingAreaSeries1 = new StackingAreaSeries() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

StackingAreaSeries stackingAreaSeries2 = new StackingAreaSeries() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

StackingAreaSeries stackingAreaSeries3 = new StackingAreaSeries() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

chart.Series.Add(stackingAreaSeries1);
chart.Series.Add(stackingAreaSeries2);
chart.Series.Add(stackingAreaSeries3);

{% endhighlight %}

{% endtabs %}

![StackedArea chart type in Xamarin.Forms](charttypes_images/charttypes_img4.png)

## 100% Stacked Area Chart

To render a [`100% Stacked Area chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/stacked-area-100-chart), create an instance of [`StackingArea100Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingArea100Series.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the 100% stacked area appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingSeriesBase.html#Syncfusion_SfChart_XForms_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingArea100Series ItemsSource ="{Binding Data1}" XBindingPath="Year" 
								 YBindingPath="Value"/>

	<chart:StackingArea100Series ItemsSource ="{Binding Data2}" XBindingPath="Year" 
								 YBindingPath="Value"/>

	<chart:StackingArea100Series ItemsSource ="{Binding Data3}" XBindingPath="Year" 
								 YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingArea100Series stackingArea100Series1 = new StackingArea100Series() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

StackingArea100Series stackingArea100Series2 = new StackingArea100Series() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

StackingArea100Series stackingArea100Series3 = new StackingArea100Series() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

chart.Series.Add(stackingArea100Series1);
chart.Series.Add(stackingArea100Series2);
chart.Series.Add(stackingArea100Series3);

{% endhighlight %}

{% endtabs %}

![StackingArea100 chart type in Xamarin.Forms](charttypes_images/charttypes_img5.png)

## Column Chart

To render a [`Column chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/column-chart), create an instance of [`ColumnSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ColumnSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ColumnSeries.html#Syncfusion_SfChart_XForms_ColumnSeries_StrokeColor) – used to change the stroke color of the series. 
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ColumnSeries.html#Syncfusion_SfChart_XForms_ColumnSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ColumnSeries.html#Syncfusion_SfChart_XForms_ColumnSeries_DataMarkerPosition) - used to position the data marker at [`Bottom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html), [`Top`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html) and [`Center`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html) of the rectangle. 
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ColumnSeries.html#Syncfusion_SfChart_XForms_ColumnSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ColumnSeries.html#Syncfusion_SfChart_XForms_ColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:ColumnSeries ItemsSource ="{Binding Data}" XBindingPath="Country" 
						YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Country", 
	YBindingPath = "Value" 
};
chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Column chart type in Xamarin.Forms](charttypes_images/charttypes_img6.png)

### Overlapped placement

By default, all the column series which has the same x and y axes are placed side by side in a chart. If you want place the series one over the other (overlapped), set the [`SideBySideSeriesPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_SideBySideSeriesPlacement) property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#) to false and configure the [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ColumnSeries.html#Syncfusion_SfChart_XForms_ColumnSeries_Width) property to differentiate the series. The following code snippet and screenshot illustrate the overlapped placement of column series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart x:Name="Chart" SideBySideSeriesPlacement="False" >
      . . .
    <chart:SfChart.Series>
      <chart:ColumnSeries ItemsSource="{Binding Data1}" Label="2014" XBindingPath="Month" YBindingPath="Year2014">
       
      </chart:ColumnSeries>
     <chart:ColumnSeries  Width="0.5" ItemsSource="{Binding Data2}" Label="2015" XBindingPath="Month" YBindingPath="Year2015" >
       
      </chart:ColumnSeries>
    </chart:SfChart.Series>
    . . .
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart()
  {
      SideBySideSeriesPlacement = false
  };
 chart.PrimaryAxis = new CategoryAxis();
 chart.SecondaryAxis = new NumericalAxis();
 ColumnSeries series1 = new ColumnSeries()
 {
                ItemsSource = view.Data1,
                XBindingPath = "Month",
                YBindingPath = "Year2014"
 };
 ColumnSeries series2 = new ColumnSeries()
 {
                ItemsSource = view.Data2,
                XBindingPath = "Month",
                YBindingPath = "Year2015",
                 Width="0.5"
 };

chart.Series.Add(series1);
chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Overlapped placement support in Xamarin.Forms Chart](charttypes_images/SideBySide-false.png)

## Histogram Chart

To render a [`Histogram chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/histogram-chart), create an instance of [`HistogramSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HistogramSeries.html), and add it to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

Histogram chart provides a visual display of large amount of data that are difficult to understand in a tabular or data grid form.

You can customize intervals using the [`Interval`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HistogramSeries.html#Syncfusion_SfChart_XForms_HistogramSeries_Interval) property and collapse the normal distribution curve using the [`ShowNormalDistributionCurve`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HistogramSeries.html#Syncfusion_SfChart_XForms_HistogramSeries_ShowNormalDistributionCurve) property.  You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HistogramSeries.html#Syncfusion_SfChart_XForms_HistogramSeries_StrokeColor) – used to change the stroke color of the series.
* [`CurveColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HistogramSeries.html#Syncfusion_SfChart_XForms_HistogramSeries_CurveColor) – used to change the color of the normal distribution curve.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HistogramSeries.html#Syncfusion_SfChart_XForms_HistogramSeries_DataMarkerPosition) - used to position the data marker at Bottom, Top and Center of the rectangle.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:HistogramSeries ItemsSource ="{Binding Data}" XBindingPath="XValue" 
						YBindingPath="YValue" Interval="20"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

HistogramSeries histogramSeries = new HistogramSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue",
	Interval = 20 
};
chart.Series.Add(histogramSeries);

{% endhighlight %}

{% endtabs %}

![Histogram chart type in Xamarin.Forms](charttypes_images/charttypes_img42.png)

## Range Column Chart

To render a [`Range Column chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/range-column-chart), create an instance of [`RangeColumnSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). 

Since the [`RangeColumnSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html) requires two Y values for a point, your data should contain high and low values. High and low value specifies the maximum and minimum range of the point. 

There are two ways you can provide data to RangeColumn chart,

1.You can use [`ChartDataPoint's`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint__ctor_System_IComparable_System_Double_System_Double_#) three parameter constructor to pass [`XValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_XValue), [`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_High) and [`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Low) values to  [`RangeColumnSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html),

{% highlight c# %}
[C#] 

SfChart chart = new SfChart();
...

ObservableCollection<ChartDataPoint> data = new ObservableCollection<ChartDataPoint>()
{    
	new ChartDataPoint("Jan", 7.6, 1.8),
	new ChartDataPoint("Feb", 10, 3),
	new ChartDataPoint("Mar", 7.5, 1.7),
	new ChartDataPoint("Apr", 7.8, 4.5),
	new ChartDataPoint("May", 11.4, 5),
	new ChartDataPoint("Jun", 10.1, 4.2),
};
	
RangeColumnSeries rangeColumnSeries = new RangeColumnSeries() 
{ 
	ItemsSource = data 
};
	
chart.Series.Add(rangeColumnSeries);

{% endhighlight %}


2.Or else you can use [`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeSeriesBase.html#Syncfusion_SfChart_XForms_RangeSeriesBase_High) and [`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeSeriesBase.html#Syncfusion_SfChart_XForms_RangeSeriesBase_Low) properties of [`RangeColumnSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html) to map the high and low values from custom object to chart. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:RangeColumnSeries ItemsSource ="{Binding Data}"
							 XBindingPath="Month"
							 High="Value1" 
							 Low="Value2"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}
   
SfChart chart = new SfChart();
...
   
RangeColumnSeries rangeColumnSeries = new RangeColumnSeries() 
{ 
	ItemsSource = Data,
	XBindingPath = "Month", 
	High = "Value1",
	Low = "Value2" 
};
chart.Series.Add(rangeColumnSeries);

{% endhighlight %}

{% endtabs %}

Following properties are used to customize the range column segment appearance,

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html#Syncfusion_SfChart_XForms_RangeColumnSeries_StrokeColor) – used to change the stroke color of the series.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html#Syncfusion_SfChart_XForms_RangeColumnSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html#Syncfusion_SfChart_XForms_RangeColumnSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RangeColumnSeries.html#Syncfusion_SfChart_XForms_RangeColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 

![RangeColumn chart type in Xamarin.Forms](charttypes_images/charttypes_img7.png)

## Stacked Column Chart

To render a [`Stacked Column chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/stacked-column-chart), create an instance of [`StackingColumnSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the stacked column segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingSeriesBase.html#Syncfusion_SfChart_XForms_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_DataMarkerPosition) - used to position the data marker at [`Bottom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html), [`Top`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html) and [`Center`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html) of the rectangle. 
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingColumnSeries ItemsSource ="{Binding Data1}" XBindingPath="Month" 
								YBindingPath="Value"/>

	<chart:StackingColumnSeries ItemsSource ="{Binding Data2}" XBindingPath="Month" 
								YBindingPath="Value"/>

	<chart:StackingColumnSeries ItemsSource ="{Binding Data3}" XBindingPath="Month" 
								YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingColumnSeries stackingColumnSeries1 = new StackingColumnSeries() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

StackingColumnSeries stackingColumnSeries2 = new StackingColumnSeries() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

StackingColumnSeries stackingColumnSeries3 = new StackingColumnSeries() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

chart.Series.Add(stackingColumnSeries1);
chart.Series.Add(stackingColumnSeries2);
chart.Series.Add(stackingColumnSeries3);

{% endhighlight %}

{% endtabs %}

![StackingColumn chart type in Xamarin.Forms](charttypes_images/charttypes_img8.png)

## 100% Stacked Column Chart

To render a [`100% Stacked Column chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/stacked-column-100-chart), create an instance of [`StackingColumn100Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumn100Series.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the series appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingSeriesBase.html#Syncfusion_SfChart_XForms_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_DataMarkerPosition) - used to position the data marker at [`Bottom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html), [`Top`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html) and [`Center`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DataMarkerPosition.html) of the rectangle. 
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_Spacing) -  used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingColumnSeries.html#Syncfusion_SfChart_XForms_StackingColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingColumn100Series ItemsSource ="{Binding Data1}" XBindingPath="Year" 
								   YBindingPath="Value"/>

	<chart:StackingColumn100Series ItemsSource ="{Binding Data2}" XBindingPath="Year" 
								   YBindingPath="Value"/>

	<chart:StackingColumn100Series ItemsSource ="{Binding Data3}" XBindingPath="Year" 
								   YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingColumn100Series stackingColumn100Series1 = new StackingColumn100Series() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

StackingColumn100Series stackingColumn100Series2 = new StackingColumn100Series() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "Year", 
	YBindingPath = "Value"  
};

StackingColumn100Series stackingColumn100Series3 = new StackingColumn100Series() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

chart.Series.Add(stackingColumn100Series1);
chart.Series.Add(stackingColumn100Series2);
chart.Series.Add(stackingColumn100Series3);

{% endhighlight %}

{% endtabs %}

![StackingColumn100 chart type in Xamarin.Forms Chart](charttypes_images/charttypes_img9.png)

## Bar Chart

To render a [`Bar chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/bar-chart), create an instance of [`BarSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BarSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the bar segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BarSeries.html#Syncfusion_SfChart_XForms_BarSeries_StrokeColor) – used to change the stroke color of the series.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BarSeries.html#Syncfusion_SfChart_XForms_BarSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BarSeries.html#Syncfusion_SfChart_XForms_BarSeries_DataMarkerPosition) - used to position the data marker at left, right and center of the rectangle. 
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BarSeries.html#Syncfusion_SfChart_XForms_BarSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BarSeries.html#Syncfusion_SfChart_XForms_BarSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:BarSeries ItemsSource ="{Binding Data}" XBindingPath="Year"
					 YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

BarSeries barSeries = new BarSeries () 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};
chart.Series.Add(barSeries);

{% endhighlight %}

{% endtabs %}

![Bar chart type in Xamarin.Forms](charttypes_images/charttypes_img10.png)

## Stacked Bar Chart

To render a [`Stacked Bar chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/stacked-bar-chart), create an instance of [`StackingBarSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the stacked bar segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingSeriesBase.html#Syncfusion_SfChart_XForms_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_DataMarkerPosition) - used to position the data marker at left, right and center of the rectangle.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_Spacing) - used to change the spacing between two segments.The default value of spacing is 0 and the value ranges from 0 to 1. Here 1 and 0 corresponds to 100% and 0% of available space respectively. 
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_Width) - used to change the width of the rectangle. The default value of width is 0.8 and the value ranges from 0 to 1. Here 1 and 0 corresponds to 100% and 0% of available width respectively. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingBarSeries ItemsSource ="{Binding Data1}" XBindingPath="Month" 
							 YBindingPath="Value"/>

	<chart:StackingBarSeries ItemsSource ="{Binding Data2}" XBindingPath="Month" 
 							 YBindingPath="Value"/>

	<chart:StackingBarSeries ItemsSource ="{Binding Data3}" XBindingPath="Month" 
							 YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingBarSeries stackingBarSeries1 = new StackingBarSeries() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

StackingBarSeries stackingBarSeries2 = new StackingBarSeries() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

StackingBarSeries stackingBarSeries3 = new StackingBarSeries() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "Month", 
	YBindingPath = "Value" 
};

chart.Series.Add(stackingBarSeries1);
chart.Series.Add(stackingBarSeries2);
chart.Series.Add(stackingBarSeries3);

{% endhighlight %}

{% endtabs %}

![StackingBar chart type in Xamarin.Forms](charttypes_images/charttypes_img11.png)

## 100% Stacked Bar Chart

To render a [`100% Stacked Bar chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/stacked-bar-100-chart), create an instance of [`StackingBar100Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBar100Series.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the series appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingSeriesBase.html#Syncfusion_SfChart_XForms_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html#Syncfusion_SfChart_XForms_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_DataMarkerPosition) - used to position the data marker at left, right and center of the rectangle.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_Spacing) - used to change the spacing between two segments.The default value of spacing is 0 and the value ranges from 0 to 1. Here 1 and 0 corresponds to 100% and 0% of available space respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StackingBarSeries.html#Syncfusion_SfChart_XForms_StackingBarSeries_Width) - used to change the width of the rectangle. The default value of width is 0.8 and the value ranges from 0 to 1. Here 1 and 0 corresponds to 100% and 0% of available width respectively. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:StackingBar100Series ItemsSource ="{Binding Data1}" XBindingPath="Year" 
								YBindingPath="Value"/>

	<chart:StackingBar100Series ItemsSource ="{Binding Data2}" XBindingPath="Year" 
								YBindingPath="Value"/>

	<chart:StackingBar100Series ItemsSource ="{Binding Data3}" XBindingPath="Year" 
								YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StackingBar100Series stackingBar100Series1 = new StackingBar100Series() 
{ 
	ItemsSource = Data1, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

StackingBar100Series stackingBar100Series2 = new StackingBar100Series() 
{ 
	ItemsSource = Data2, 
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};

StackingBar100Series stackingBar100Series3 = new StackingBar100Series() 
{ 
	ItemsSource = Data3, 
	XBindingPath = "Year", 
	YBindingPath = "Value"  
};

chart.Series.Add(stackingBar100Series1);
chart.Series.Add(stackingBar100Series2);
chart.Series.Add(stackingBar100Series3);

{% endhighlight %}

{% endtabs %}

![StackingBar100 chart type in Xamarin.Forms](charttypes_images/charttypes_img12.png)

## Spline Chart

To render a [`Spline chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/spline-chart), create an instance of [`SplineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the spline segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:SplineSeries ItemsSource ="{Binding Data}" XBindingPath="Month"
	  					YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

SplineSeries splineSeries = new SplineSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value"  
};
chart.Series.Add(splineSeries);

{% endhighlight %}

{% endtabs %}

![Spline chart type in Xamarin.Forms](charttypes_images/charttypes_img13.png)

### Dashed Lines

[`StrokeDashArray`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineSeries.html#Syncfusion_SfChart_XForms_SplineSeries_StrokeDashArray) property of the [`SplineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineSeries.html) is used to render spline series with dashes.

{% tabs %} 

{% highlight xaml %}

<chart:SplineSeries ItemsSource ="{Binding Data}" XBindingPath="Month" YBindingPath="Value">
    <chart:SplineSeries.StrokeDashArray>
        <x:Array Type="{x:Type x:Double}">
            <sys:Double>5</sys:Double>
            <sys:Double>6</sys:Double>
        </x:Array>
    </chart:SplineSeries.StrokeDashArray>
</chart:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries splineSeries = new SplineSeries()
{
    ItemsSource = Data,
    XBindingPath = "Month",
    YBindingPath = "Value"
};

splineSeries.StrokeDashArray = new double[2] { 5, 6 };
chart.Series.Add(splineSeries);

{% endhighlight %}

{% endtabs %}

### Spline Rendering Types

[`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineSeries.html#Syncfusion_SfChart_XForms_SplineSeries_SplineType) allows you to change the spline curve in series. 
The following types are used in [`SplineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineSeries.html) as 

 * Natural
 * Monotonic
 * Cardinal
 * Clamped

By default [`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html) value is [`Natural`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html).

The following code shows how to set the [`SplineType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html) value as [`Cardinal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)

{% tabs %}

{% highlight xaml%}

<chart:SfChart>
...

	<chart:SplineSeries ItemsSource ="{Binding Data}" XBindingPath="Month"
	  					YBindingPath="Value" SplineType="Cardinal" />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

SplineSeries splineSeries = new SplineSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value",
	SplineType = SplineType.Cardinal
};
chart.Series.Add(splineSeries);

{% endhighlight %}

{% endtabs %}

[`Cardinal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html) 

![SplineType support in Xamarin.Forms Chart](charttypes_images/CardinalSplineType.png)

[`Monotonic`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)

![SplineType support in Xamarin.Forms Chart](charttypes_images/MonotonicSplineType.png)

[`Clamped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SplineType.html)

![SplineType support in Xamarin.Forms Chart](charttypes_images/ClampedSplineType.png)

## Step Line Chart

To render a [`Step Line chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/step-line-chart), create an instance of [`StepLineSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.StepLineSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of
[`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the spline segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.Series>

	<chart:StepLineSeries ItemsSource="{Binding Data}" XBindingPath="Month"
	   					  YBindingPath="Value" />
	
</chart:SfChart.Series>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

StepLineSeries stepLine = new StepLineSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value"
};
chart.Series.Add(stepLine);

{% endhighlight %}

{% endtabs %}

![StepLine chart type in Xamarin.Forms](charttypes_images/stepline.png)

## Bubble Chart

To render a [`Bubble chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/bubble-chart), create an instance of [`BubbleSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). 

Bubble chart requires 3 fields (X, Y and Size) to plot a point. Here [`Size`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html#Syncfusion_SfChart_XForms_BubbleSeries_Size) is used to specify the size of each bubble segment. 

There are two ways you can provide data to bubble chart,

1.You can use [ChartDataPoint's](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint__ctor_System_IComparable_System_Double_System_Double_#) three parameter constructor to pass [`XValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_XValue), [`YValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_YValue) and [`Size`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Size) values to  [`BubbleSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html),

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

ObservableCollection<ChartDataPoint> data = new ObservableCollection<ChartDataPoint>()
{    
	new ChartDataPoint(64, 14.4, 20),
	new ChartDataPoint(71, 2, 15),
	new ChartDataPoint(74, 7, 30),
	new ChartDataPoint(80, 4, 22),
	new ChartDataPoint(82, 10.3, 28),
	new ChartDataPoint(94, 1, 8),
	new ChartDataPoint(96, 6, 18),
	new ChartDataPoint(98, 12.3, 28),                       
};
   
BubbleSeries bubbleSeries = new BubbleSeries() 
{ 
	ItemsSource = data 
};

chart.Series.Add(bubbleSeries);

{% endhighlight %}


2.Or else you can use [`YBindingPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.XyDataSeries.html#Syncfusion_SfChart_XForms_XyDataSeries_YBindingPath) and [`Size`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html#Syncfusion_SfChart_XForms_BubbleSeries_Size) properties of [`BubbleSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html) to map the Y value and size from custom object to chart. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:BubbleSeries ItemsSource ="{Binding Data}"
						XBindingPath="XValue"
						YBindingPath="YValue" 
						Size="Size"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

BubbleSeries bubbleSeries = new BubbleSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "XValue", 
	YBindingPath = "YValue", 
	Size = "Size” 
};
chart.Series.Add(bubbleSeries);

{% endhighlight %}

{% endtabs %}

Following properties are used to customize the bubble segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html#Syncfusion_SfChart_XForms_BubbleSeries_StrokeColor) – used to change the stroke color of the series.
* [`MinimumRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html#Syncfusion_SfChart_XForms_BubbleSeries_MinimumRadius) – used to change the minimum size of the series.
* [`MaximumRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BubbleSeries.html#Syncfusion_SfChart_XForms_BubbleSeries_MaximumRadius) – used to change the maximum size of the series.

![Bubble chart type in Xamarin.Forms](charttypes_images/charttypes_img16.png)

## Scatter Chart	

To render a [`Scatter chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/scatter-chart), create an instance of [`ScatterSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ScatterSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the scatter segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ScatterSeries.html#Syncfusion_SfChart_XForms_ScatterSeries_StrokeColor) – used to change the stroke color of the series.
* [`ScatterWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ScatterSeries.html#Syncfusion_SfChart_XForms_ScatterSeries_ScatterWidth) – used to change the width of the series.
* [`ScatterHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ScatterSeries.html#Syncfusion_SfChart_XForms_ScatterSeries_ScatterHeight) – used to change the height of the series.
* [`ShapeType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ScatterSeries.html#Syncfusion_SfChart_XForms_ScatterSeries_ShapeType) - used to change the rendering shape of scatter series. The available shapes are [`Cross`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Diamond`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Ellipse`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Hexagon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`InvertedTriangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Pentagon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Plus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html) and [`Triangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html).

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:ScatterSeries ScatterHeight="15"
	ScatterWidth="15"
	ShapeType="Ellipse"
	ItemsSource ="{Binding Data}" 
	XBindingPath="Year"
	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ScatterSeries scatterSeries = new ScatterSeries ()
{ 
	ItemsSource = Data, 	
	ScatterHeight = 15, 
	ScatterWidth = 15, 
	ShapeType = ChartScatterShapeType.Ellipse,
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};
chart.Series.Add(scatterSeries);

{% endhighlight %}

{% endtabs %}

![Scatter chart type in Xamarin.Forms](charttypes_images/charttypes_img17.png)

## Fast Scatter Chart

The [`FastScatterSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastScatterSeries.html) is a special kind of scatter series that renders a collection with a huge number of data points. You can use the following properties to customize the appearance of a fast scatter point.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) – used to control the transparency of chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastScatterSeries.html#Syncfusion_SfChart_XForms_FastScatterSeries_StrokeColor) – used to change the stroke color of series.
* [`ScatterWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastScatterSeries.html#Syncfusion_SfChart_XForms_FastScatterSeries_ScatterWidth) –  used to change the width of series.
* [`ScatterHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastScatterSeries.html#Syncfusion_SfChart_XForms_FastScatterSeries_ScatterHeight) – used to change the height of series.
* [`ShapeType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastScatterSeries.html#Syncfusion_SfChart_XForms_FastScatterSeries_ShapeType) – used to change the rendering shape of fast scatter series. The available shapes are [`Cross`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Diamond`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Ellipse`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Hexagon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`InvertedTriangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Pentagon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Plus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html), [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html) and [`Triangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartScatterShapeType.html).
* [`EnableAntiAliasing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastScatterSeries.html#Syncfusion_SfChart_XForms_FastScatterSeries_EnableAntiAliasing) – Enables or disables the smoothness of series. Default value of [`EnableAntiAliasing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FastScatterSeries.html#Syncfusion_SfChart_XForms_FastScatterSeries_EnableAntiAliasing) property is true.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:FastScatterSeries ScatterHeight="15"
	ScatterWidth="15"
	ShapeType="Ellipse"
	ItemsSource ="{Binding Data}" 
	XBindingPath="Year"
	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

FastScatterSeries fastScatterSeries = new FastScatterSeries ()
{ 
	ItemsSource = Data, 	
	ScatterHeight = 15, 
	ScatterWidth = 15, 
	ShapeType = ChartScatterShapeType.Ellipse,
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};
chart.Series.Add(fastScatterSeries);

{% endhighlight %}

{% endtabs %}

![Fast Scatter chart type in Xamarin.Forms](charttypes_images/charttypes_img17.png)

## OHLC Chart

To render an [`OHLC chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/ohlc-chart), create an instance of [`HiLoOpenCloseSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HiLoOpenCloseSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

OHLC chart requires five values (X, Open, High, Low and Close) to plot a point. 

There are two ways you can provide data to an OHLC chart,

1.You can use [`ChartDataPoint's`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint__ctor_System_IComparable_System_Double_System_Double_System_Double_System_Double_#) five parameter constructor to pass [`XValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_XValue), [`Open`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Open), [`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_High), [`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Low), [`Close`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Close) , [`Volume`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Volume) values to [`HiLoOpenCloseSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HiLoOpenCloseSeries.html) and [`technical indicators`](https://help.syncfusion.com/xamarin/sfchart/technicalindicators#accumulation-distribution-indicator).

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

ObservableCollection<ChartDataPoint> data = new ObservableCollection<ChartDataPoint>()
{
	new ChartDataPoint("2010", 873.8, 878.85, 855.5, 860.5),
	new ChartDataPoint("2011", 861, 868.4, 835.2, 843.45),
	new ChartDataPoint("2012", 846.15, 853, 838.5, 847.5),
	new ChartDataPoint("2013", 846, 860.75, 841, 855),
	new ChartDataPoint("2014", 841, 845, 827.85, 838.65)
};
	
HiLoOpenCloseSeries hiLoOpenCloseSeries = new HiLoOpenCloseSeries() 
{ 
	ItemsSource = data
};
	
chart.Series.Add(hiLoOpenCloseSeries);

{% endhighlight %}

2.Or else you can use [`Open`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_Open),[`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_High),[`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_Low) and [`Close`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_Close) properties of [`HiLoOpenCloseSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HiLoOpenCloseSeries.html) to map Open, High, Low and Close values from custom object to chart.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:HiLoOpenCloseSeries ItemsSource ="{Binding Data}" XBindingPath="Year" 
				High="Value1" Low="Value2"
				Open="Value3" Close="Value4"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

HiLoOpenCloseSeries hiLoOpenCloseSeries = new HiLoOpenCloseSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	Open = "Value1", 
	High = "Value2", 
	Low = "Value3", 
	Close = "Value4" 
};
chart.Series.Add(hiLoOpenCloseSeries);

{% endhighlight %}

{% endtabs %}

You can use the following properties to customize the [`HiLoOpenCloseSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HiLoOpenCloseSeries.html) segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HiLoOpenCloseSeries.html#Syncfusion_SfChart_XForms_HiLoOpenCloseSeries_Spacing) - used to change the spacing between two segments.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.HiLoOpenCloseSeries.html#Syncfusion_SfChart_XForms_HiLoOpenCloseSeries_Width) - used to change the width of the rectangle.

![HiLoOpenClose chart type in Xamarin.Forms](charttypes_images/charttypes_img18.png)

### Bull and Bear Color	

In OHLC chart, [`BullFillColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_BullFillColor) property is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and [`BearFillColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_BearFillColor) property is used to specify a fill color for the segments that indicates a decrease in stock price in the measured time interval.

{% tabs %} 

{% highlight xaml %}

<chart:HiLoOpenCloseSeries BearFillColor="Blue" 
			BullFillColor="Purple"
			ItemsSource ="{Binding Data}" 
			XBindingPath="Year" 
			High="Value1" 
			Low="Value2" 
			Open="Value3" 
			Close="Value4"/>

{% endhighlight %}

{% highlight c# %}

HiLoOpenCloseSeries hiLoOpenCloseSeries = new HiLoOpenCloseSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	Open = "Value1", 
	High = "Value2", 
	Low = "Value3", 
	Close = "Value4",
	BearFillColor = Color.Blue,
	BullFillColor = Color.Purple
};

{% endhighlight %}

{% endtabs %}

![Bull and bear Color support for financial series in Xamarin.Forms Chart](charttypes_images/charttypes_img19.png)

## Candle Chart

To render a [`Candle chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/candle-chart), create an instance of [`CandleSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CandleSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

Candle chart requires five values (X, Open, High, Low and Close) to plot a point. 

There are two ways you can provide data to an candle chart,

1.You can use [ChartDataPoint's](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint__ctor_System_IComparable_System_Double_System_Double_System_Double_System_Double_#) five parameter constructor to pass [`XValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_XValue), [`Open`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Open), [`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_High), [`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartDataPoint.html#Syncfusion_SfChart_XForms_ChartDataPoint_Low) and close values to  [`CandleSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CandleSeries.html),

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

ObservableCollection<ChartDataPoint> data = new ObservableCollection<ChartDataPoint>()
{
	new ChartDataPoint("2010", 873.8, 878.85, 855.5, 860.5),
	new ChartDataPoint("2011", 861, 868.4, 835.2, 843.45),
	new ChartDataPoint("2012", 846.15, 853, 838.5, 847.5),
	new ChartDataPoint("2013", 846, 860.75, 841, 855),
	new ChartDataPoint("2014", 841, 845, 827.85, 838.65)
};

CandleSeries candleSeries = new CandleSeries () 
{ 
	ItemsSource = data
};

chart.Series.Add(candleSeries);

{% endhighlight %}

2.Or else you can use [`Open`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_Open),[`High`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_High),[`Low`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_Low) and [`Close`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_Close) property of [`CandleSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CandleSeries.html) to map Open, High, Low and Close values from custom object to chart.

{% tabs %} 

{% highlight xaml %}  

<chart:SfChart>
...

	<chart:CandleSeries ItemsSource ="{Binding Data}"
	XBindingPath="Year" 
	High="Value1"
	Low="Value2"
	Open="Value3"
	Close="Value4"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %} 

SfChart chart = new SfChart();
...

CandleSeries candleSeries = new CandleSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	Open = "Value1", 
	High = "Value2", 
	Low = "Value3", 
	Close = "Value4"
};
chart.Series.Add(candleSeries);

{% endhighlight %}

{% endtabs %}
   
You can use the following properties to customize the candle segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CandleSeries.html#Syncfusion_SfChart_XForms_CandleSeries_StrokeColor) – used to change the stroke color of the series.

![Candle chart type in Xamarin.Forms](charttypes_images/charttypes_img20.png)

### Bull and Bear Color

In Candle chart, [`BullFillColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_BullFillColor) property is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and [`BearFillColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FinancialSeriesBase.html#Syncfusion_SfChart_XForms_FinancialSeriesBase_BearFillColor) property is used to specify a fill color for the segments that indicates a decrease in stock price in the measured time interval.

{% tabs %} 

{% highlight xaml %}

<chart:CandleSeries BearFillColor="Blue"
	BullFillColor="Purple"
	ItemsSource ="{Binding Data}" 
	XBindingPath="Year"
	High="Value1"
	Low="Value2"
	Open="Value3"
	Close="Value4" />

{% endhighlight %}

{% highlight c# %}

CandleSeries candleSeries = new CandleSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	Open = "Value1", 
	High = "Value2", 
	Low = "Value3", 
	Close = "Value4",
	BearFillColor = Color.Blue,
	BullFillColor = Color.Purple
};

{% endhighlight %}

{% endtabs %}

![Bull and bear Color support for financial series in Xamarin.Forms Chart](charttypes_images/charttypes_img21.png)

### EnableSolidCandles

In Candle Series, [`EnableSolidCandles`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CandleSeries.html#Syncfusion_SfChart_XForms_CandleSeries_EnableSolidCandles) property is used to specify whether the candle segment should be filled or hollow. The default value of this property is false.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
    ...
    <chart:SfChart.Series>

        <chart:CandleSeries ItemsSource="{Binding FinancialData}" EnableSolidCandles="True"/>

    </chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart()

{
     ...
     Series =
     {
         new CandleSeries()
         {
               ItemsSource = viewModel.FinancialData,
   
               EnableSolidCandles = true,
         }
     }
};

{% endhighlight %}

{% endtabs %}

## Radar Chart

To render a [`Radar chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/radar-chart), create an instance of [`RadarSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.RadarSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).  

### Draw type

[`DrawType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_DrawType) property is used to specify the radar series rendering type. Following are the two options you can set to this property,

* [`Line`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesDrawType.html) – data points are visualized using line series.
* [`Area`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesDrawType.html) – data points are visualized using area series.

{% tabs %}
{% highlight xaml %}
<chart:RadarSeries ItemsSource="{Binding RadarData}" DrawType="Line"
          XBindingPath="Name" YBindingPath="Value"  />

{% endhighlight %}
{% highlight c# %}
RadarSeries radar = new RadarSeries ();
radar.ItemsSource = viewModel.RadarData;
radar.XBindingPath = "Name";
radar.YBindingPath = "Value";
radar.DrawType = PolarRadarSeriesDrawType.Line;

{% endhighlight %}
{% endtabs %}

![Draw type support for radar series in Xamarin.Forms Chart](ChartTypes_images/Radar.png)

### Customize the appearance

You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_StrokeColor) – used to change the stroke color of the series when draw types is set to `Area`
* [`StrokeDashArray`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_StrokeDashArray) – used to render lines with dashes when the draw type is set to `Line`.

{% tabs %}
{% highlight xaml %}
<chart:RadarSeries ItemsSource="{Binding RadarData}" Color="Aqua" StrokeColor="Blue" 
StrokeWidth="3" XBindingPath="Name" YBindingPath="Value"  />

{% endhighlight %}
{% highlight c# %}
RadarSeries radar = new RadarSeries ();
radar.ItemsSource = viewModel.RadarData;
radar.XBindingPath = "Name";
radar.YBindingPath = "Value";
radar.Color = Color.Aqua;
radar.StrokeColor = Color.Blue;
radar.StrokeWidth = 3;

{% endhighlight %}
{% endtabs %}

![Customizing the appearance of radar series in Xamarin.Forms Chart](ChartTypes_images/RadarCustomization.png)

### Closed

[`Closed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_IsClosed) property is used to determine, whether to connect the first and last data point of the series. By default, the property is set to `true`.

{% tabs %}
{% highlight xaml %}
<chart:RadarSeries ItemsSource="{Binding RadarData}" IsClosed="false"
         XBindingPath="Name" YBindingPath="Value"  />

{% endhighlight %}
{% highlight c# %}
RadarSeries radar = new RadarSeries ();
radar.ItemsSource = viewModel.RadarData;
radar.XBindingPath = "Name";
radar.YBindingPath = "Value";
radar.IsClosed = false;

{% endhighlight %}
{% endtabs %}

![Closed radar series in Xamarin.Forms Chart](ChartTypes_images/RadarClosed.png)

### Radar start angle for primary axis

The start position of the radar series can be set by using [`PolarAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_PolarAngle) property of axis. Default value of [`PolarAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_PolarAngle) property is [`Rotate270`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartPolarAngle.html). [`PolarAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_PolarAngle) property can be set for primary axis, secondary axis, or both axes

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

    <chart:CategoryAxis PolarAngle = “Rotate0”/>

</chart:SfChart.PrimaryAxis >
 
<chart:SfChart.SecondaryAxis>

    <chart:NumericalAxis/>

</chart:SfChart.SecondaryAxis >
 
{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis  = new CategoryAxis(){ PolarAngle = ChartPolarAngle.Rotate0 };

chart.SecondaryAxis =  new NumericalAxis(); 

{% endhighlight %}

{% endtabs %}

![Radar start angle support for primary axis in Xamarin.Forms Chart](charttypes_images/radarangle_img1.png)

### Radar start angle for secondary axis

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

    <chart:CategoryAxis/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

    <chart:NumericalAxis  PolarAngle="Rotate0"/>

</chart:SfChart.SecondaryAxis>
 
{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis  = new CategoryAxis();

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

{% endtabs %}

![Radar start angle support for secondary axis in Xamarin.Forms Chart](charttypes_images/radarangle_img2.png)

### Radar start angle for both axis

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

    <chart:CategoryAxis PolarAngle = “Rotate0” />

</chart:SfChart.PrimaryAxis>
 
<chart:SfChart.SecondaryAxis>

    <chart:NumericalAxis  PolarAngle = “Rotate0” />

</chart:SfChart.SecondaryAxis >
 
{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis  = new CategoryAxis(){ PolarAngle = ChartPolarAngle.Rotate0 };

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

{% endtabs %}
![Radar start angle support for both axes in Xamarin.Forms Chart](charttypes_images/radarangle_img3.png)

## Polar Chart

To render a [`Polar chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/polar-chart), create an instance of [`PolarSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). 
 

### Draw type

[`DrawType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_DrawType) property is used to specify the polar series rendering type. Following are the two options you can set to this property,

* [`Line`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesDrawType.html) – data points are visualized using line series.
* [`Area`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesDrawType.html) – data points are visualized using area series.

{% tabs %}
{% highlight xaml %}
<chart:PolarSeries ItemsSource="{Binding PolarData}" DrawType="Line" 
XBindingPath="Name" YBindingPath="Value"  />

{% endhighlight %}
{% highlight c# %}
PolarSeries polar = new PolarSeries ();
polar.ItemsSource = viewModel.PolarData;
polar.XBindingPath = "Name";
polar.YBindingPath = "Value";
polar.DrawType = PolarRadarSeriesDrawType.Line;

{% endhighlight %}
{% endtabs %}

![Draw type support for polar series in Xamarin.Forms Chart](ChartTypes_images/Polar.png)

### Customize the appearance

You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_StrokeColor) – used to change the stroke color of the series when draw types is set to [`Area`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesDrawType.html)
* [`StrokeDashArray`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_StrokeDashArray) – used to render lines with dashes when the draw type is set to [`Line`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesDrawType.html)

{% tabs %}
{% highlight xaml %}
<chart:PolarSeries ItemsSource="{Binding PolarData}" StrokeColor="Blue" Color="Aqua" 
StrokeWidth="3" XBindingPath="Name" YBindingPath="Value"  />

{% endhighlight %}
{% highlight c# %}
PolarSeries polar = new PolarSeries ();
polar.ItemsSource = viewModel.PolarData;
polar.XBindingPath = "Name";
polar.YBindingPath = "Value";
polar.Color = Color.Aqua;
polar.StrokeColor = Color.Blue;
polar.StrokeWidth = 3;

{% endhighlight %}
{% endtabs %}

![Customizing the appearance of polar series in Xamarin.Forms Chart](ChartTypes_images/PolarCustomization.png)

### Closed

[`Closed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PolarRadarSeriesBase.html#Syncfusion_SfChart_XForms_PolarRadarSeriesBase_IsClosed) property is used to determine, whether to connect the first and last data point of the series. By default, the property is set to `true`.

{% tabs %}
{% highlight xaml %}
<chart:PolarSeries ItemsSource="{Binding PolarData}" IsClosed="false"
         XBindingPath="Name" YBindingPath="Value"  />

{% endhighlight %}
{% highlight c# %}
PolarSeries polar = new PolarSeries ();
polar.ItemsSource = viewModel.PolarData;
polar.XBindingPath = "Name";
polar.YBindingPath = "Value";
polar.IsClosed = false;

{% endhighlight %}
{% endtabs %}

![Closed polar series in Xamarin.Forms Chart](ChartTypes_images/PolarClosed.png)

### Polar start angle for primary axis

The start position of the polar series can be set by using [`PolarAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_PolarAngle) property of axis. Default value of [`PolarAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_PolarAngle) property is [`Rotate270`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartPolarAngle.html). [`PolarAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_PolarAngle) property can be set for primary axis, secondary axis, or both axes.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

    <chart:CategoryAxis PolarAngle = “Rotate0”/>

</chart:SfChart.PrimaryAxis >
 
<chart:SfChart.SecondaryAxis>

    <chart:NumericalAxis/>

</chart:SfChart.SecondaryAxis >
 
{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis  = new CategoryAxis(){ PolarAngle = ChartPolarAngle.Rotate0 };

chart.SecondaryAxis =  new NumericalAxis(); 

{% endhighlight %}

{% endtabs %}

![Polar start angle support for primary axis in Xamarin.Forms Chart](charttypes_images/polarangle_img1.png)

### Polar start angle for secondary axis

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

    <chart:CategoryAxis/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

    <chart:NumericalAxis PolarAngle="Rotate0"/>

</chart:SfChart.SecondaryAxis>
 
{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis  = new CategoryAxis();

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

{% endtabs %}

![Polar start angle support for secondary axis in Xamarin.Forms Chart](charttypes_images/polarangle_img2.png)

### Polar start angle for both axis

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

    <chart:CategoryAxis PolarAngle = “Rotate0” />

</chart:SfChart.PrimaryAxis >
 
<chart:SfChart.SecondaryAxis>

    <chart:NumericalAxis  PolarAngle = “Rotate0” />

</chart:SfChart.SecondaryAxis >
 
{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis  = new CategoryAxis(){ PolarAngle = ChartPolarAngle.Rotate0 };

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

{% endtabs %}

![Polar start angle support for both axes in Xamarin.Forms Chart](charttypes_images/polarangle_img3.png)

## Pie Chart

To render a [`Pie chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/pie-chart), create an instance of [`PieSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PieSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the pie segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_DataMarkerPosition) - used to change the position of data marker at [`Inside`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeriesDataMarkerPosition.html), [`Outside`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeriesDataMarkerPosition.html) or [`OutsideExtended`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeriesDataMarkerPosition.html).
* [`ConnectorLinePosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_ConnectorLinePosition) - used to change the position of the connector line at [`Auto`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ConnectorLinePosition.html) and [`Center`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ConnectorLinePosition.html).

N> ConnectorLinePosition provides better alignment to the straight connector lines with outside extended label position for the minimum number of data points. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:PieSeries ItemsSource ="{Binding Data}" XBindingPath="Expense"
	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

PieSeries pieSeries = new PieSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value" 
};
chart.Series.Add(pieSeries);

{% endhighlight %}

{% endtabs %}

![Pie chart type in Xamarin.Forms](charttypes_images/charttypes_img22.png)

### Changing the pie size

You can use [`CircularCoefficient`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_CircularCoefficient) property to change the diameter of the pie chart with respect to the plot area. It ranges from 0 to 1 and the default value is `0.8`.

{% tabs %} 

{% highlight xaml %}

<chart:PieSeries CircularCoefficient="0.5"
ItemsSource ="{Binding Data}"
XBindingPath="Expense" 
YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

PieSeries pieSeries = new PieSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value",
	CircularCoefficient = 0.5
};

{% endhighlight %}

{% endtabs %}

![Changing the pie size in Xamarin.Forms Chart](charttypes_images/charttypes_img23.png)

### Exploding a pie segment

You can explode a pie segment using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeIndex) property and specify the explode radius using [`ExplodeRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_ExplodeRadius) property of [`PieSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PieSeries.html).

{% tabs %} 

{% highlight xaml %}

<chart:PieSeries ExplodeIndex="1"
ItemsSource ="{Binding Data}"
XBindingPath="Expense" 
YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

PieSeries pieSeries = new PieSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value",
	ExplodeIndex = 1
};

{% endhighlight %}

{% endtabs %}

Also, the segments can be exploded by touch using [`ExplodeOnTouch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeOnTouch) property of [`PieSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PieSeries.html). Default value of this property is false.

![Exploding a pie segment support in Xamarin.Forms Chart](charttypes_images/charttypes_img24.png)

### Exploding all the segments

Using [`ExplodeAll`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeAll) property of [`PieSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PieSeries.html), you can explode all the pie segments.

{% tabs %} 

{% highlight xaml %}

<chart:PieSeries ExplodeAll="True" ItemsSource ="{Binding Data}" XBindingPath="Expense" 
				 YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

PieSeries pieSeries = new PieSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value",
	ExplodeAll = true	
};

{% endhighlight %}

{% endtabs %}

![Exploding all the segments of pie series in Xamarin.Forms Chart](charttypes_images/charttypes_img25.png)

### Sector of Pie

SfChart allows you to render all the data points/segments in semi-pie, quarter-pie or in any sector using [`StartAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_StartAngle) and [`EndAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_EndAngle) properties.

{% tabs %} 

{% highlight xaml %}

<chart:PieSeries StartAngle="180"
EndAngle="360"
ItemsSource ="{Binding Data}"
XBindingPath="Expense" 
YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

PieSeries pieSeries = new PieSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value",
	StartAngle = 180,
	EndAngle = 360
};

{% endhighlight %}

{% endtabs %}

![Sector support for pie series in Xamarin.Forms Chart](charttypes_images/charttypes_img26.png)

### Group small data points into “others”

The small segments in the pie chart can be grouped into “others” category using the [`GroupTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupTo) and [`GroupMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupMode) properties of PieSeries. The [`GroupMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupMode) property is used to specify the grouping type based on slice [`Angle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PieGroupMode.html), actual data point value, or [`Percentage`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PieGroupMode.html), and the [`GroupTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupTo) property is used to set the limit to group data points into a single slice. The grouped segment is labeled as “Others” in legend and toggled as any other segment. The default value of the [`GroupTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupTo) property is [`double.NAN`], and [`GroupMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupMode) property is Value.

## Doughnut Chart

To render a [`Doughnut chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/doughnut-chart), create an instance of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the doughnut segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_DataMarkerPosition) - used to change the position of data marker at [`Inside`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeriesDataMarkerPosition.html), [`Outside`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeriesDataMarkerPosition.html) or [`OutsideExtended`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeriesDataMarkerPosition.html).
* [`ConnectorLinePosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_ConnectorLinePosition) - used to change the position of the connector line at [`Auto`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ConnectorLinePosition.html) and [`Center`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ConnectorLinePosition.html).

N> ConnectorLinePosition provides better alignment to the straight connector lines with outside extended label position for the minimum number of data points. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:DoughnutSeries ItemsSource ="{Binding Data}"
	XBindingPath="Expense"
	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

DoughnutSeries doughnutSeries = new DoughnutSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value" 
};
chart.Series.Add(doughnutSeries);

{% endhighlight %}

{% endtabs %}

![Doughnut chart type in Xamarin.Forms](charttypes_images/charttypes_img27.png)

### Stacked doughnut

Doughnut segments can be separated as individual circles using the [`IsStackedDoughnut`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_IsStackedDoughnut) property. The following properties are used to customize the stacked doughnut chart:

* [`CapStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_CapStyle) - Specifies the shape of the start and end points of the circular segment. The supported values are `BothFlat`, `BothCurve`, `StartCurve`, and `EndCurve`. The default value of the this property is [`BothFlat`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutCapStyle.html).
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_Spacing) - Changes the spacing between two individual segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`MaximumValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_MaximumValue) - Represents the entire span of an individual circle. The default value of the this property is `double.NaN`.
* [`TrackColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_TrackColor) - Changes the color of the track area.
* [`TrackBorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_TrackBorderColor) - Changes the color of the track border.
* [`TrackBorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_TrackBorderWidth) - Changes the width of the track border.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

    <chart:DoughnutSeries ItemsSource ="{Binding Data}"
    XBindingPath="Expense"
    YBindingPath="Value"
    IsStackedDoughnut="true"
    CapStyle="BothCurve"
    Spacing=”0.4”
    MaximumValue=“100” />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

DoughnutSeries doughnutSeries = new DoughnutSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Expense", 
    YBindingPath = "Value",
    IsStackedDoughnut = true,
    CapStyle = DoughnutCapStyle.BothCurve,
    Spacing = 0.4,
    MaximumValue = 100 
};
chart.Series.Add(doughnutSeries);

{% endhighlight %}

{% endtabs %}

![Stacked doughnut support for doughnut series in Xamarin.Forms Chart](charttypes_images/stacked_doughnut.png)

### Changing Doughnut inner radius

You can change the doughnut chart inner radius using [`DoughnutCoefficient`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_DoughnutCoefficient) with respect to the plot area. It ranges from 0 to 1 and the default value is `0.4`.

{% tabs %} 

{% highlight xaml %}

<chart:DoughnutSeries DoughnutCoefficient="0.6"
ItemsSource ="{Binding Data}"
XBindingPath="Expense" 
YBindingPath="Value" />

{% endhighlight %}

{% highlight c# %}

DoughnutSeries doughnutSeries = new DoughnutSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value", 
	DoughnutCoefficient = 0.6 
};

{% endhighlight %}

{% endtabs %}

![DoughnutCoefficient support for doughnut series in Xamarin.Forms Chart](charttypes_images/charttypes_img28.png)

### Changing the doughnut size

You can use the [`CircularCoefficient`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_CircularCoefficient) property to change the diameter of the doughnut chart with respect to the plot area. It ranges from 0 to 1 and the default value is 0.8.

{% tabs %} 

{% highlight xaml %}

<chart:DoughnutSeries CircularCoefficient="0.5"
ItemsSource ="{Binding Data}"
XBindingPath="Expense" 
YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

DoughnutSeries doughnutSeries = new DoughnutSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value", 
	CircularCoefficient = 0.5 
};

{% endhighlight %}

{% endtabs %}

![CircularCoefficient support for doughnut series in Xamarin.Forms Chart](charttypes_images/charttypes_img29.png)

### Exploding a doughnut segment

Exploding a specific doughnut segment, you have to set the index to be exploded using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeIndex) property of the series.

{% tabs %} 

{% highlight xaml %}

<chart:DoughnutSeries ExplodeIndex="1" ItemsSource ="{Binding Data}" XBindingPath="Expense" 
					  YBindingPath="Value" />

{% endhighlight %}

{% highlight c# %}

DoughnutSeries doughnutSeries = new DoughnutSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value",
	ExplodeIndex = 1
};

{% endhighlight %}

{% endtabs %}

Also, the segments can be exploded by touch using [`ExplodeOnTouch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeOnTouch) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html). Default value of this property is false.

![Exploding a doughnut segment support in Xamarin.Forms Chart](charttypes_images/charttypes_img30.png)

### Exploding all the segments

To explode all the segments, you have to enable [`ExplodeAll`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeAll) property of the series.

{% tabs %} 

{% highlight xaml %}

<chart:DoughnutSeries ExplodeAll="True" ItemsSource ="{Binding Data}" XBindingPath="Expense" 
					  YBindingPath="Value" />

{% endhighlight %}

{% highlight c# %}

DoughnutSeries doughnutSeries = new DoughnutSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value",
	ExplodeAll = true
};

{% endhighlight %}

{% endtabs %}

![Exploding all the segments of doughnut series in Xamarin.Forms Chart](charttypes_images/charttypes_img31.png)

### Sector of Doughnut

[`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html) allows you to render all the data points/segments in semi-doughnut, quarter- doughnut or in any sector using [`StartAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_StartAngle) and [`EndAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_EndAngle) properties.

{% tabs %} 

{% highlight xaml %}

<chart:DoughnutSeries StartAngle="180" EndAngle="360" ItemsSource ="{Binding Data}" 
					  XBindingPath="Expense" YBindingPath="Value" />

{% endhighlight %}

{% highlight c# %}

DoughnutSeries doughnutSeries = new DoughnutSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Expense", 
	YBindingPath = "Value",
	StartAngle = 180,
	EndAngle = 360
};

{% endhighlight %}

{% endtabs %}

![Sector support for doughnut series in Xamarin.Forms Chart](charttypes_images/charttypes_img32.png)

### Group small data points into “others”

The small segments in the doughnut chart can be grouped into “others” category using the [`GroupTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupTo) and [`GroupMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupMode) properties of DoughnutSeries. The [`GroupMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupMode) property is used to specify the grouping type based on slice angle, actual data point value, or percentage, and the [`GroupTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupTo) property is used to set the limit to group data points into a single slice. The grouped segment is labeled as “Others” in legend and toggled as any other segment. The default value of the [`GroupTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupTo) property is [`double.NAN`], and [`GroupMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.CircularSeries.html#Syncfusion_SfChart_XForms_CircularSeries_GroupMode) property is Value.

### Add view to the center of doughnut chart

Any view can be added to the center of doughnut chart using the [`CenterView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_CenterView) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html). The binding context of the [`CenterView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_CenterView) will be the respective [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html).

{% tabs %} 

{% highlight xaml %}

<chart:DoughnutSeries>
...

	<chart:DoughnutSeries.CenterView>
		<StackLayout HorizontalOptions = "FillAndExpand" 
		             VerticalOptions = "FillAndExpand">
		...
		</StackLayout>
	</chart:DoughnutSeries.CenterView>
...
</chart:DoughnutSeries>
	
{% endhighlight %}

{% highlight C# %}

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
	...
}
doughnutSeries.CenterView = new Label() { Text = "CenterView" };

{% endhighlight %}

{% endtabs %}

![CenterView support for doughnut series in Xamarin.Forms Chart](charttypes_images/charttypes_img41.png)

### InnerRadius

The [`InnerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_InnerRadius) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html) is used to get only the inner radius. Using this [`InnerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_InnerRadius) value, you can provide [`CentreView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.DoughnutSeries.html#Syncfusion_SfChart_XForms_DoughnutSeries_CenterView) for series to avoid the view from being cropped outside the series.

## Pyramid Chart

To render a [`Pyramid chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/pyramid-chart), create an instance of [`PyramidSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PyramidSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the pyramid segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:PyramidSeries ItemsSource ="{Binding Data}" XBindingPath="Country"
	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

PyramidSeries pyramidSeries = new PyramidSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Country", 
	YBindingPath = "Value" 
};
chart.Series.Add(pyramidSeries);

{% endhighlight %}

{% endtabs %}

![Pyramid chart type in Xamarin.Forms](charttypes_images/charttypes_img33.png)

### Pyramid Mode

You can render the pyramid series as linear or surface mode. In linear mode, height of the pyramid segment is based on the Y value and in surface mode, area of the pyramid segment is based on the Y values. The default value of [`PyramidMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PyramidSeries.html#Syncfusion_SfChart_XForms_PyramidSeries_PyramidMode) property is [`Linear`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartPyramidMode.html).

{% tabs %} 

{% highlight xaml %}

<chart:PyramidSeries ItemsSource ="{Binding Data}" PyramidMode="Surface" XBindingPath="Country" 
					 YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

PyramidSeries pyramidSeries = new PyramidSeries ()
{ 
	ItemsSource = Data, 
	XBindingPath = "Country", 
	YBindingPath = "Value",
	PyramidMode = ChartPyramidMode.Surface 
};

{% endhighlight %}

{% endtabs %}

![Pyramid mode support in Xamarin.Forms Chart](charttypes_images/charttypes_img34.png)

### Gap between the segments

You can control the gap between the two segments using [`GapRatio`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.TriangularSeries.html#Syncfusion_SfChart_XForms_TriangularSeries_GapRatio) property. Its ranges from 0 to 1.

{% tabs %} 

{% highlight xaml %}

<chart:PyramidSeries ItemsSource ="{Binding Data}" GapRatio="0.1"
XBindingPath="Country" 
YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

PyramidSeries pyramidSeries = new PyramidSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Country", 
	YBindingPath = "Value",
	GapRatio = 0.1
};

{% endhighlight %}

{% endtabs %}

![Gap between the pyramid segments support in Xamarin.Forms Chart](charttypes_images/charttypes_img35.png)

### Exploding a pyramid segment

You can explode a pyramid segment using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeIndex) property, and [`ExplodeOffset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.TriangularSeries.html#Syncfusion_SfChart_XForms_TriangularSeries_ExplodeOffset) property is used to specify the exploded segment’s distance.

{% tabs %} 

{% highlight xaml %}

<chart:PyramidSeries ItemsSource ="{Binding Data}" ExplodeIndex="2"
XBindingPath="Country" 
YBindingPath="Value" />

{% endhighlight %}

{% highlight c# %}

PyramidSeries pyramidSeries = new PyramidSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Country", 
	YBindingPath = "Value",
	ExplodeIndex = 2
};

{% endhighlight %}

Also, the segments can be exploded by touch using [`ExplodeOnTouch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeOnTouch) property of [`PyramidSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.PyramidSeries.html). Default value of this property is false.

{% endtabs %}

![Exploding a pyramid segment support in Xamarin.Forms Chart](charttypes_images/charttypes_img36.png)

## Funnel Chart

To render a [`Funnel chart`](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts/chart-types/funnel-chart), create an instance of [`FunnelSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FunnelSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the funnel segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) – used to change the color of the series.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Opacity) - used to control the transparency of the chart series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:FunnelSeries ItemsSource ="{Binding Data}" XBindingPath="Status"
	YBindingPath="Value"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

FunnelSeries funnelSeries = new FunnelSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Status", 
	YBindingPath = "Value" 
};
chart.Series.Add(funnelSeries);

{% endhighlight %}

{% endtabs %}

![Funnel chart type in Xamarin.Forms](charttypes_images/charttypes_img37.png)

### Gap between the segments

You can control the gap between the two segments using [`GapRatio`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.TriangularSeries.html#Syncfusion_SfChart_XForms_TriangularSeries_GapRatio) property. Its ranges from 0 to 1.

{% tabs %} 

{% highlight xaml %}

<chart:FunnelSeries ItemsSource ="{Binding Data}" GapRatio="0.1"
XBindingPath="Year" 
YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

FunnelSeries funnelSeries = new FunnelSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	YBindingPath = "Value",
	GapRatio = 0.1
};

{% endhighlight %}

{% endtabs %}

![Gap between the funnel segments support in Xamarin.Forms Chart](charttypes_images/charttypes_img38.png)

### Exploding a funnel segment

You can explode a pyramid segment using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeIndex) property and [`ExplodeOffset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.TriangularSeries.html#Syncfusion_SfChart_XForms_TriangularSeries_ExplodeOffset) property is used to specify the exploded segment’s distance.

{% tabs %} 

{% highlight xaml %}

<chart:FunnelSeries ItemsSource ="{Binding Data}" ExplodeIndex="1"
XBindingPath="Status" 
YBindingPath="Value" />

{% endhighlight %}

{% highlight c# %}

FunnelSeries funnelSeries = new FunnelSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Status", 
	YBindingPath = "Value", 
	ExplodeIndex = 1 
};

{% endhighlight %}

{% endtabs %}

Also, the segments can be exploded by touch using [`ExplodeOnTouch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.AccumulationSeries.html#Syncfusion_SfChart_XForms_AccumulationSeries_ExplodeOnTouch) property of [`FunnelSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FunnelSeries.html). Default value of this property is false.

![Exploding a funnel segment support in Xamarin.Forms Chart](charttypes_images/charttypes_img39.png)

### Changing the minimum width of the funnel

You can change the minimum width of the funnel neck using [`MinWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FunnelSeries.html#Syncfusion_SfChart_XForms_FunnelSeries_MinWidth) property of [`FunnelSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.FunnelSeries.html). Default value of minWidth is `40`.

{% tabs %} 

{% highlight xaml %}

<chart:FunnelSeries ItemsSource ="{Binding Data}" MinWidth="20"
XBindingPath="Year" 
YBindingPath="Value"/>

{% endhighlight %}

{% highlight c# %}

FunnelSeries funnelSeries = new FunnelSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Year", 
	YBindingPath = "Value",
	MinWidth = 20 
};

{% endhighlight %}

{% endtabs %}

![Minimum width support for funnel series in Xamarin.Forms Chart](charttypes_images/charttypes_img40.png)

## Waterfall Chart

[`WaterfallSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.WaterfallSeries.html) clarifies the cumulative effect of a set of provided positive and negative values. The series is represented by a rectangle and a connector between the rectangles. 

* [`SummaryBindingPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.WaterfallSeries.html#Syncfusion_SfChart_XForms_WaterfallSeries_SummaryBindingPath) – Gets or sets the string value that indicates the sum of previous segments in series.
* [`SummarySegmentColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.WaterfallSeries.html#Syncfusion_SfChart_XForms_WaterfallSeries_SummarySegmentColor) – Changes the color of summary segment in series.
* [`NegativeSegmentColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.WaterfallSeries.html#Syncfusion_SfChart_XForms_WaterfallSeries_NegativeSegmentColor) – Changes the color of negative segment in series.
* [`AllowAutoSum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.WaterfallSeries.html#Syncfusion_SfChart_XForms_WaterfallSeries_AllowAutoSum) – Enables or disables the segment that has been drawn based on the sum value of previous segments. By default, the value of this property is true. When disabling this property, it renders the segment by using the y-value of provided ItemsSource collection.
* [`ShowConnectorLine`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.WaterfallSeries.html#Syncfusion_SfChart_XForms_WaterfallSeries_ShowConnectorLine) – Enables or disables the connector line of series. By default, value of this property is true.
* [`ConnectorLineStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.WaterfallSeries.html#Syncfusion_SfChart_XForms_WaterfallSeries_ConnectorLineStyle) – Customizes the appearance of connector line style.

{% tabs %}

{% highlight xaml %}

<chart:WaterfallSeries ItemsSource="{Binding RevenueDetails}" 
XBindingPath="Category"
YBindingPath="Value" 
AllowAutoSum="True"	
SummaryBindingPath="IsSummary"   
NegativeSegmentColor="#F14C72" 
SummarySegmentColor="#8C8C8C" 
ShowConnectorLine="True">
</chart:WaterfallSeries>

{% endhighlight %}

{% highlight c# %}

WaterfallSeries waterfallSeries = new WaterfallSeries()
{
	ItemsSource = RevenueDetails,
	XBindingPath = "Category",
	YBindingPath = "Value",
	AllowAutoSum = true,
	SummaryBindingPath = "IsSummary",
	NegativeSegmentColor = Color.FromHex("#F14C72"),
	SummarySegmentColor = Color.FromHex("#8C8C8C"),
	ShowConnectorLine = true
};

chart.Series.Add(waterfallSeries);

{% endhighlight %}

{% endtabs %}

![Waterfall chart type in Xamarin.Forms](charttypes_images/Waterfall.png)

## Box and Whisker Chart

BoxAndWhiskerSeries plots a combination of rectangles and lines to show the distribution of data sets. To render a box and whisker(box plot) chart, create an instance of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html). You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_Color) - used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSeries.html#Syncfusion_SfChart_XForms_ChartSeries_StrokeWidth) - used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_StrokeColor) - used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 corresponds to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 corresponds to 100% and 0% of the available width, respectively.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:BoxAndWhiskerSeries ItemSource ="{Binding Data"} XBindingPath="Department" 
                               YBindingPath="Ages" 
                               ShowMedian="True" />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Department", 
    YBindingPath = "Ages",
    ShowMedian = true;
};
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

{% endtabs %}

![BoxAndWhiskerSeries chart type in Xamarin.Forms Chart](charttypes_images/BoxAndWhisker_Exclusive_Median.png)

### Customize the series box mode

The series box plotting mode can be changed using the [`BoxPlotMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_BoxPlotMode) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html). The plotting mode of series can be calculated as follows:

* [`Exclusive`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxPlotMode.html) - The quartile values are calculated using the formula (N+1) * P (N count, P percentile), and their index value starts from 1 in the list.
* [`Inclusive`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxPlotMode.html) - The quartile values are calculated using the formula (N−1) * P (N count, P percentile), and their index value starts from 0 in the list.
* [`Normal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxPlotMode.html) - The quartile values are calculated by splitting the list and getting the median values.

By default, [`BoxPlotMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_BoxPlotMode) value is [`Exclusive`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxPlotMode.html). 

The following code shows how to set the [`BoxPlotMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_BoxPlotMode) value as [`Inclusive`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxPlotMode.html).

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:BoxAndWhiskerSeries ItemSource ="{Binding Data"} XBindingPath="Department" 
                               YBindingPath="Ages" 
                               BoxPlotMode="Inclusive"
                               ShowMedian="True" />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Department", 
    YBindingPath = "Ages",
    BoxPlotMode = BoxPlotMode.Inclusive,
    ShowMedian = true
};
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

{% endtabs %}

![BoxPlotMode support for BoxAndWhiskerSeries in Xamarin.Forms Chart](charttypes_images/BoxAndWhisker_Inclusive.png)

### ShowMedian

The Median values of given data set is viewed by enabling the [`ShowMedian`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_ShowMedian) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html). By default,[`ShowMedian`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_ShowMedian) value is false. The following code demonstrates how to enable the [`ShowMedian`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_ShowMedian) property.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:BoxAndWhiskerSeries ItemSource ="{Binding Data"} XBindingPath="Department" 
                               YBindingPath="Ages" 
                               ShowMedian="True" />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries()
{
    ItemsSource = Data,
    XBindingPath = "Department",
    YBindingPath = "Ages",
    ShowMedian = true
} 
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

{% endtabs %}

![ShowMedian support for BoxAndWhiskerSeries in Xamarin.Forms Chart](charttypes_images/BoxAndWhisker_Exclusive_Median.png)

### SymbolType

The [`SymbolType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_SymbolType) is used to display the outlier point that lie either below the lower whisker or above the upper whisker line. The available symbols are Cross, Diamond, Ellipse, Hexagon, InvertedTriangle, Pentagon, Plus, Rectangle and Triangle. By default, [`SymbolType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_SymbolType) value is [`Ellipse`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSymbolType.html).

The following code shows how to set the [`SymbolType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.BoxAndWhiskerSeries.html#Syncfusion_SfChart_XForms_BoxAndWhiskerSeries_SymbolType) value as [`Cross`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartSymbolType.html).

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:BoxAndWhiskerSeries ItemSource ="{Binding Data"} XBindingPath="Department" 
                               YBindingPath="Ages" 
                               ShowMedian="True"
                               SymbolType="Cross" />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries()
{
    ItemsSource = Data,
    XBindingPath = "Department",
    YBindingPath = "Ages",
    ShowMedian = true,
    SymbolType = ChartSymbolType.Cross
} 
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

{% endtabs %}

![Outlier for BoxAndWhiskerSeries in Xamarin.Forms Chart](charttypes_images/BoxAndWhisker_Symbol.png)

## Error Bar Chart

ErrorBarSeries is graphical representations of the variations of data and used on graphs to indicate the errors or uncertainty in a reported measurement. To render a error bar chart, create an instance of [`ErrorBarSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ScatterSeries ScatterHeight="20"
	ScatterWidth="20"
	ShapeType="Ellipse"
	ItemsSource ="{Binding CarDistributionDetails}" 
	XBindingPath="Country"
	YBindingPath="Value">
	<chart:ScatterSeries.ColorModel>
		<chart:ChartColorModel Palette="Natural"/>
        </chart:ScatterSeries.ColorModel>
	</chart:ScatterSeries>	

    <chart:ErrorBarSeries ItemsSource = "{Binding CarDistributionDetails}"
	XBindingPath = "Country"
        YBindingPath = "Value"
	Type = ErrorBarType.Fixed  
	Mode = ErrorBarMode.Both
	HorizontalErrorValue = 0.5
        VerticalErrorValue = 4/>

</chart:SfChart>					  					  
{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ScatterSeries scatterSeries = new ScatterSeries ()
{ 
	ItemsSource = Data, 	
	ScatterHeight = 20, 
	ScatterWidth = 20, 
	ShapeType = ChartScatterShapeType.Ellipse,
	XBindingPath = "Year", 
	YBindingPath = "Value" 
};
scatterSeries.ColorModel.Palette = ChartColorPalette.Natural;
chart.Series.Add(scatterSeries);

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed, 
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

{% endtabs %}

![ErrorBar chart type in Xamarin.Forms](charttypes_images/ErrorBar.png)

### Type

The [`Type`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_Type) property is used to define the error bar type value in Fixed, Custom, Percentage, StandardDeviation, and StandardErrors. The default value of this property is [`Fixed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarType.html). For all types, You have to set the values for [`HorizontalErrorValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_HorizontalErrorValue) and [`VerticalErrorValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_VerticalErrorValue) except [`Custom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarType.html).

#### Fixed

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource = "{Binding CarDistributionDetails}"
	XBindingPath = "Country"
        YBindingPath = "Value"
	Type = ErrorBarType.Fixed  
	Mode = ErrorBarMode.Both
	HorizontalErrorValue = 0.5
        VerticalErrorValue = 4/>

</chart:SfChart>					  					  
{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed, 
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};

{% endhighlight %}

{% endtabs %}

![Fixed type for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_Fixed.png)

#### Percentage

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource = {Binding  CarDistributionDetails}"
	XBindingPath = "Country"
        YBindingPath = "Value" 
        Type = ErrorBarType.Percentage 
	Mode = ErrorBarMode.Both
	HorizontalErrorValue = 1
	VerticalErrorValue = 8/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Percentage,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 1,
	VerticalErrorValue = 8
};

{% endhighlight %}

{% endtabs %}

![Percentage type for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_Percentage.png)

#### Standard Deviation

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...
     
    <chart:ErrorBarSeries ItemsSource = "{Binding  CarDistributionDetails}"
	XBindingPath = "Country" 
	YBindingPath = "Value" 
	Type = ErrorBarType.StandardDeviation
	Mode = ErrorBarMode.Both
	HorizontalErrorValue = 1
    VerticalErrorValue = 4/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.StandardDeviation,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 1,
	VerticalErrorValue = 4
};

{% endhighlight %}

{% endtabs %}

![StandardDeviation type for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_StandardDeviation.png)

#### Standard Errors

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource = "{Binding CarDistributionDetails}"
	XBindingPath = "Country" 
	YBindingPath = "Value"
	Type = ErrorBarType.StandardErrors
        Mode = ErrorBarMode.Both
	HorizontalErrorValue = 1
    VerticalErrorValue = 4/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.StandardErrors,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 1,
	VerticalErrorValue = 4
};

{% endhighlight %}

{% endtabs %}

![StandardErrors type for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_StandardErrors.png)

#### Custom

If [`Type`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_Type) is [`Custom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarType.html), you have to set values for [`HorizontalErrorPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_HorizontalErrorPath) and [`VerticalErrorPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_VerticalErrorPath) as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource = "{Binding CarDistributionDetails}"
	XBindingPath = "Country"
        YBindingPath = "Value"
	Type=ErrorBarType.Custom
        Mode = ErrorBarMode.Both
        HorizontalErrorPath = "HorizontalErrorValues" 
        VerticalErrorPath = "VerticalErrorValues"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Custom,
	Mode = ErrorBarMode.Both,
	HorizontalErrorPath = "HorizontalErrorValues",
	VerticalErrorValue = "VerticalErrorValues"
};

{% endhighlight %}

{% endtabs %}

![Custom type for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_Custom.png)

### Mode

The error value shown on the chart is based on the [`Mode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_Mode) property. It have the values of [`Both`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarMode.html), [`Horizontal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarMode.html), and [`Vertical`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarMode.html). The default value of this property is [`Both`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarMode.html). 

#### Both

To display horizontal and vertical error values, you can set the [`Mode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_Mode) as [`Both`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarMode.html) as shown in the following code.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource="{Binding CarDistributionDetails}"
	XBindingPath = "Country"
        YBindingPath = "Value"
	Type = ErrorBarType.Fixed 
        Mode = ErrorBarMode.Both
	HorizontalErrorValue = 0.5
    VerticalErrorValue = 4/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Horizontal,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};

{% endhighlight %}

{% endtabs %}

![ErrorBarMode support for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_Mode_Both.png)

#### Horizontal

To display horizontal error value only, you can set the [`Mode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_Mode) as [`Horizontal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarMode.html) as shown in the following code.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource="{Binding CarDistributionDetails}"
	XBindingPath = "Country"
	YBindingPath = "Value"
	Type = ErrorBarType.Fixed 
	Mode = ErrorBarMode.Horizontal
        HorizontalErrorValue = 0.5
	VerticalErrorValue = 4/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Horizontal,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};

{% endhighlight %}

{% endtabs %}

![ErrorBarMode Horizontal support for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_Mode_Horizontal.png)

#### Vertical

To display vertical error value only, you can set the [`Mode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_Mode) as [`Vertical`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarMode.html) as shown in the following code.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource="{Binding CarDistributionDetails}"
	XBindingPath = "Country"
	YBindingPath = "Value"
	Type = ErrorBarType.Fixed
        Mode = ErrorBarMode.Vertical
        HorizontalErrorValue = 0.5
	VerticalErrorValue = 4/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Vertical,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};

{% endhighlight %}

{% endtabs %}

![ErrorBarMode Vertical support for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_Mode_Vertical.png)

### Direction

The [`HorizontalDirection`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_HorizontalDirection) and [`VerticalDirection`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_VerticalDirection) properties are used to set the direction of error bar lines. The default value is [`Both`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarDirection.html).

* [`Both`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarDirection.html) - used to set error value in positive and negative directions.
* [`Minus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarDirection.html) - used to set error value in a negative direction.
* [`Plus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarDirection.html) - used to set error value in a positive direction.	

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries ItemsSource = "{Binding CarDistributionDetails}"
	XBindingPath = "Country"
	YBindingPath = "Value"
	HorizontalDirection = ErrorBarDirection.Plus
        VerticalDirection = ErrorBarDirection.Minus
        HorizontalErrorValue = 0.5
	VerticalErrorValue = 4/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
	HorizontalDirection = ErrorBarDirection.Plus,
       VerticalDirection = ErrorBarDirection.Minus,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};

{% endhighlight %}

{% endtabs %}

![ErrorBarDirection support for ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_Direction.png)

### Customization

You can customize the [`ErrorBarSeries`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html) with the following style properties.

* [`HorizontalLineStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_HorizontalLineStyle) – used to customize the appearance of horizontal error bar line.
* [`VerticalLineStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_VerticalLineStyle) – used to customize the appearance of vertical error bar line.
* [`HorizontalCapLineStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_HorizontalCapLineStyle) – used to customize the appearance of horizontal error bar cap line.
* [`VerticalCapLineStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ErrorBarSeries.html#Syncfusion_SfChart_XForms_ErrorBarSeries_VerticalCapLineStyle) – used to customize the appearance of vertical error bar cap line.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
...

    <chart:ErrorBarSeries.HorizontalLineStyle>
    <chart:ErrorBarLineStyle
	StrokeColor= "Cyan"
	StrokeWidth = "4">
    </chart:ErrorBarSeries.HorizontalLineStyle>
	
    <chart:ErrorBarSeries.VerticalLineStyle>       
    <chart:ErrorBarLineStyle
	StrokeColor = "Cyan" 
	StrokeWidth = "4">
    </chart:ErrorBarSeries.VerticalLineStyle>

    <chart:ErrorBarSeries.HorizontalCapLineStyle>
    <chart:ErrorBarCapLineStyle
	StrokeColor= "Green"
	StrokeWidth= "4"
	IsVisible = "true">
    </chart:ErrorBarSeries.HorizontalCapLineStyle>
	
    <chart:ErrorBarSeries.VerticalCapLineStyle>    
    <chart:ErrorBarCapLineStyle
	StrokeColor = "Green"
	StrokeWidth = "4"
	IsVisible = "true">
    </chart:ErrorBarSeries.VerticalCapLineStyle>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

 errorBarSeries.HorizontalLineStyle = new ErrorBarLineStyle();
 errorBarSeries.HorizontalLineStyle.StrokeColor = Color.Cyan;
 errorBarSeries.HorizontalLineStyle.StrokeWidth = 4;
 
 errorBarSeries.VerticalLineStyle = new ErrorBarLineStyle();
 errorBarSeries.VerticalLineStyle.StrokeColor = Color.Cyan;
 errorBarSeries.VerticalLineStyle.StrokeWidth = 4;
 
 errorBarSeries.HorizontalCapLineStyle = new ErrorBarCapLineStyle();
 errorBarSeries.HorizontalCapLineStyle.StrokeColor = Color.Green;
 errorBarSeries.HorizontalCapLineStyle.StrokeWidth = 4;
 errorBarSeries.HorizontalCapLineStyle.IsVisible = true;

 errorBarSeries.VerticalCapLineStyle = new ErrorBarCapLineStyle();
 errorBarSeries.VerticalCapLineStyle.StrokeColor = Color.Green;
 errorBarSeries.VerticalCapLineStyle.StrokeWidth = 4;
 errorBarSeries.VerticalCapLineStyle.IsVisible = true;

{% endhighlight %}

{% endtabs %}

![Customization of ErrorBarSeries in Xamarin.Forms Chart](charttypes_images/ErrorBar_LineStyle.png)

## See also

[How to draw dotted line using FastLineSeries in Chart](https://www.syncfusion.com/kb/5924/how-to-draw-dotted-line-using-fastlineseries-in-chart)

[How to visualize the Xamarin.Forms Pie Chart in linear form](https://www.syncfusion.com/kb/11285/how-to-visualize-the-xamarin-forms-pie-chart-in-linear-form)

[How to achieve the Tornado chart in Xamarin.Forms Chart](https://www.syncfusion.com/kb/10684/how-to-achieve-the-tornado-chart-in-xamarin-forms-chart)

[How to use the drill-down functionality in Xamarin.Forms Chart](https://www.syncfusion.com/kb/10662/how-to-use-the-drill-down-functionality-in-xamarin-forms-chart)

[How to set size of pie/doughnut](https://www.syncfusion.com/kb/5525/how-to-set-size-of-pie-doughnut)
