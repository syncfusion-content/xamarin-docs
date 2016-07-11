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

## TickFrequency

The `TickFrequency` property is used to decide the number of ticks to be displayed along the track based on Minimum and Maximum values.

{% tabs %}

{% highlight c# %}

	rangeslider.TickFrequency=4;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickFrequency="4" />
	
{% endhighlight %}

{% endtabs %}

N> When the `SnapsTo` property is set to `Ticks`, the `TickFrequency` is used to specify the interval between snap points.

## StepFrequency

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

## SnapsTo

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

## Orientation

The `Orientation` property has the following two options.

### Horizontal

In this orientation, the values and the slider are set horizontally. 

{% tabs %}

{% highlight c# %}

	rangeslider.Orientation=Orientation.Horizontal;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Orientation="Horizontal"/>
	
{% endhighlight %}

{% endtabs %}

![](images/RangeSlider-Horizontal.png)

### Vertical

In this Orientation, the values and the slider are set vertically. 

N> The default option is Horizontal.

{% tabs %}

{% highlight c# %}

	rangeslider.Orientation=Orientation.Vertical;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Orientation="Vertical"/>
	
{% endhighlight %}

{% endtabs %}

![](images/RangeSlider-Vertical.png)


