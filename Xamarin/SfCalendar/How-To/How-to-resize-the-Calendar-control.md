---
layout: post
title: Resizing the Syncfusion Calendar control for Xamarin.Forms
description: Learn how to resize the Calendar control
platform: Xamarin
control: Calendar
documentation: ug
---

# How to resize the SfCalendar control

SfCalendar control can be resized using `WidthRequest` and `HeightRequest` properties in SfCalendar control.


{% tabs %}

{% highlight c# %}

calendar = new SfCalendar();
calendar.WidthRequest = 200;
calendar.HeightRequest = 200;
	
{% endhighlight %}

{% endtabs %}