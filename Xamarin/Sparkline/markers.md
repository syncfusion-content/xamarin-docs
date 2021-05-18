---
layout: post
title: Markers in Xamarin Sparkline control | Syncfusion
description: Learn here all about Markers support in Syncfusion Xamarin Sparkline (SfSparkline) control and more.
platform: xamarin
control: Sparkline
documentation: ug
---

# Markers in Xamarin Sparkline (SfSparkline)

[`Markers`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SfLineSparkline.html#Syncfusion_SfSparkline_XForms_SfLineSparkline_Marker) are used to highlight the data point in [`SfLineSparkline`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SfLineSparkline.html) and [`SfAreaSparkline`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.SfAreaSparkline.html). You can use the following properties to customize the appearance.

* [`IsVisible`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.MarkerBase.html#Syncfusion_SfSparkline_XForms_MarkerBase_IsVisible) - used to change the visibility of the marker.
* [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.MarkerBase.html#Syncfusion_SfSparkline_XForms_MarkerBase_Width) - used to change the width of the marker.
* [`Height`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.MarkerBase.html#Syncfusion_SfSparkline_XForms_MarkerBase_Height) - used to change the height of the marker.
* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSparkline.XForms.MarkerBase.html#Syncfusion_SfSparkline_XForms_MarkerBase_Color) - used to change the color of the marker.

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

![Markers support in Xamarin.Forms Sparkline](sparkline_images/Markers.png)
