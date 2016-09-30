---
layout: post
title: Title support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to add title description to SfBusyIndicator
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Set Header

SfBusyIndicator provides option to set the text that indicates the information related to loading. This can be done using `Title` property.

{% tabs %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="Ball" Title="Loading..." />
	
{% endhighlight %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType=AnimationTypes.Ball;
	busyindicator.Title ="Loading…";

{% endhighlight %}

{% endtabs %}

![](images/Title.png) 


