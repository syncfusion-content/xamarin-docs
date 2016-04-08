---
layout: post
title: Ticks of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set ticks in proper position for RangeSlider control in Xamarin.Forms
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Ticks

## TickPlacement

The `TickPlacement` property determines where to draw tick marks in relation to the track. Available options for this property are,

* BottomRight

* Inline

* None

* Outside

* TopLeft

N> The default option is Inline.

## BottomRight

Tick marks can be placed either below the track in horizontal orientation or right of the track in vertical orientation.

{% highlight c# %}

	sfRangeSlider.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

![](images/BottomRight.png)

## TopLeft

Tick marks are placed either above the track in horizontal orientation or left of the track in vertical orientation.

{% highlight c# %}

	sfRangeSlider.TickPlacement=TickPlacement.TopLeft;

{% endhighlight %}

![](images/TopLeft.png)

## Inline

Ticks are placed along the track.

{% highlight c# %}

	sfRangeSlider.TickPlacement=TickPlacement.Inline;

{% endhighlight %}

![](images/Inline.png)

## Outside

Tick marks are placed on both sides of the track either in horizontal or vertical orientation.

{% highlight c# %}

	sfRangeSlider.TickPlacement=TickPlacement.Outside;

{% endhighlight %}

![](images/Outside.png)



