---
layout: post
title: Range Band in Syncfusion Sparkline control for Xamarin.Forms
description: How to highlight particualr region in Essential Xamarin.Forms Sparkline
platform: xamarin
control: Sparkline
documentation: ug
---

# Range Band

This feature is used to highlight a particular region in the sparkline along Y axis.

* [`RangeBandStart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~RangeBandStart.html) - used to configure the start range band value in Y axis.
* [`RangeBandEnd`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~RangeBandEnd.html) - used to configure the end range band values in Y axis.
* [`RangeBandColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~RangeBandColor.html) - used to change the color for range band.

{% tabs %} 

{% highlight xaml %}

  <sparkline:SfLineSparkline ItemsSource="{Binding Data}" 
                             YBindingPath="Performance" 
                             RangeBandStart="4000" 
                             RangeBandEnd="1000"
                             RangeBandColor="Green"> 
  </sparkline:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline lineSparkline = new SfLineSparkline()
{
    YBindingPath = "Performance",
    ItemsSource = viewModel.Data,
    RangeBandStart = 4000,
    RangeBandEnd = 1000,
    RangeBandColor = Color.FromRgba(0, 255, 0, 100)
};

{% endhighlight %}

{% endtabs %}

![Range band support in Xamarin.Forms Sparkline](sparkline_images/RangeBand.png)
