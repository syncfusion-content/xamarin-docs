---
layout: post
title: Adding Looping and Delays in Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Forms
platform: xamarin 
control: Rotator
documentation: ug
---

# Sliding Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in SfRotator control.

## Horizontal

Items can be navigated in horizontal direction.

{% tabs %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationDirection="Horizontal" />
	
{% endhighlight %}

{% highlight C# %}

	rotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

{% endtabs %}

## Vertical

Items can be navigated in vertical direction.

{% tabs %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationDirection="Vertical" />
	
{% endhighlight %}

{% highlight C# %}

	rotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}

{% endtabs %}