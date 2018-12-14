---
layout: post
title: Customizations in Syncfusion SfChart
description: Customizations in SfChart
platform: xamarin
control: Chart
documentation: ug
---

# How to

## Transform axis value to pixel value and vice-versa

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) offers two utility methods to transform the pixel to chart point and vice-versa.

* [`ValueToPoint(ChartAxis axis, double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ValueToPoint.html) - Converts the data point value to screen point.
* [`PointToValue(ChartAxis axis, Point point)`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~PointToValue.html) - Converts the screen point to chart value.

{% highlight c# %}

double xValue = Chart.PointToValue(Chart.PrimaryAxis, screenPoint);

double yValue = Chart.PointToValue(Chart.SecondaryAxis, screenPoint);

double chartPointX = Chart.ValueToPoint(Chart.PrimaryAxis, xValue);

double chartPointY = Chart.ValueToPoint(Chart.SecondaryAxis, yValue);

{% endhighlight  %}

Use the [`ValueToPoint`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ValueToPoint.html) and [`PointToValue`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~PointToValue.html) methods, which are available in [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html), to convert the screen point within the rendered area of the series.

N> You can convert the actual axis value to 0 to 1 coefficient using the [`ValueToCoefficient(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ValueToCoefficient.html) and [`CoefficientToValue(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~CoefficientToValue.html) methods of [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html).

## Get the touch position in chart

ChartBehavior provides the following override methods to get the x and y positions when touch the [`Chart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~Chart.html).

* [`OnTouchUp`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchUp.html) - Called when touch up on the chart area with respective x and y position.
* [`OnTouchMove`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchMove.html) - Called when touch move on the chart area with respective x and y position.
* [`OnTouchDown`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchDown.html) -  Called when touch down on the chart area with respective x and y position.
* [`DoubleTap`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~DoubleTap.html) - Called when double tap on the chart area with respective x and y position.


{% highlight c# %}

public class ChartTooltipBehaviorExt : ChartTooltipBehavior
{
        
        protected override void OnTouchUp(float pointX, float pointY)
        {
               base.OnTouchUp(pointX, pointY);
        }

        protected override void OnTouchMove(float pointX, float pointY)
        {
               base.OnTouchMove(pointX, pointY);
        }

        protected override void OnTouchDown(float pointX, float pointY)
        {
               base.OnTouchDown(pointX, pointY);
        }

        protected override void DoubleTap(float pointX, float pointY)
        {
               base.DoubleTap(pointX, pointY);
        }
      
}

{% endhighlight  %}

##  Get the data point collection based on region

[`CartesianSeries`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CartesianSeries.html) provides the following methods to get a collection of data under a particular region.

* [`GetDataPoints(Rectangle rect)`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CartesianSeries~GetDataPoints(Rectangle).html) - Gets the collection of data that fall inside the given rectangle region.
* [`GetDataPoints(double startX, double endX, double startY, double endY)`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CartesianSeries~GetDataPoints(Double,Double,Double,Double).html) - Gets the collection of data from the given ChartAxis visible range.

{% highlight c# %}

List<object> dataPoints = Series.GetDataPoints(rectangle);

or

List<object> dataPoints = Series.GetDataPoints(startX, endX, startY, endY);

{% endhighlight  %}

##  Adding duplicate axis in SfChart

Duplicate axis can be added in the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) using the chart [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Axes.html) collection property. The axis added in the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Axes.html) collection will be aligned in the horizontal position by default. The axis position can be changed by using the [`IsVertical`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~IsVertical.html) bool property of the [`Axis`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html). When [`IsVertical`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~IsVertical.html) property is set true axis will be placed vertical and vice versa.

N> The [`axis`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html) added in the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Axes.html) collection won’t get removed until removing it from the [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Axes.html) collection. The [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Axes.html) collection clear method doesn’t support. Same axis can’t be added more than once in [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Axes.html) only distinct axis get added in [`Axes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Axes.html) collection.
