---
layout: post
title: Title support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to add title description to SfBusyIndicator
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Set Header and Font

The `Title` property can be used to get or set the text that indicates the information related to loading. The `FontFace` property can be used to define the font style and size of the title.

{% tabs %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" AnimationType="Ball" Title="Loading..."  Fontface="Bold"/>
	
{% endhighlight %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator();
	busyindicator.AnimationType=AnimationTypes.Ball;
	busyindicator.Title ="Loading…";
	busyindicator.Fontface=Typeface.create("Arial",Typeface.NONE);

{% endhighlight %}

{% endtabs %}

![](images/Title.png) 


