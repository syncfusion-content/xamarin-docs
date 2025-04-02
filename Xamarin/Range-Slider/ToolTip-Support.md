---
layout: post
title: ToolTip Support in Xamarin Range Slider control | Syncfusion
description: Learn here all about ToolTip Support in Syncfusion Xamarin Range Slider (SfRangeSlider) control and more.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# ToolTip Support in Xamarin Range Slider (SfRangeSlider)

The ToolTip shows the current value based on thumb position.

## Set ToolTip Precision

The [`ToolTipPrecision`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipPrecision) property is used to define the precision of the value displayed in the ToolTip.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPrecision="2"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% endtabs %}

## Set ToolTip Placement

The position of the ToolTip in relation to the thumb can be controlled by the [`ToolTipPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipPlacement) property. It has the following options.

1. [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ToolTipPlacement.html#Syncfusion_SfRangeSlider_XForms_ToolTipPlacement_BottomRight)
2. [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ToolTipPlacement.html#Syncfusion_SfRangeSlider_XForms_ToolTipPlacement_TopLeft)
3. [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ToolTipPlacement.html#Syncfusion_SfRangeSlider_XForms_ToolTipPlacement_None)

### BottomRight

The ToolTip will be placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="BottomRight"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPlacement = ToolTipPlacement.BottomRight;
	
{% endhighlight %}

{% endtabs %}

### TopLeft

the ToolTip will be placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPlacement = ToolTipPlacement.TopLeft;
	
{% endhighlight %}

{% endtabs %}

### None

ToolTip will be collapsed.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="None"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPlacement = ToolTipPlacement.None;
	
{% endhighlight %}

{% endtabs %}

## Tooltip color

[`TooltipTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipTextColor) - Changes the text color of tooltip.
[`TooltipBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ToolTipBackgroundColor) - Changes the background color of tooltip.

![SfRangeSlider Tooltip color Xamarin.Forms](images/Tooltip-color.jpg)

