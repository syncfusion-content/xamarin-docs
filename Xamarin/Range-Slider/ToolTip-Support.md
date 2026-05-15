---
layout: post
title: ToolTip Support in Xamarin Range Slider Control | Syncfusion
description: Discover ToolTip support in the Syncfusion Xamarin Range Slider (SfRangeSlider) control, including customization and placement options.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# ToolTip Support in Xamarin Range Slider (SfRangeSlider)

The ToolTip feature indicates the current value based on the thumb's position.

## Set ToolTip Precision

The [`ToolTipPrecision`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipPrecision) property sets the decimal precision of the value displayed in the ToolTip.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPrecision="2"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% endtabs %}

## Set ToolTip Placement

Control the ToolTip's position relative to the thumb using the [`ToolTipPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipPlacement) property. Options include:

1. [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ToolTipPlacement.html#Syncfusion_SfRangeSlider_XForms_ToolTipPlacement_BottomRight)
2. [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ToolTipPlacement.html#Syncfusion_SfRangeSlider_XForms_ToolTipPlacement_TopLeft)
3. [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ToolTipPlacement.html#Syncfusion_SfRangeSlider_XForms_ToolTipPlacement_None)

### BottomRight

Position the ToolTip below the thumb in horizontal orientation or to the right in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="BottomRight"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPlacement = ToolTipPlacement.BottomRight;
	
{% endhighlight %}

{% endtabs %}

### TopLeft

Position the ToolTip above the thumb in horizontal orientation or to the left in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPlacement = ToolTipPlacement.TopLeft;
	
{% endhighlight %}

{% endtabs %}

### None

The ToolTip will not be displayed.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="None"/>
	
{% endhighlight %}

{% highlight c# %}
	rangeSlider.ToolTipPlacement = ToolTipPlacement.None;
	
{% endhighlight %}

{% endtabs %}

## Tooltip Color

Customize the ToolTip's appearance by modifying the following properties:
- [`TooltipTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipTextColor): Changes the text color.
- [`TooltipBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipBackgroundColor): Changes the background color.

![SfRangeSlider ToolTip color in Xamarin.Forms](images/Tooltip-color.jpg)
