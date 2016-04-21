---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Forms
platform: Xamarin.Forms 
control: Rotator
documentation: ug
---

# Features

## AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on `NavigationDelay` property, when the property value is set to true.

N> By default, the property value is set to false.

{% highlight C# %}

	rotator.EnableAutoPlay = True;

{% endhighlight %}

## Navigation Delay

The `NavigationDelay` property specifies the duration to delay the switch to next navigation item, when `EnableAutoPlay` property is enabled.

N> The property value should be in milliseconds.

{% highlight C# %}

	rotator.NavigationDelay = 2000;

{% endhighlight %}

## Item Looping

The `EnableLooping` property specifies whether the items should navigate to first item once it reaches the last item and vice-versa.

{% highlight C# %}

	rotator.EnableLooping = True;

{% endhighlight %}

## Text Area 

The `IsTextVisible` property can be used to enable the text area visibility in bottom area of rotator for providing additional information of items.

N> By default, the property value is false.

{% highlight C# %}

	rotator.IsTextVisible = True;

{% endhighlight %}

## Navigation Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in Rotator control.

* `Horizontal` - Items can be navigated in horizontal direction.

{% highlight C# %}

	rotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

* `Vertical` - Items can be navigated in vertical direction.

{% highlight C# %}

	rotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}