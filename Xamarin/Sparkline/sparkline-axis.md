---
layout: post
title: Sparkline Axis in Syncfusion Sparkline control for Xamarin.Forms
description: How to customize Axis in Essential Xamarin.Forms Sparkline
platform: xamarin
control: Sparkline
documentation: ug
---

# Sparkline Axis

Axis of the sparkline can be configured and customized using following properties. This feature is applicable for all the sparkline types except [`SfWinLossSparkline`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SfWinLossSparkline.html).

* [`IsVisible`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SparklineAxis.html#Syncfusion_SfSparkline_XForms_SparklineAxis_IsVisible) - used to change the visibility of the axis.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SparklineAxis.html#Syncfusion_SfSparkline_XForms_SparklineAxis_StrokeColor) - used to change the color of the axis.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SparklineAxis.html#Syncfusion_SfSparkline_XForms_SparklineAxis_StrokeWidth) - used to change the width of the axis.
* [`AxisOrigin`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SparklineAxis.html#Syncfusion_SfSparkline_XForms_SparklineAxis_AxisOrigin) - used to change the origin (positive or negative) of the axis.

{% tabs %} 

{% highlight xaml %}

<sparkline:SfLineSparkline ItemsSource="{Binding Data}" 
                           YBindingPath="Performance">  
  <sparkline:SfLineSparkline.Axis>
    <sparkline:SparklineAxis IsVisible="true"
                             StrokeColor="Red"/>

  </sparkline:SfLineSparkline.Axis>
</sparkline:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline lineSparkline = new SfLineSparkline()
{
    YBindingPath = "Performance",
    ItemsSource = viewModel.Data,
    Axis = new SparklineAxis()
    {
        IsVisible = true,
        StrokeColor = Color.Red,
    }
};

{% endhighlight %}

{% endtabs %}

![Axis support in Xamarin.Forms Sparkline](sparkline_images/Axis.png)
