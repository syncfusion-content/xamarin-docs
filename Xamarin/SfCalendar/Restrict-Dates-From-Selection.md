---
layout: post
title: Blackout dates | SfCalendar | Xamarin.Forms | Syncfusion
description: Learn how to set min and max date in calendar
platform: Xamarin
control: Calendar
documentation: ug
---

# Restrict Dates From Selection

Dates can be restricted or a collection of dates can be blacked out in `SfCalendar` Control.

## Range of Min / Max Dates

Visible dates can be restricted between certain range of dates using `MinDate` and `MaxDate` properties available in `SfCalendar` control. It is applicable in all the calendar views.

The inline feature in month view will work only within the min max date range.

Beyond the min max date range, following restrictions will be applied.

* Date navigation features of move to date will be restricted.

* Cannot swipe the control using touch gesture.

* Selection does not work for month view.

* The tapped delegates will not be triggered while tapped on the MonthCell.
    

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();    
DateTime minDate=new DateTime(2015,1,1);
calendar.MinDate=minDate;
DateTime maxDate=new DateTime(2040,12,12);
calendar.MaxDate=maxDate;
this.Content = calendar;
	
{% endhighlight %}

## Blackout Dates

In `SfCalendar`, BlackoutDates refers the disabled dates that restrict the user from selecting it. These dates will be marked with slanted Stripes.

The BlackoutDays can be achieved in two ways.

A date collection can be provided to set the `BlackoutDates`. This is useful when one wants to block dates where holidays or any other events occur.

By invoking the `AddDatesInPast` method, all past dates will be blacked out till current date.

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();        
List<DateTime> black_dates = new List<DateTime>();
black_dates.Add (new DateTime(2016,1,20));
black_dates.Add (new DateTime(2016,1,21));
black_dates.Add (new DateTime(2016,1,22));
black_dates.Add (new DateTime(2016,1,23));
black_dates.Add (new DateTime(2016,1,24));
calendar.BlackoutDates= black_dates ;
this.Content = calendar;
	
{%  endhighlight %}
	
![BlackoutDate support in Xamarin.Forms Calendar](images/xamarin.forms-calendar-Blackout.png)