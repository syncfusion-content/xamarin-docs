---
layout: post
title: ToolTip support for Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set tooltip for RangeSlider in Xamarin.Forms
platform: Xamarin
control: RangeSlider
documentation: ug
---

# ToolTip Support

The ToolTip shows the current value based on thumb position.

## Set ToolTip Precision

The `ToolTipPrecision` property is used to define the precision of the value displayed in the ToolTip.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPrecision="2"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% endtabs %}

## Set ToolTip Placement

The position of the ToolTip in relation to the thumb can be controlled by the `ToolTipPlacement` property. It has the following options.

1. BottomRight
2. TopLeft
3. None

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

`TooltipTextColor` - Changes the text color of tooltip.
`TooltipBackgroundColor` - Changes the background color of tooltip.

![SfRangeSlider Tooltip color Xamarin.Forms](images/Tooltip-color.jpg)

