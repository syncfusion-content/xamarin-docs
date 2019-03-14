---
layout: post
title: Customize the axis label generation in Syncfusion SfChart
description: Customize the axis label generation in SfChart
platform: xamarin
control: Chart
documentation: ug
---

## Customize the axis label generation in SfChart

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) allows the user to define the labels for the axis. In order to define a label, you need to write a class derived from ChartAxis. You need to override [`OnCreateLabels`]() method, which will be called whenever new labels are going to be generated. The labels should be created only if the user calls the base of [`OnCreateLabels`](). Using this method, the user can able to add, remove, insert and clear the custom labels based on position. You can get the generated labels and define the labels using [`VisibleLabels`]() collection.

{% highlight c# %}

public class DateTimeAxisExt : DateTimeAxis
{
    protected override void OnCreateLabels()
    {
        base.OnCreateLabels();

        //Using VisibleLabels collection you can define your custom labels
    }
}

{% endhighlight  %}

N> Labels are rendered only if the label position is present within the visible range.