---
layout: post
title: Customize the Syncfusion SfChart padding
description: Customize the SfChart padding
platform: xamarin
control: Chart
documentation: ug
---

# Customize the SfChart padding

By default, padding is applied to all the sides of chart to avoid the cropping of axis labels and leaving some space between nearby views and chart. However, it can be removed or changed using the [`ChartPadding`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_ChartPadding) property of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

The following code example shows how to customize the padding of chart. 


{% tabs %} 

{% highlight xaml %}

<chart:SfChart   x:Name="Chart" ChartPadding ="5,5,5,5">

...

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

...  

     SfChart chart = new SfChart()
       {
           ChartPadding = new Thickness(5)
       };

...

{% endhighlight %}

{% endtabs %}