---
layout: post
title: FirstDayofWeek support in Syncfusion Calendar control for Xamarin.Forms
description: Learn how to change the first day of week
platform: Xamarin
control: Calendar
documentation: ug
---

# Change First Day Of Week

By default, the starting day will be taken from the device culture. This can be modified using `FirstDayofWeek` property. Changing the first day of week will be applied to both month and year view.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" FirstDayofWeek="2"/>

{% endhighlight %}

{% highlight c# %}
	
	calendar.FirstDayofWeek= 2;
	
{% endhighlight %}

{% endtabs %}

N> The value will be provided as integers starting from 0 as Sunday.
	
![](images/Firstdayofweek.png)