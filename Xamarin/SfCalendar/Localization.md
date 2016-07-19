---
layout: post
title: Localization support in Syncfusion Calendar control for Xamarin.Forms
description: Learn how to localize your calendar to regional language
platform: Xamarin
control: Calendar
documentation: ug
---

# Localization

SfCalendar control is available with complete localization support.
 
Localization can be specified by setting the `Locale` property of the control using the format of Language code followed by Country code. Based on the locale specified, the strings in the control are localized accordingly.
 
N> By default, SfCalendar control is available with en-US locale.      
     
Control has been initialized in Xaml

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar"/>

{% endhighlight %}

and culture has been set in codes.

{% highlight c# %}

	sfCalendar.Locale= new System.Globalization.CultureInfo("zh-CN");
	
{% endhighlight %}


![](images/Localization.png)