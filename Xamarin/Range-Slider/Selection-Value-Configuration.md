---
layout: post
title: Selection Value configuration in Xamarin Range Slider | Syncfusion
description: Learn here all about Selection Value configuration support in Syncfusion Xamarin Range Slider (SfRangeSlider) control and more.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Selection Value configuration in Xamarin Range Slider (SfRangeSlider)

Various customization options are available to configure the selection value in [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html).

## Set Minimum Value

Gets or sets the minimum possible value of the range. The thumb could not move beyond that value.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Minimum="0"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.Minimum=0;

{% endhighlight %}

{% endtabs %}

## Set Maximum Value

Gets or sets the maximum possible value of the range. The thumb could not move after that value.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Maximum="24"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.Maximum=24;

{% endhighlight %}

{% endtabs %}

## Set Tick Frequency

The [`TickFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickFrequency) property is used to decide the number of ticks to be displayed along the track based on Minimum and Maximum values.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickFrequency="4" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickFrequency=4;

{% endhighlight %}

{% endtabs %}

N> When the [`SnapsTo`]([`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html)) property is set to `Ticks`, the [`TickFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickFrequency) is used to specify the interval between snap points.

## Set Interval between Snap Points.

The [`StepFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_StepFrequency) property is used to specify the interval between snap points.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" StepFrequency="4"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.StepFrequency=4;

{% endhighlight %}

{% endtabs %}

N> When the [`SnapsTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_SnapsTo) property is set to [`StepValues`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_StepValues), the [`StepFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_StepFrequency) property is enabled.

## Set Snapping Mode

The [`SnapsTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_SnapsTo)` property determines whether the RangeSlider snaps to steps or ticks. Available options for this property are

* [`StepValues`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_StepValues) - The [`StepFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_StepFrequency) property will be used to specify the interval between snap points.

* [`Ticks`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_Ticks) - The [`TickFrequency`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickFrequency) property will be used to specify the interval between snap points

* [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_None) - The thumb is moved independent of any values.

N> The default option is [`Ticks`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_Ticks).

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" SnapsTo="Ticks"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.SnapsTo=SnapsTo.Ticks;

{% endhighlight %}

{% endtabs %}
