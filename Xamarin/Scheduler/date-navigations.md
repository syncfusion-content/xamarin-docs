---
layout: post
title: Dates, Navigations and Gestures in Syncfusion SfSchedule Xamarin.Forms
description: This section describes the complete navigation and gestures support in SfSchedule control in Xamarin.Forms
platform: xamarin
control: SfSchedule
documentation: ug
---

# Date Navigations in Xamarin Scheduler (SfSchedule)

## Enabling Navigation 
By default, Schedule views can be moved backwards and forwards using touch swipe gesture. This navigation gesture can be enabled or disabled by setting [EnableNavigation](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_EnableNavigation) property of `SfSchedule`. By default, it is enabled.

{% tabs %}   
{% highlight xaml %} 
<schedule:SfSchedule EnableNavigation="False"/>
{% endhighlight %}   
{% highlight c# %} 
//disabling navigation gesture
schedule.EnableNavigation = false;
{% endhighlight %}   
{% endtabs %}

>**NOTE**
**Move to time**:
*   The scrolled position of timeslots will be maintained in day/week/work week view when swiping the next or previous views and switching between day, week or work week views,
*   If view switch from month/timeline view to week/work/day week views, move to time will be considered if move time mentioned in `MoveToDate` otherwise, position scrolled to `work start hour` in day/week/work week views.


## Programmatically change to specific dates 
Visible dates can be moved to specific date using [NavigateTo](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_NavigateTo_System_DateTime_) method and [MoveToDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_MoveToDate) property available in SfSchedule. It will move to any specific date if the schedule view is Day View, similarly it will move to the specific week if it is week view and to specific month if it is month view

{% tabs %}
{% highlight c# %} 
//using NavigateTo

DateTime currentDate = DateTime.Now;
DateTime SpecificDate = new DateTime(currentDate.Year - 5,currentDate.Month - 3, currentDate.Day, 0, 0, 0);
Schedule.NavigateTo(SpecificDate);

//using MoveToDate
DateTime currentDate = DateTime.Now;
DateTime SpecificDate = new DateTime(currentDate.Year - 5,currentDate.Month - 3, currentDate.Day, 0, 0, 0);
Schedule.MoveToDate = SpecificDate;
{% endhighlight %} 
{% endtabs %}  

>**NOTE**
The specified date should lies between MinDisplayDate and MaxDisplayDate, if the specified date is greater than *MaxDisplayDate* then the view moved to MaxDisplayDate similarly if the specified date is lesser than the *MinDisplayDate* then the view moved to MinDisplayDate.


## Programmatically change to adjacent dates.
By default the date can be navigated to next and previous view using touch gesture, by swiping the control in right to left and right to left direction. The view can be also changed programmatically using [Forward](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_Forward) and [Backward](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_Backward) method available in SfSchedule. 

*  	Forward
*	Backward

### Forward
You can use the `Forward` method for viewing the next immediate visible dates in the SfSchedule. It will move to next month if the schedule view is month, similarly it will move to next week for week view and next day for day view.

{% tabs %}
{% highlight c# %} 
//Viewing next immediate visible dates
schedule.Forward();
{% endhighlight %}  
{% endtabs %} 

>**NOTE**
Date can be navigated until it reaches the Min Max date.**


### Backward
You can use the `Backward` method for viewing the previous immediate visible dates in the SfSchedule. It will move to previous month if the schedule view is month, similarly it will move to previous week for week view and previous day for day view.

{% tabs %}
{% highlight c# %} 
//Viewing previous immediate visible dates
schedule.Backward();
{% endhighlight %}   
{% endtabs %}

>**NOTE**
Date can be navigated until it reaches the Min Max date.**


## Range for visible dates
Visible dates can be restricted between certain range of dates, using [MinDisplayDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_MinDisplayDate)  and [MaxDisplayDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_MaxDisplayDate)  property in `SfSchedule`. It is applicable in all the schedule views.

### Minimum Display Date
`MinDisplayDate` will restrict date navigations features of `Backward`, `MoveToDate` and also can’t swipe the control using touch gesture beyond the min max date range. Thus, Inline and selection feature in month view will works only within the min max date range.

{% tabs %}
{% highlight c# %} 
int monthRange = 2; DateTime currentDate = DateTime.Now;
//setting minimum display date
DateTime minDate = new DateTime(currentDate.Year, currentDate.Month - monthRange, currentDate.Day, 10, 0, 0);
schedule.MinDisplayDate = minDate;
{% endhighlight %}   
{% endtabs %}

### Maximum Display Date
`MaxDisplayDate` will restrict date navigations features of `Forward`, `MoveToDate` and also can’t swipe the control using touch gesture beyond the max date range. Thus, Inline and selection in month view will works only within the max date range.


{% tabs %}
{% highlight c# %} 
int monthRange = 2; DateTime currentDate = DateTime.Now;
//setting maximum display date
DateTime maxDate = new DateTime(currentDate.Year, currentDate.Month + monthRange, currentDate.Day, 10, 0, 0);
schedule.MaxDisplayDate = maxDate;
{% endhighlight %}   
{% endtabs %}


## VisibleDatesChanged event
You can get the visible dates of the Schedule using [VisibleDatesChangedEvent](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html) in `SfSchedule`. It is applicable in all the schedule views.The event handler receives an argument of type [VisibleDatesChangedEventArgs](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.VisibleDatesChangedEventArgs.html) containing [visibleDates](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.VisibleDatesChangedEventArgs.html#Syncfusion_SfSchedule_XForms_VisibleDatesChangedEventArgs_visibleDates) and [Schedule](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.VisibleDatesChangedEventArgs.html#Syncfusion_SfSchedule_XForms_VisibleDatesChangedEventArgs_Schedule).


{% tabs %}
{% highlight c# %} 
schedule.VisibleDatesChangedEvent += Schedule_VisibleDatesChangedEvent;

..... 

private void Schedule_VisibleDatesChangedEvent(object sender, VisibleDatesChangedEventArgs e)
{
	var visibleDates = e.visibleDates;
	var Schedule = e.Schedule;
}
{% endhighlight %}  
{% endtabs %}

`VisibleDatesChangedEvent` will be triggered when view is swiped back or forth and also when schedule view is switched dynamically.

You can add appointments on demand based on the visible date range in this event by setting DataSource property to schedule in the VisibleDatesChangedEvent.

{% tabs %}
{% highlight c# %} 
private void Schedule_VisibleDatesChangedEvent(object sender, VisibleDatesChangedEventArgs e)
{
	schedule.DataSource = scheduleAppointmentCollection;
} 
{% endhighlight %}  
{% endtabs %}

You can also move to specific time of the day or current time of day when view is swiped by setting specific time in MoveToDate property in the VisibleDatesChanged event. Such that when the schedule view is swiped, it moves to the mentioned time.  

{% tabs %}
{% highlight c# %}
schedule.VisibleDatesChangedEvent += Schedule_VisibleDatesChangedEvent;

...

private void Schedule_VisibleDatesChangedEvent(object sender, VisibleDatesChangedEventArgs e)
{
	var date = DateTime.Now;
	var formatDate = e.visibleDates[0];
	schedule.MoveToDate = new DateTime(formatDate.Year, formatDate.Month, formatDate.Day, date.Hour, date.Minute, date.Second);
}
{% endhighlight %}  
{% endtabs %}
