---
layout: post
title: Events in Syncfusion Calendar control for Xamarin.Forms
description: Learn how to populate events in calendar control
platform: Xamarin.Forms
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
<tr>
<td>SelectionChanged</td>
<td>Triggered when selected date is changed.</td>
</tr>
<tr>
<td>MonthChanged</td>
<td>Triggered when month is changed from one to another.</td>
</tr>
<tr>
<td>InlineToggled</td>
<td>Triggered when Inline event is clicked.</td>
</tr>
<tr>
<td>OnDrawMonthCell</td>
<td>Triggered when month cell is drawn.</td>
</tr>
<tr>
<td>OnDrawYearCell</td>
<td>Triggered when year cell is drawn.</td>
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

##  SelectionChanged Event

SelectionChanged event returns the dates selected and dates deselected from the calendar.

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
                                                
## MonthChanged Event

MonthChanged event returns the details about current value and previous value of month.

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
                                    
{% tabs %}

{% highlight c# %}

	sfcalendar.MonthChanged += (object sender, MonthChangedEventArgs args) =>
			{
				SfCalendar calendar = args.Calendar;
				DateTime oldMonth = args.args.PreviousValue;
				DateTime currentMonth = args.args.CurrentValue;
			};
{% endhighlight %}

{% endtabs %}

## InlineToggled Event

InlineToggled event returns the selected date along with the appointments it carries.

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

## OnMonthCellLoaded Event 

OnMonthCellLoaded  event allows us to customize calendar control. It returns MonthCell args

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Args</td>
<td>Carries details about MonthCell</td>
</tr>
</table>

### MonthCell

MonthCell consisting of following members which allows us to customize calendar control in Month View mode.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>BackgroundColor</td>
<td>Allows us to set background color for each cell</td>
</tr>
<tr>
<td>TextColor</td>
<td>Allows us to set Text color for each date</td>
</tr>
<tr>
<td>BorderColor</td>
<td>Allows us to set border color</td>
</tr>
<tr>
<td>Date</td>
<td>It shows the datetime in Calendar</td>
</tr>
<tr>
<td>FontAttribute</td>
<td>Allows  us to set font attributes for  calendar text</td>
</tr>
</table>

{% tabs %}

{% highlight c# %}

	sfcalendar.OnDrawMonthCell += (object sender, MonthCell args) =>
			 {
				 DateTime dTime = args.Date;
				 args.BackgroundColor = Color.FromRgb(237, 236, 237);
				 args.TextColor = Color.FromRgb(61, 61, 61);
				 args.BorderColor = Color.FromRgb(40, 100, 80);
				 args.FontAttribute = FontAttributes.Bold;
			};
{% endhighlight %}

{% endtabs %}


