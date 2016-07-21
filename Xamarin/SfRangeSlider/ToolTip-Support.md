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

The `ToolTipPrecision` property is used to define the precision of the value displayed in the Tooltip.

{% tabs %}

{% highlight c# %}

	rangeslider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPrecision="2"/>
	
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

{% highlight c# %}

	rangeslider.ToolTipPlacement = ToolTipPlacement.BottomRight;
	
{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="BottomRight"/>
	
{% endhighlight %}

{% endtabs %}

### TopLeft

the Tooltip will be placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeslider.ToolTipPlacement = ToolTipPlacement.TopLeft;
	
{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="TopLeft"/>
	
{% endhighlight %}

{% endtabs %}

### None

Tooltip will be collapsed.

{% tabs %}

{% highlight c# %}

	rangeslider.ToolTipPlacement = ToolTipPlacement.None;
	
{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ToolTipPlacement="None"/>
	
{% endhighlight %}

{% endtabs %}



