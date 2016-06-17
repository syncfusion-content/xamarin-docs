---
layout: post
title: Animating chart series
description: Series animation in Essential Xamarin.Forms Chart
platform: xamarin
control: SfChart
documentation: ug
---

# Animation

SfChart provides animation support for data series. Series will be animated whenever the iems source changes. Animation can be enabled by setting the `EnableAnimation` property to `true`. You can also control the duration of the animation using `AnimationDuration` property.

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

