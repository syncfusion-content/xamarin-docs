---
layout: post
title: Markers
description: How to customize markers in Essential Xamarin.Forms Sparkline
platform: xamarin
control: Sparkline
documentation: ug
---

# Markers

[`Markers`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline~Marker.html) are used to highlight the data point in [`SfLineSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline.html) and [`SfAreaSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfAreaSparkline.html). You can use the following properties to customize the appearance.

* [`IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.MarkerBase~IsVisible.html) - used to change the visibility of the marker.
* [`Width`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.MarkerBase~Width.html) - used to change the width of the marker.
* [`Height`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.MarkerBase~Height.html) - used to change the height of the marker.
* [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.MarkerBase~Color.html) - used to change the color of the marker.

{% tabs %} 

{% highlight xaml %}

<sparkline:SfLineSparkline ItemsSource="{Binding Data}" 
                           YBindingPath="Performance">  
     <sparkline:SfLineSparkline.Marker>
	       <sparkline:MarkerBase IsVisible="True" 
                                 Width="15"
                                 Height="15"/>
     </sparkline:SfLineSparkline.Marker> 
</sparkline:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline lineSparkline = new SfLineSparkline()
{
    YBindingPath = "Performance",
    ItemsSource = viewModel.Data,
    Marker = new MarkerBase()
    {
        IsVisible = true,
        Width = 15,
        Height = 15
    }
};

{% endhighlight %}

{% endtabs %}

![](sparkline_images/Markers.png)
