---
layout: post
title: Interactive Selection modes in Syncfusion Calendar control for Xamarin.Forms
description: How to Perform an operation while a calendar cell is Tapped
platform: Xamarin
control: Calendar
documentation: ug
---

# How to Perform an operation while a calendar cell is Tapped?

We can perform operation while the Calendar cell is Tapped using `CalendarTapped` event. CalendarTapped event returns the date selected and the Appointments that are associated with the date selected.

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