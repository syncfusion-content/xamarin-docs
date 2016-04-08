---
layout: post
title: Range in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set Dual thumb slider and its ranges in RangeSlider control.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Range

The SfRangeSlider control supports to select range of value by using two Thumbs.

## ShowRange

The `ShowRange` property should be set to true for displaying two thumbs in track with range of values.

N> When this property is set to false, single thumb is displayed without any range 

{% highlight c# %}

	sfRangeSlider.ShowRange= True;

{% endhighlight %}

## RangeStart

Gets and sets the start value of the range.

{% highlight c# %}

	sfRangeSlider.RangeStart=0;

{% endhighlight %}

## RangeEnd

Gets and sets the end value of the range.

{% highlight c# %}

	sfRangeSlider.RangeEnd=10;

{% endhighlight  %}
