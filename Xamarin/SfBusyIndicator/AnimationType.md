---
layout: post
title: AnimationTypes in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn various animation types available in SfBusyIndicator
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Animation Type

The `AnimationType` property allows you to choose anyone of the 10 predefined animation types.

* Ball
* HorizontalPulsingBox
* Rectangle
* Battery
* Globe
* SingleCircle
* SlicedCircle
* DoubleCircle
* ECG
* Print

{% tabs %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="Ball" />

{% endhighlight %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType=AnimationTypes.Ball;
	
{% endhighlight %}

{% endtabs %}

![](images/Ball.png) 
