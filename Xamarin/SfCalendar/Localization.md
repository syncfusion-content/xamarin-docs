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
    
{% tabs %}    

{% highlight c# %}

	SfCalendar  calendar = new SfCalendar ();
	calendar.Locale= new System.Globalization.CultureInfo("zh-CN");
	
{% endhighlight %}

{% endtabs %}

N> By default, SfCalendar control is available with en-US locale.  

![](images/Localization.png)