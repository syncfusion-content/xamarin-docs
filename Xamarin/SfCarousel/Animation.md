---
layout : post
title : Transformation in Syncfusion Carousel control in Xamarin.Forms
description : Learn how to set the Rotation Angle and Offset in Carousel for Xamarin.Forms
platform : Xamarin
control : Carousel
documentation : ug
---

# Animation

The `Duration` property of the SfCarousel control is used to specify the time taken to move an item to the selected item position. The duration is specified in seconds.  The default value is 300 ms.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfCarousel x:Name="carousel" Duration="1000" />
	
{% endhighlight %}

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();
	carousel.Duration = 1000;
	

{% endhighlight %}

{% endtabs %}

