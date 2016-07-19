---
layout: post
title: Various features of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set minimum value, maximum value, tick frequency, step frequency, enabling snaps to support and orientation for RangeSlider
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Configuring Thumb Movement

Thumb movement can be configured using `SnapsTo` and `StepFrequency` properties in SfRangeSlider.

## Setting SnapsTo

The `SnapsTo` property determines whether the SfRangeSlider snaps to steps or ticks. Available options for this property are

* `StepValues` - The `StepFrequency` property will be used to specify the interval between snap points.

* `Ticks` - The `TickFrequency` property will be used to specify the interval between snap points

* `None` - The thumb is moved independent of any values.

N> The default option is Ticks.

{% tabs %}

{% highlight c# %}

	rangeslider.SnapsTo=SnapsTo.Ticks;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" SnapsTo="Ticks"/>
	
{% endhighlight %}

{% endtabs %}


## Setting Step Frequency

The `StepFrequency` property is used to specify the interval between snap points.

{% tabs %}

{% highlight c# %}

	rangeslider.StepFrequency=4;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" StepFrequency="4"/>
	
{% endhighlight %}

{% endtabs %}

N> When the `SnapsTo` property is set to `StepValues`, the `StepFrequency` property is enabled.




