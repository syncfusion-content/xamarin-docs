---
layout: post
title: Interactive Selection modes in Syncfusion Calendar control for Xamarin.Forms
description: How to Perform an operation when navigate to next month
platform: Xamarin
control: Calendar
documentation: ug
---

# How to Perform an operation when navigate to next month?

User defined operation can be performed using `MonthChanged` event when navigating to next month. This event returns the details about current value and previous value of month.

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
<td>Args</td>
<td>Carries details about MonthEventParameters</td>
</tr>
</table>
                                    

{% highlight c# %}

	sfcalendar.MonthChanged += (object sender, MonthChangedEventArgs args) =>
			{
				SfCalendar calendar = args.Calendar;
				DateTime oldMonth = args.args.PreviousValue;
				DateTime currentMonth = args.args.CurrentValue;
			};
{% endhighlight %}
