---
layout: post
title: Customizations in SfChart
description: Customizations in SfChart
platform: xamarin
control: Chart
documentation: ug
---

# How to

## Transform axis value to pixel value and vice versa

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) offers two utility methods for transforming the pixel to chart point and vice versa.

* [`ValueToPoint(ChartAxis axis, double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ValueToPoint.html) - Converts the data point value to screen point.
* [`PointToValue(ChartAxis axis, Point point)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~PointToValue.html) - Converts the screen point to chart value.

{% highlight c# %}

double xValue = Chart.PointToValue(Chart.PrimaryAxis, screenPoint);

double yValue = Chart.PointToValue(Chart.SecondaryAxis, screenPoint);

double chartPointX = Chart.ValueToPoint(Chart.PrimaryAxis, xValue);

double chartPointY = Chart.ValueToPoint(Chart.SecondaryAxis, yValue);

{% endhighlight  %}

Also, use the [`ValueToPoint`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ValueToPoint.html) and [`PointToValue`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~PointToValue.html) methods which are also available in [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html) to convert the screen point within the rendered area of the series.

N> You can convert the actual axis value to  0 to 1 coefficient using [`ValueToCoefficient(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ValueToCoefficient.html) and [`CoefficientToValue(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~CoefficientToValue.html) methods of [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html).

## Get the touch position in chart

ChartBehavior provides the below override methods to get the x and y position when touch on the chart.

* [`OnTouchUp`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchUp.html) - Occurs when the finger is raised off the screen while the finger is over the Chart. 

* [`OnTouchMove`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchMove.html) - Occurs when a finger moves on the chart area. 

* [`OnTouchDown`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchDown.html) - Occurs when a finger touches the chart area.

* [`DoubleTap`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~DoubleTap.html) - Occurs when touch the chart area twice in rapid succession.


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
