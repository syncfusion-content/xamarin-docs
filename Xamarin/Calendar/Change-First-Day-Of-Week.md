---
layout: post
title: Change First Day Of Week in Xamarin Calendar control | Syncfusion<sup>&reg;</sup>
description: Learn here all about Change First Day Of Week support in Syncfusion<sup>&reg;</sup> Xamarin Calendar (SfCalendar) control and more.
platform: xamarin
control: Calendar
documentation: ug
---

# Change First Day Of Week in Xamarin Calendar (SfCalendar)

By default, the starting day will be taken from the device culture. This can be modified using [FirstDayofWeek](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_FirstDayofWeek) property. Changing the first day of week will be applied to both month and year view.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" FirstDayofWeek="2"/>

{% endhighlight %}

{% highlight c# %}
	
SfCalendar  calendar = new SfCalendar();
calendar.FirstDayofWeek= 2;
this.Content = calendar;
	
{% endhighlight %}

{% endtabs %}

N> The value will be provided as integers starting from 0 as Sunday.
	
![FirstDayofWeek support in Xamarin.Forms Calendar](images/xamarin.forms-calendar-firstdayofweek.png)
