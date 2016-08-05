---
layout: post
title: AnimationTypes in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn various animation types available in SfBusyIndicator
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Animation Type

The `AnimationType` property for the SfBusyIndicator allows the user to set one of the 10 animations from the built-in animations.

{% tabs %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="Ball" Title="Loading..." BackgroundColor="Color.Blue"/>

{% endhighlight %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType=AnimationTypes.Ball;
	busyindicator.Title ="Loading…";
	busyindicator.BackgroundColor= Color.Blue;
	
{% endhighlight %}

{% endtabs %}

![](images/ball1.png)

Busy Indicator with Ball type animation 
{:.caption}

![](images/HorizontalPulsingBox.png) 

Busy Indicator with HorizontalPulsingBox type animation 
{:.caption}

![](images/rectangle.png) 

Busy Indicator with Rectangle type animation 
{:.caption}
 
![](images/battery.png) 

Busy Indicator with Battery type animation 
{:.caption}
 
![](images/globe.png) 

Busy Indicator with Globe type animation 
{:.caption}
 
![](images/singlecircle.png) 

Busy Indicator with SingleCircle type animation 
{:.caption}

![](images/SlicedCircle.png) 

Busy Indicator with SlicedCircle type animation 
{:.caption}
 
![](images/doublecircle.png) 

Busy Indicator with DoubleCircle type animation 
{:.caption}
 
![](images/ecg.png) 

Busy Indicator with ECG type animation 
{:.caption}
 
![](images/print.png) 

Busy Indicator with Print type animation 
{:.caption}





 
