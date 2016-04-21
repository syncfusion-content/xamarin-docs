---
layout: post
title: Various features of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set minimum value, maximum value, tick frequency, step frequency, enabling snaps to support and orientation for RangeSlider
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Features

## Minimum

Gets or sets the minimum possible value of the range. The thumb could not move beyond that value.

{% highlight c# %}

	rangeSlider.Minimum=0;

{% endhighlight %}

## Maximum

Gets or sets the maximum possible value of the range. The thumb could not move after that value.

{% highlight c# %}

	rangeSlider.Maximum=24;

{% endhighlight %}

## TickFrequency

The `TickFrequency` property is used to decide the number of ticks to be displayed along the track based on Minimum and Maximum values.

{% highlight c# %}

	rangeSlider.TickFrequency=4;

{% endhighlight %}

N> When the `SnapsTo` property is set to `Ticks`, the `TickFrequency` is used to specify the interval between snap points.

## StepFrequency

The `StepFrequency` property is used to specify the interval between snap points.

{% highlight c# %}

	rangeSlider.TickFrequency=4;

{% endhighlight %}

N> When the `SnapsTo` property is set to `StepValues`, the `StepFrequency` property is enabled.

## SnapsTo

The `SnapsTo` property determines whether the RangeSlider snaps to steps or ticks. Available options for this property are

* `StepValues` - The `StepFrequency` property will be used to specify the interval between snap points.

* `Ticks` - The `TickFrequency` property will be used to specify the interval between snap points

* `None` - The thumb is moved independent of any values.

N> The default option is Ticks.

{% highlight c# %}

	rangeSlider.SnapsTo=SnapsTo.Ticks;

{% endhighlight %}

## Orientation

The Orientation property has the following two options.

### Horizontal

In this orientation, the values and the slider are set horizontally. 

{% highlight c# %}

	rangeSlider.Orientation=Orientation.Horizontal

{% endhighlight %}

![](images/RangeSlider-Horizontal.png)

### Vertical

In this Orientation, the values and the slider are set vertically. 

N> The default option is Horizontal.

{% highlight c# %}

	rangeSlider.Orientation=Orientation.Vertical

{% endhighlight %}

![](images/RangeSlider-Vertical.png)


