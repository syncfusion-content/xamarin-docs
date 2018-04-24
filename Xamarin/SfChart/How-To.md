---
layout: post
title: How to
description: how to
platform: xamarin
control: Chart
documentation: ug
---

# How to

## transform axis value to pixel value and vice versa

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) offers two utility methods for converting your data points into pixel values (device coordinates).

* [`ValueToPoint(ChartAxis axis, double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ValueToPoint.html)
* [`PointToValue(ChartAxis axis, Point point)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~PointToValue.html)

{% highlight c# %}

// Converts the screen points into a value related to ChartAxis.

double xValue = Chart.PointToValue(Chart.PrimaryAxis, touchPoint);

double yValue = Chart.PointToValue(Chart.SecondaryAxis, touchPoint);

// Converts the data point value of the chart to Chart coordinate.

double chartPointX = Chart.ValueToPoint(Chart.PrimaryAxis, xValue);

double chartPointY = Chart.ValueToPoint(Chart.SecondaryAxis, yValue);

{% endhighlight  %}

N> The [`ValueToPoint`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ValueToPoint.html) and [`PointToValue`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~PointToValue.html) methods are also available in [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html) so we can access these methods
 from chart axis.

 ## transform axis value to Coefficient value and vice versa

[`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html) offers below two methods to coverts data point value into Coordinate unites and vice versa.

* [`ValueToCoefficient(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ValueToCoefficient.html)

* [`CoefficientToValue(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~CoefficientToValue.html)

{% highlight c# %}

//Converts value of passed point co-ordinate to control related co-ordinate.
var valToCoefficient = Chart.SecondaryAxis.ValueToCoefficient(400);

//Converts co-ordinate of point related to chart control to axis units.
var CoeffToVal = Chart.SecondaryAxis.CoefficientToValue(valToCoefficient);

{% endhighlight  %}

## get the touch actions in chart 

ChartBehavior provides the below override methods to get the corresponding touch point while on touch actions and it can be possible by extending any of the Chart behavior class.

* [`OnTouchUp`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchUp.html)

* [`OnTouchMove`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchMove.html)

* [`OnTouchDown`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchDown.html)

* [`DoubleTap`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~DoubleTap.html)

Here, for example, you can get the user touch points using above methods by extending ChartTooltipBehavior. 

{% highlight c# %}

public class ChartTooltipBehaviorExt : ChartTooltipBehavior
{
        
        protected override void OnTouchUp(float pointX, float pointY)
        {
            //you can perform any operations 
        }

        protected override void OnTouchMove(float pointX, float pointY)
        {
            //you can perform any operations 
        }

        protected override void OnTouchDown(float pointX, float pointY)
        {
            //you can perform any operations 
        }

        protected override void DoubleTap(float pointX, float pointY)
        {
           //you can perform any operations 
        }
      
}

{% endhighlight  %}
