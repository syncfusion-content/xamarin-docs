---
layout: post
title: IsBusy support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to enable and disable animation in SfBusyIndicator
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Make Busy Animation Idle

The `IsBusy` property in SfBusyIndicator control is used to determine whether an animation needs to be executed or not.

{% tabs %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="Ball" IsBusy="true" />
	
{% endhighlight %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType=AnimationTypes.Ball;
	busyindicator.IsBusy=true;

{% endhighlight %}

{% endtabs %}

![](images/IsBusy.png) 


