---
layout: post
title: IsBusy support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to enable and disable animation in SfBusyIndicator
platform: Xamarin.Forms
control: BusyIndicator
documentation: ug
---
# IsBusy

The `IsBusy` property in SfBusyIndicator control is used to determine whether an animation needs to be executed or not.

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.IsBusy=true;

{% endhighlight %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" IsBusy="true" />
	
{% endhighlight %}

{% endtabs %}

![](images/IsBusy.png) 


