---
layout: post
title: Transform axis value to Coefficient value and vice versa
description: transform axis value to coefficient value and vice versa
platform: xamarin
control: Chart
documentation: ug
---

## Transform axis value to Coefficient value and vice versa

[`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html) offers below two methods to coverts data point value into Coordinate unites and vice versa.

* [`ValueToCoefficient(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ValueToCoefficient.html)

* [`CoefficientToValue(double value)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~CoefficientToValue.html)

{% highlight c# %}

//Converts value of passed point co-ordinate to control related co-ordinate.
var valToCoefficient = Chart.SecondaryAxis.ValueToCoefficient(400);

//Converts co-ordinate of point related to chart control to axis units.
var CoeffToVal = Chart.SecondaryAxis.CoefficientToValue(valToCoefficient);

{% endhighlight  %}
 
