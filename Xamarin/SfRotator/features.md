---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Forms
platform: xamarin 
control: Rotator
documentation: ug
---

# Features

## AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on `NavigationDelay` property, when the property value is set to true.

N> By default, the property value is set to false.

{% tabs %}

{% highlight C# %}

	rotator.EnableAutoPlay = true;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" EnableAutoPlay="true" />
	
{% endhighlight %}

{% endtabs %}

## Navigation Delay

The `NavigationDelay` property specifies the duration to delay the switch to next navigation item, when `EnableAutoPlay` property is enabled.

N> The property value should be in milliseconds.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDelay = 2000;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationDelay="2000" />
	
{% endhighlight %}

{% endtabs %}

## Item Looping

The `EnableLooping` property specifies whether the items should navigate to first item once it reaches the last item and vice-versa.

{% tabs %}

{% highlight C# %}

	rotator.EnableLooping = true;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" EnableLooping="true" />
	
{% endhighlight %}

{% endtabs %}

## Text Area 

The `IsTextVisible` property can be used to enable the text area visibility in bottom area of rotator for providing additional information of items.

N> By default, the property value is false.

{% tabs %}

{% highlight C# %}

	rotator.IsTextVisible = true;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" IsTextVisible="true" />
	
{% endhighlight %}

{% endtabs %}

## Navigation Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in SfRotator control.

* `Horizontal` - Items can be navigated in horizontal direction.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationDirection="Horizontal" />
	
{% endhighlight %}

{% endtabs %}

* `Vertical` - Items can be navigated in vertical direction.

{% tabs %}

{% highlight C# %}

	rotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationDirection="Vertical" />
	
{% endhighlight %}

{% endtabs %}