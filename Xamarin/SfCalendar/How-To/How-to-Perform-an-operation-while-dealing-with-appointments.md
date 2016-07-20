---
layout: post
title: Interactive Selection modes in Syncfusion Calendar control for Xamarin.Forms
description: How to Perform an operation while dealing with appointments
platform: Xamarin
control: Calendar
documentation: ug
---

# How to Perform an operation while dealing with appointments?

`InlineToggled` event returns the selected date along with the appointments it carries. Using this event user can perform operation while dealing with appointments.

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
<td>SelectedAppointment</td>
<td>Appointments from the selected date</td>
</tr>
</table>

{% tabs %}

{% highlight c# %}

	sfcalendar.InlineToggled += (object sender, InlineToggledEventArgs args) => {

				string subject = args.selectedAppointment[0].Subject;
				DateTime startTime = args.selectedAppointment[0].StartTime;
				DateTime endTime = args.selectedAppointment[0].EndTime;
		
			};
{% endhighlight %}

{% endtabs %}