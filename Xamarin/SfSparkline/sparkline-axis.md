---
layout: post
title: Sparkline Axis
description: How to customize Axis in Essential Xamarin.Forms Sparkline
platform: xamarin
control: Sparkline
documentation: ug
---

# Sparkline Axis

Axis of the sparkline can be configured and customized using following properties. This feature is applicable for all the sparkline types except [`SfWinLossSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfWinLossSparkline.html).

* [`IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SparklineAxis~IsVisible.html) - used to change the visibility of the axis.
* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SparklineAxis~StrokeColor.html) - used to change the color of the axis.
* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SparklineAxis~StrokeWidth.html) - used to change the width of the axis.
* [`AxisOrigin`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SparklineAxis~AxisOrigin.html) - used to change the origin (positive or negative) of the axis.

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

![](sparkline_images/Axis.png)
