---
layout: post
title: Changing display Orientation of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set orientation for RangeSlider
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Orientation

SfRangeSlider provides option to display the values and the slider either horizontally or vertically.

N> The default option is Horizontal.

## Horizontal

{% tabs %}

{% highlight c# %}

	rangeslider.Orientation=Orientation.Horizontal;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Orientation="Horizontal"/>
	
{% endhighlight %}

{% endtabs %}

![](images/RangeSlider-Horizontal.png)

## Vertical

{% tabs %}

{% highlight c# %}

	rangeslider.Orientation=Orientation.Vertical;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Orientation="Vertical"/>
	
{% endhighlight %}

{% endtabs %}

![](images/RangeSlider-Vertical.png)


