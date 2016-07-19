---
layout: post
title: Interactive Selection modes in Syncfusion Calendar control for Xamarin.Forms
description: How to Perform an operation when the selected date get changed
platform: Xamarin
control: Calendar
documentation: ug
---

# How to Perform an operation when the selected date get changed?

We can perform an operation when the selected date get changed using `SelectionChanged` event which returns the dates selected and dates deselected from the SfCalendar.

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
<td>DateAdded</td>
<td>Date selected from the calendar</td>
</tr>
<tr>
<td>DateRemoved</td>
<td>Date deselected from the calendar</td>
</tr>
</table>


{% tabs %}

{% highlight c# %}

	sfcalendar.SelectionChanged += (object sender, SelectionChangedEventArgs args) =
			{
				SfCalendar calendar = args.Calendar;
				IList<DateTime> selectedDates = args.DateAdded;
				IList<DateTime> deselectedDates = args.DateRemoved;
			};
{% endhighlight %}

{% endtabs %}