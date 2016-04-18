---
layout: post
title: Events in Syncfusion Calendar control for Xamarin.Forms
description: Learn how to populate events in calendar control
platform: xamarin
control: Calendar
documentation: ug
---

# Calendar Events

The events of the Calendar control are as follows.

<table>
<tr>
<th>Calendar Events</th>
<th>Description</th>
</tr>
<tr>
<td>OnCalendarTapped</td>
<td>Triggered when each cell in calendar is clicked.</td>
</tr>
</table>


##  OnCalendarTapped Event

CalendarTapped event returns the date selected and the Appointments that are associated with the date selected.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Calendar</td>
<td>Displays the native control</td>
</tr>
<tr>
<td>DateTime</td>
<td>It shows the datetime in Calendar</td>
</tr>
</table>


{% tabs %}

{% highlight c# %}

	sfCalendar.OnCalendarTapped+= (object sender, CalendarTappedEventArgs args) => 
			{
				SfCalendar calendar = args.Calendar;
				DateTime date = args.datetime;
				
			};

{% endhighlight %}

{% endtabs %}
                                                

                                    
