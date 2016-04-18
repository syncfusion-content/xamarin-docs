---
layout: post
title: Date Navigation and Gestures with Syncfusion Calendar control for Xamarin.Forms
description: Learn the complete navigation and gestures support
platform: xamarin
control: Calendar
documentation: ug
---

# Date Navigation and Gesture

## Transition Modes

Dates can be navigated by using swipe gesture as well as using built-in methods `forward` and `backward`. By default those navigation are performed along with Scroll animation. Other than the default scroll animation, there are other options available like card, reveal, float animations. It can be changed by using  transitionMode property of calendar control.

{% highlight c# %}
	
	sfCalendar.TransitionMode=TransitionMode.Float;
	
{% endhighlight %}

### Forward

By default, the date can be navigated to next view using touch gesture and swiping the control in right to left direction. The view also can be changed programmatically using `forward` method available in SfCalendar. It will move to next month, if the view mode is month or it will move to next Year, if the view mode is year.

N> It can be navigated until it reaches the MaxDate.

{% highlight c# %}

	calendar.Forward();

{% endhighlight %}

### Backward

By default, the date can be navigated to previous view using touch gesture and swiping the control in left to right direction. The view also can be changed programmatically using `backward` method available in SfCalendar. It will move to previous month, if the view mode is month or it will move to previous year, if view mode is year view.

N> It can be navigated until it reaches the MinDate.

{% highlight c# %}

	calendar.Backward();

{% endhighlight %}

## Move to Date 

Visible dates can be moved to specific date using `MoveToDate` property available in Calendar. It will move to any specific month if the view mode is month view or move to year if it is a year view.

N>  The specified date should lie between MinDate and MaxDate, if  the specified date is greater than MaxDate then the view will be moved to maxDate and if the specified date is lesser than the MinDate then the view will be moved to minDate.

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

## Toggle  navigation

By default, calendar views can be moved backwards and forwards using touch swipe gesture.  This navigation, using touch gesture can be enabled and disabled using `NavigationEnabled` property available in Calendar control. By default, `NavigationEnabled` property is enabled.

{% highlight c# %}

    calendar.ViewMode=ViewMode.MonthView;
	calendar.NavigationEnable=false;

{% endhighlight %}