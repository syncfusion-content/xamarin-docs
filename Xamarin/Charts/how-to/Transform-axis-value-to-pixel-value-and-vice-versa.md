---
layout: post
title: Transform axis value to pixel value and vice-versa | Syncfusion
description: Transform axis value to pixel value and vice-versa in SfChart
platform: xamarin
control: Chart
documentation: ug
---

# Transform axis value to pixel value and vice-versa

[`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html) offers two utility methods to transform the pixel to chart point and vice-versa.

* [`ValueToPoint(ChartAxis axis, double value)`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_ValueToPoint_Syncfusion_SfChart_XForms_ChartAxis_System_Double_) - Converts the data point value to screen point.
* [`PointToValue(ChartAxis axis, Point point)`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_PointToValue_Syncfusion_SfChart_XForms_ChartAxis_Xamarin_Forms_Point_) - Converts the screen point to chart value.

{% highlight c# %}

double xValue = Chart.PointToValue(Chart.PrimaryAxis, screenPoint);

double yValue = Chart.PointToValue(Chart.SecondaryAxis, screenPoint);

double chartPointX = Chart.ValueToPoint(Chart.PrimaryAxis, xValue);

double chartPointY = Chart.ValueToPoint(Chart.SecondaryAxis, yValue);

{% endhighlight  %}

Use the [`ValueToPoint`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_ValueToPoint_System_Double_) and [`PointToValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_PointToValue_Xamarin_Forms_Point_) methods, which are available in [`ChartAxis`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html), to convert the screen point within the rendered area of the series.

N> You can convert the actual axis value to 0 to 1 coefficient using the [`ValueToCoefficient(double value)`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_ValueToCoefficient_System_Double_) and [`CoefficientToValue(double value)`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html#Syncfusion_SfChart_XForms_ChartAxis_CoefficientToValue_System_Double_) methods of [`ChartAxis`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.ChartAxis.html).
