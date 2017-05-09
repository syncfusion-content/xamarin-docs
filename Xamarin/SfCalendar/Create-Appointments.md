---
layout: post
title: Populating Events in Syncfusion Calendar control for Android
description: Learn how to create appointments
platform: Xamarin
control: Calendar
documentation: ug
---

# Create Appointments

SfCalendar control provides support to add appointments on calendar's dates. By the way of adding collection of appointments, it will show the event with indicator on the desired dates.

Calendar's events can be added to SfCalendar using the following ways. `CalendarEventCollection` holds the details about the events to be rendered in calendar. Events contains the following attributes

1. StartTime

2. EndTime

3. Subject

4. Color

Finally add this collection of CalendarInlineEvents into `DataSource` of SfCalendar. The following code example will help to create an appointments on Calendar's date. For events to be listed for a particular day, enable the inline feature in month view cell.

I> Inline event support can be toggled on / off with `ShowInlineEvents` property.

{% highlight c# %}
		   
SfCalendar calendar = new SfCalendar();
calendar.ShowInlineEvents = true;

CalendarInlineEvent events = new CalendarInlineEvent();
events.StartTime = new DateTime(2017, 5, 1,5,0,0);
events.EndTime = new DateTime(2017, 5, 1,7,0,0);
events.Subject = "Go to Meeting";
events.Color = Color.Fuchsia;

CalendarEventCollection collection = new CalendarEventCollection();
collection.Add(events);

calendar.DataSource = collection;

this.Content = calendar;
		   
{% endhighlight %}

N> The Inline function will be available only in MonthView with Single selection mode.

![](images/events.png)





	

	
