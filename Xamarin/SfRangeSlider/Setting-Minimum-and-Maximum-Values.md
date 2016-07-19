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

{% tabs %}

{% highlight c# %}

	rangeslider.Minimum=0;
	rangeslider.Maximum=24;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Minimum="0" Maximum="24"/>
	
{% endhighlight %}

{% endtabs %}
