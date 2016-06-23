---
layout: post
title: Sizing support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to customize the size of the control viewbox
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Sizing

## ViewBoxHeight

The `ViewBoxHeight` property allows the user to set the height of the control ViewBox. 

## ViewBoxWidth

The `ViewBoxWidth` property allows the user to set the width of the control ViewBox.

{% tabs %}

{% highlight c# %}
    SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType=AnimationTypes.SlicedCircle;
	busyindicator.ViewBoxHeight=20;
	busyindicator.ViewBoxWidth=20;

{% endhighlight %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="SlicedCircle" ViewBoxHeight="20" ViewBoxWidth="20" />
	
{% endhighlight %}

{% endtabs %}

![](images/heightand width.png)  



