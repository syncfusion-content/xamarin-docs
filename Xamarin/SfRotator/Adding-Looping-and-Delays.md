---
layout: post
title: Adding Looping and Delays in Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Forms
platform: xamarin 
control: Rotator
documentation: ug
---

# Adding Looping and Delays

Looping and delay can be enabled in SfRotator control and also we can customize the Text and Navigation direction.

## Toggle AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on `NavigationDelay` property, when the property value is set to true.

N> By default, the property value is set to false.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfRotator x:Name="rotator" EnableAutoPlay="true" />
	
{% endhighlight %}

{% highlight C# %}
    
	SfRotator rotator = new SfRotator();
	rotator.EnableAutoPlay = true;

{% endhighlight %}

{% endtabs %}

## Setting Navigation Delay

The `NavigationDelay` property specifies the delay duration while switching to next navigation item, when `EnableAutoPlay` property is enabled.

N> The property value should be in milliseconds.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfRotator x:Name="rotator" NavigationDelay="2000" />
	
{% endhighlight %}

{% highlight C# %}

    SfRotator rotator = new SfRotator();
	rotator.NavigationDelay = 2000;

{% endhighlight %}

{% endtabs %}

## Looping Items

The `EnableLooping` property specifies whether the items should navigate to first item once it reaches the last item and vice-versa.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfRotator x:Name="rotator" EnableLooping="true" />
	
{% endhighlight %}

{% highlight C# %}

    SfRotator rotator = new SfRotator();
	rotator.EnableLooping = true;

{% endhighlight %}

{% endtabs %}



