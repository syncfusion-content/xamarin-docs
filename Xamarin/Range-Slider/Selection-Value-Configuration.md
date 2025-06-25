---
layout: post
title: Selection Value Configuration in Xamarin Range Slider | Syncfusion
description: Explore the options for configuring selection values in the Syncfusion Xamarin Range Slider (SfRangeSlider) control.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Selection Value Configuration in Xamarin Range Slider (SfRangeSlider)

Various customization options are available for configuring selection values in [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html).

## Set Minimum Value

Set the minimum possible value for the range. The thumb cannot move below this value.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Minimum="0"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.Minimum=0;

{% endhighlight %}

{% endtabs %}

## Set Maximum Value

Set the maximum possible value for the range. The thumb cannot move beyond this value.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Maximum="24"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.Maximum=24;

{% endhighlight %}

{% endtabs %}

## Set Tick Frequency

The [`TickFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickFrequency) property determines the interval of ticks displayed along the track between the [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Maximum) values.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickFrequency="4" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickFrequency=4;

{% endhighlight %}

{% endtabs %}

> **Note**: The [`TickFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickFrequency) sets intervals when [`SnapsTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_SnapsTo) is set to `Ticks`.

## Set Interval Between Snap Points

The [`StepFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_StepFrequency) property defines the interval between snap points.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" StepFrequency="4"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.StepFrequency=4;

{% endhighlight %}

{% endtabs %}

> **Note**: The [`StepFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_StepFrequency) is used when [`SnapsTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_SnapsTo) is set to [`StepValues`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_StepValues).

## Set Snapping Mode

The [`SnapsTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_SnapsTo) property controls whether the RangeSlider snaps to steps or ticks. Available options are:

- [`StepValues`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_StepValues): Uses [`StepFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_StepFrequency) to specify intervals.
- [`Ticks`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_Ticks): Uses [`TickFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickFrequency).
- [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_None): The thumb moves independently of set values.

> **Note**: The default is [`Ticks`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_Ticks).

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" SnapsTo="Ticks"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.SnapsTo=SnapsTo.Ticks;

{% endhighlight %}

{% endtabs %}
