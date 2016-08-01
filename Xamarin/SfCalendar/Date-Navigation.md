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

Dates can be navigated by using swipe gesture as well as using built-in methods named `Forward` and `Backward`. By default those navigations are performed along with Scroll animation. Other than the default scroll animation, there are other options available like card, reveal, float animations. It can be changed by using `TransitionMode` property of SfCalendar control.

{% tabs %}
{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" ViewMode="MonthView" TransitionMode="Float"/>

{% endhighlight %}

{% highlight c# %}
	
	calendar.TransitionMode=TransitionMode.Float;
	
{% endhighlight %}

{% endtabs %}

N> This transitions works only for Month view.

## Programmatic Navigation

Date can be navigated to next view using Forward and Backward methods in SfCalendar control. 

### Forward

By default, the date can be navigated to next view using touch gesture and swiping the control in right to left direction. The view can also be changed programmatically using `Forward` method available in SfCalendar. It will move to next month, if the view mode is month or it will move to next Year,if the view mode is year.

{% tabs %}

{% highlight c# %}

	DependencyService.Get<ICalendarDirection>().Forward();

{% endhighlight %}

{% endtabs %}


N> It can be navigated until it reaches the MaxDate.

### Backward

By default, the date can be navigated to previous view using touch gesture and swiping the control in left to right direction. The view can also be changed programmatically using `Backward` method available in SfCalendar. It will move to previous month, if the view mode is month or it will move to previous year, if the view mode is year view.
{% tabs %}

{% highlight c# %}

	DependencyService.Get<ICalendarDirection>().Backward();

{% endhighlight %}

{% endtabs %}


N> It can be navigated until it reaches the MinDate.

### Move to Date 

Visible dates can be moved to specific date using `MoveToDate` property available in SfCalendar. It will move to any specific month if the view mode is month view or move to year if it is a year view.

N>  The specified date should lie between MinDate and MaxDate, if the specified date is greater than MaxDate then the view will be moved to MaxDate and if the specified date is lesser than the MinDate then the view will be moved to MinDate.

{% tabs %}

{% highlight xaml %}

		<Calendar:SfCalendar  x:Name="calendar" MoveToDate="2017,5,5"  ViewMode="MonthView"  VerticalOptions="FillAndExpand"/>

{% endhighlight %}

{% highlight c# %}

	calendar.MoveToDate = new DateTime(2017,5,5);
	
{% endhighlight %}

{% endtabs %}
