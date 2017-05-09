---
layout: post
title: Interactive Selection modes in Syncfusion Calendar control for Xamarin.Forms
description: How to Perform an operation while a calendar cell is Tapped
platform: Xamarin
control: Calendar
documentation: ug
---

# How to Perform an Operation while a Calendar Cell is Tapped?

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

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" OnCalendarTapped="Handle_OnCalendarTapped" />

{% endhighlight %}

{% highlight c# %}
	
void Handle_OnCalendarTapped(object sender, Syncfusion.SfCalendar.XForms.CalendarTappedEventArgs args)
{
	SfCalendar calendar = args.Calendar;
	DateTime date = args.datetime;		
}
	
{% endhighlight %}

{% endtabs %}

# How to Perform an Operation when the Selected Date Get Changed?

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

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="MonthView"  SelectionChanged="Handle_SelectionChanged" />

{% endhighlight %}

{% highlight c# %}
	
void Handle_SelectionChanged(object sender, Syncfusion.SfCalendar.XForms.SelectionChangedEventArgs args)
{
	SfCalendar calendar = args.Calendar;
	IList<DateTime> selectedDates = args.DateAdded;
	IList<DateTime> deselectedDates = args.DateRemoved;
}
	
{% endhighlight %}

{% endtabs %}


# How to Perform an Operation when Navigate to Next Month?

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
                                    
{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="MonthView" MonthChanged="Handle_MonthChanged" />

{% endhighlight %}

{% highlight c# %}
	
void Handle_MonthChanged(object sender, Syncfusion.SfCalendar.XForms.MonthChangedEventArgs args)
{
	SfCalendar calendar = args.Calendar;
	DateTime oldMonth = args.args.PreviousValue;
	DateTime currentMonth = args.args.CurrentValue;
}
	
{% endhighlight %}

{% endtabs %}


# How to Perform an Operation while Dealing with Appointments?

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

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" InlineToggled="Handle_InlineToggled" />

{% endhighlight %}

{% highlight c# %}
	
void Handle_InlineToggled(object sender, Syncfusion.SfCalendar.XForms.InlineToggledEventArgs args)
{
		string subject = args.selectedAppointment[0].Subject;
		DateTime startTime = args.selectedAppointment[0].StartTime;
		DateTime endTime = args.selectedAppointment[0].EndTime;	
}
	
{% endhighlight %}

{% endtabs %}


# How to Customize Cell or Month View?

`OnMonthCellLoaded` event allows us to customize SfCalendar control. It returns MonthCell args

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

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="MonthView"  OnMonthCellLoaded="Handle_OnMonthCellLoaded"  />

{% endhighlight %}

{% highlight c# %}

void Handle_OnMonthCellLoaded(object sender, Syncfusion.SfCalendar.XForms.MonthCell args)
{

	if ((args.Date.DayOfWeek == DayOfWeek.Sunday || args.Date.DayOfWeek == DayOfWeek.Saturday))
	{
		args.BackgroundColor = Color.Gray;
		args.TextColor = Color.Red;
	}
}

{% endhighlight %}

{% endtabs %}

# How to Perform the Operation while longpressing the dateCell

`OnDateCellHolding` event returns the long pressed date along with the SfCalendar it carries. Using this event user can perform operation while long pressing the date.


<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Args</td>
<td>Carries details with long pressed date and Calendar</td>
</tr>
</table>

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar x:Name="sfcalendar" OnDateCellHolding="Handle_OnDateCellHolding" />

{% endhighlight %}

{% highlight c# %}

calendar.OnDateCellHolding += (object sender, DayCellHoldingEventArgs args) =>
{
	// do the operation while long pressing the date cell
};

{% endhighlight %}

{% endtabs %}

# How to Resize the SfCalendar Control

SfCalendar control can be resized using `WidthRequest` and `HeightRequest` properties in SfCalendar control.

{% highlight c# %}

SfCalendar calendar = new SfCalendar();
calendar.WidthRequest = 200;
calendar.HeightRequest = 200;
	
{% endhighlight %}
