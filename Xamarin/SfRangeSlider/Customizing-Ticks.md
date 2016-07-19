---
layout: post
title: Ticks of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set ticks in proper position for RangeSlider control in Xamarin.Forms
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Customizing Ticks 

This section explains about the customization of the Ticks in SfRangeSlider control.

## Set Tick Frequency

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


## Displaying Ticks in Different Positions

The `TickPlacement` property determines where to draw tick marks in relation to the track. Available options for this property are,

* BottomRight

* Inline

* None

* Outside

* TopLeft

N> The default option is Inline.

## BottomRight

Tick marks can be placed either below the track in horizontal orientation or right of the track in vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeslider.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="BottomRight"/>
	
{% endhighlight %}

{% endtabs %}

![](images/BottomRight.png)

## TopLeft

Tick marks are placed either above the track in horizontal orientation or left of the track in vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeslider.TickPlacement=TickPlacement.TopLeft;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="TopLeft"/>
	
{% endhighlight %}

{% endtabs %}

![](images/TopLeft.png)

## Inline

Ticks are placed along the track.

{% tabs %}

{% highlight c# %}

	rangeslider.TickPlacement=TickPlacement.Inline;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="Inline"/>
	
{% endhighlight %}

{% endtabs %}

![](images/Inline.png)

## Outside

Tick marks are placed on both sides of the track either in horizontal or vertical orientation.

{% tabs %}

{% highlight c# %}

	rangeslider.TickPlacement=TickPlacement.Outside;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="Outside"/>
	
{% endhighlight %}

{% endtabs %}

![](images/Outside.png)



