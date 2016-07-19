---
layout: post
title: Various features of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set minimum value, maximum value, tick frequency, step frequency, enabling snaps to support and orientation for RangeSlider
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Setting Minimum and Maximum Values

SfRangeSlider provides option to set Maximum and Minimum values in which a thumb can not be moved beyond that value.

## Minimum

Gets or sets the minimum possible value of the range. The thumb could not move beyond that value.

{% tabs %}

{% highlight c# %}

	rangeslider.Minimum=0;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Minimum="0"/>
	
{% endhighlight %}

{% endtabs %}

## Maximum

Gets or sets the maximum possible value of the range. The thumb could not move after that value.

{% tabs %}

{% highlight c# %}

	rangeslider.Maximum=24;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Maximum="24"/>
	
{% endhighlight %}

{% endtabs %}

