---
layout: post
title: Date Navigation and Gestures with Syncfusion Calendar control for Xamarin.Forms
description: Learn the complete navigation and gestures support
platform: Xamarin
control: Calendar
documentation: ug
---

# Date Navigation

This section explains about the programmatic and gesture navigation support available in SfCalendar control.

## Transition Modes

Dates can be navigated by using swipe gesture as well as using built-in methods `forward` and `backward`. By default those navigation are performed along with Scroll animation. Other than the default scroll animation, there are other options available like card, reveal, float animations. It can be changed by using `TransitionMode` property of SfCalendar control.

{% tabs %}

{% highlight c# %}
	
	sfCalendar.TransitionMode=TransitionMode.Float;
	
{% endhighlight %}

{% endtabs %}

## Programmatic Navigation

Date can be navigated to next view using Froward and Backward methods in SfCalendar control. 

### Forward

By default, the date can be navigated to next view using touch gesture and swiping the control in right to left direction. The view can also be changed programmatically using `forward` method available in SfCalendar. It will move to next month, if the view mode is month or it will move to next Year, if the view mode is year.

{% tabs %}

{% highlight c# %}

	DependencyService.Get<ICalendarDirection>().Forward();

{% endhighlight %}

{% endtabs %}

N> It can be navigated until it reaches the MaxDate.

### Backward

By default, the date can be navigated to previous view using touch gesture and swiping the control in left to right direction. The view also can be changed programmatically using `backward` method available in SfCalendar. It will move to previous month, if the view mode is month or it will move to previous year, if view mode is year view.

{% tabs %}

{% highlight c# %}

	DependencyService.Get<ICalendarDirection>().Backward();

{% endhighlight %}

{% endtabs %}

N> It can be navigated until it reaches the MinDate.

### Move to Date 

Visible dates can be moved to specific date using `MoveToDate` property available in Calendar. It will move to any specific month if the view mode is month view or move to year if it is a year view.

N>  The specified date should lie between MinDate and MaxDate, if the specified date is greater than MaxDate then the view will be moved to MaxDate and if the specified date is lesser than the MinDate then the view will be moved to MinDate.

{% tabs %}

{% highlight c# %}

Calendar moveToDate = Calendar.getInstance();   
    moveToDate.Set
        (
                2010,
                Calendar.AUGUST,
                25,
                0,
                0,
                0
        );
    calendar.MoveToDate=moveToDate;
	
{% endhighlight %}

{% endtabs %}

## Gesture Navigation

By default, calendar views can be moved backwards and forwards using touch swipe gesture. This navigation, using touch gesture can be enabled and disabled using `NavigationEnabled` property available in SfCalendar control. By default, `NavigationEnabled` property is enabled.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" ViewMode="MonthView" NavigationEnabled="false"/>

{% endhighlight %}

{% highlight c# %}

    calendar.ViewMode=ViewMode.MonthView;
	calendar.NavigationEnable=false;

{% endhighlight %}

{% endtabs %}