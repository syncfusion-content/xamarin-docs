---
layout: post
title: Animating chart series
description: Series animation in Essential Xamarin.Forms Chart
platform: xamarin
control: SfChart
documentation: ug
---

# Animation

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) provides animation support for data series. [`Series`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Series.html) will be animated whenever the items source changes. Animation can be enabled by setting the [`EnableAnimation`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~EnableAnimationProperty.html#) property to true. You can also control the duration of the animation using the [`AnimationDuration`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~AnimationDurationProperty.html#) property.

{% tabs %} 

{% highlight xaml %}

<chart:ColumnSeries 
    ItemsSource="{Binding ColumnData}" 
    EnableAnimation = "true" 
    AnimationDuration="0.8" 
    XBindingPath="Name" 
    YBindingPath="Value"  />
{% endhighlight %}

{% highlight c# %}

ColumnSeries column = new ColumnSeries ();
column.ItemsSource = viewModel.ColumnData;
column.XBindingPath = "Name";
column.YBindingPath = "Value";
column.EnableAnimation = true;
column.AnimationDuration = 0.8;

{% endhighlight %}

{% endtabs %}

