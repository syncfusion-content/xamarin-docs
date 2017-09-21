---
layout: post
title: Sparkline types
description: What are the different types of Sparklines available in Essential Xamarin.forms Sparkline.
platform: xamarin
control: Sparkline
documentation: ug
---

# Sparkline Types

## Line Sparkline

[`SfLineSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline.html) is used to visualize a data trend of specific intervals. You can use the following properties to customize the appearance.

* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeWidth.html) - used to change the stroke width of the sparkline.
* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeColor.html) - used to change the stroke color of the sparkline.

The following code is used to create the [`SfLineSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline.html).

{% tabs %} 

{% highlight xaml %}

<sparkline:SfLineSparkline ItemsSource = "{Binding Data}" 
                           YBindingPath = "Performance"> 
</sparkline:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline lineSparkline = new SfLineSparkline()
{
   ItemsSource = viewModel.Data,
   YBindingPath = "Performance"           
};

{% endhighlight %}

{% endtabs %}

![](sparklinetypes_images/charttypes_img1.png)


## Column Sparkline

[`SfColumnSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfColumnSparkline.html) is used to facilitate comparison of values in discrete categories. You can use the following properties to customize the appearance.

* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeWidth.html) - used to change the stroke width of the sparkline.
* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeColor.html) - used to change the stroke color of the sparkline.

The following code is used to create the [`SfColumnSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfColumnSparkline.html).

{% tabs %} 

{% highlight xaml %}

<sparkline:SfColumnSparkline ItemsSource = "{Binding Data}" 
                             YBindingPath = "Performance"> 
</sparkline:SfColumnSparkline>

{% endhighlight %}

{% highlight c# %}

SfColumnSparkline columnSparkline = new SfColumnSparkline()
{
   ItemsSource = viewModel.Data,
   YBindingPath = "Performance"            
};

{% endhighlight %}

{% endtabs %}

![](sparklinetypes_images/charttypes_img1.png)


## Area Sparkline

[`SfAreaSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfAreaSparkline.html) is used to emphasize a change in values. This is primarily used when the magnitude of the trend is to be communicated rather than individual data values.

* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeWidth.html) - used to change the stroke width of the sparkline.
* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeColor.html) - used to change the stroke color of the sparkline.

The following code is used to create the [`SfAreaSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfAreaSparkline.html).

{% tabs %} 

{% highlight xaml %}

<sparkline:SfAreaSparkline ItemsSource = "{Binding Data}"
                           YBindingPath = "Performance"> 
</sparkline:SfAreaSparkline>

{% endhighlight %}

{% highlight c# %}

SfAreaSparkline areaSparkline = new SfAreaSparkline()
{
   ItemsSource = viewModel.Data,
   YBindingPath = "Performance"            
};

{% endhighlight %}

{% endtabs %}

![](sparklinetypes_images/charttypes_img1.png)


## WinLoss Sparkline

[`SfWinLossSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfWinLossSparkline.html) is used to show whether each value is positive or negative visualizing a Win/Loss scenario. You can use the following properties to customize the appearance.

* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeWidth.html) - used to change the stroke width of the sparkline.
* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~StrokeColor.html) - used to change the stroke color of the sparkline.

The following code is used to create the [`SfWinLossSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/sfsparkline/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfWinLossSparkline.html).

{% tabs %} 

{% highlight xaml %}

<sparkline:SfWinLossSparkline ItemsSource = "{Binding Data}" 
                              YBindingPath = "Performance"> 
</sparkline:SfWinLossSparkline >

{% endhighlight %}

{% highlight c# %}

SfWinLossSparkline winLossSparkline = new SfWinLossSparkline()
{
   ItemsSource = viewModel.Data,
   YBindingPath = "Performance"
};

{% endhighlight %}

{% endtabs %}

![](sparklinetypes_images/charttypes_img1.png)