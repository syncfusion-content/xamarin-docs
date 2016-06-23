---
layout: post
title: FirstDayofWeek support in Syncfusion Calendar control for Xamarin.Forms
description: Learn how to change the first day of week
platform: Xamarin
control: Calendar
documentation: ug
---

# First Day of Week

By default, the starting day will be Sunday. This can be modified using `FirstDayofWeek` property. Changing the first day of week will be applied to both month and year view.

{% tabs %}

{% highlight c# %}
	
	sfCalendar.FirstDayofWeek= 4;
	
{% endhighlight %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" FirstDayofWeek="4"/>

{% endhighlight %}

{% endtabs %}
	
![](images/Firstdayofweek.png)