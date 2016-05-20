---
layout: post
title: Title support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to add title description to SfBusyIndicator
platform: Xamarin.Forms
control: BusyIndicator
documentation: ug
---
# Title

The `Title` property can be used to get or set the text that indicates the information related to loading. 

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator(this);
	busyindicator.Title =”Loading…”;

{% endhighlight %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" Title="Loading..." />
	
{% endhighlight %}

{% endtabs %}

## FontFace

The `FontFace` property can be used to define the font style and size of the title.

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyindicator = new SfBusyIndicator(this);
	busyindicator.Title="Loading...";
	busyindicator.Fontface=Typeface.create("Arial",Typeface.BOLD);

{% endhighlight %}

{% highlight xaml %}

	<busyindicator:SfBusyIndicator x:Name="busyindicator" Title="Loading..."  Fontface="Bold"/>
	
{% endhighlight %}

{% endtabs %}


![](images/Title.png) 


