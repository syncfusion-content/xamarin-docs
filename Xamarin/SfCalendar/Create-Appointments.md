---
layout: post
title: Populating Events in Syncfusion Calendar control for Android
description: Learn how to create appointments
platform: Xamarin
control: Calendar
documentation: ug
---

# Create Appointments

This section explains the programmatic creation of appointments in SfCalendar control.

## Programmatic Creation

SfCalendar control has an built-in capability to display the events based on the calendar events collection provided to `DataSource` property. For events to be listed for a particular day, enable the inline feature in month view cell.

The default UI of the inline view with events will be like list of events with a Gray background

![](images/Event.png)

Inline event support can be toggled on / off with `ShowInLineEvent` property.
    
{% tabs %}    
    
{% highlight c# %}
	
	sfcalendar.ShowInLineEvent=true;
	
{% endhighlight %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" ShowInlineEvent="true" />

{% endhighlight %}

{% endtabs %}
	
N> The Inline function will be available only in MonthView with Single selection mode.
	
### Adding events using collection

Calendar Events collection can be provided to SfCalendar using the following steps. `CalendarEventCollection` is a class, which holds the details about the events to be rendered in calendar. 

`CalendarInlineEvent` has some basic properties such as `StartTime`, `EndTime` and `Subject`.



{% highlight c# %}
		   
    CalendarInlineEvent event=new CalendarInlineEvent();
    event.StartTime=new DateTime(2015,1,1);
    event.EndTime=new DateTime(2015,1,1);
    event.Subject=”Go to Meeting”;
    event.Color=Color.Red;
		   
{% endhighlight %}




	

	
