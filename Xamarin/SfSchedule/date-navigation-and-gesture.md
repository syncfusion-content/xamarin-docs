---
title: Date Navigation and Gesture in Syncfusion SfSchedule control for Xamarin.Forms Platform
description: Learn the complete navigation and gestures support
platform: xamarin
control: SfSchedule
documentation: ug
---

# Date Navigation and Gesture

## Forward

Schedule views by default can be navigated to next view using touch swipe gesture. The view can also be changed programatically using `Forward` and `Backward` methods available in `SfSchedule`.So that next immediate visible dates will be viewed. It will move to next month if the schedule views is month, similarly it will move to next week for week view and next day for day view.

{% highlight C# %}
    
    //using Schedule Forward()
    sfschedule.Forward();
    
{% endhighlight %}

## Backward

Schedule views by default can be navigated to previous view using touch swipe gesture. The view can also be changed programatically using `Backward` method available in `SfSchedule`.So that previous immediate visible dates will be displayed. It will move to previous month if the schedule views is month, similarly it will move to previous week for week view and previous day for day view.

{% highlight C# %}
    
    //using Schedule Backward()
    sfschedule.Backward();
    
{% endhighlight %}

## Navigate To

Visible dates can be moved to specific date using `NavigateTo` method available in `SfSchedule`. It will move to any specific date if the [ScheduleView](/xamarin/sfschedule/views "Schedule Views") is Day View, similarly it will move to the specific week if it is week view and to specific month if it is month view.

{% highlight c# %}

    DateTime currentDate = DateTime.Now;
    
    DateTime SpecificDate= new DateTime (currentDate.Year- 5,currentDate.Month-3, currentDate.Day, 0, 0, 0);

    sfschedule.NavigateTo(SpecificDate);

{% endhighlight %}

>**NOTE**:
The specified date should lies between `MinDisplayDate` and `MaxDisplayDate`, if the specified date is greater than `MaxDisplayDate` then the view moved to `MaxDisplayDate` similarly if the specified date is lesser than the `MinDisplayDate` then the view moved to `MinDisplayDate`.

## Enable/disable navigation

By default Schedule views can be moved backwards and forwards using touch swipe gesture. This navigation, using touch gesture can be enabled and disabled using `EnableNavigation` property available in `SfSchedule`. By default this is enabled.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule EnableNavigation="false"/>
    
{% endhighlight %}

{% highlight c# %}

    //disabling navigation gesture
    sfschedule.EnableNavigation = false;

{% endhighlight %}

{% endtabs %}

## Min Max dates.

Visible dates can be restricted between certain range of dates using `MinDisplayDate` and `MaxDisplayDate` properties available in Schedule control. It is applicable in all the schedule views.

So that beyond the min max date range, it will restrict date navigations features of `MoveToDate()` and also can’t swipe the control using touch gesture beyond the min max date range. Also, beyond the min max date range, selection will also not works for `MonthView`. So that tapped listeners while tapped on the month cell will not be listened. Thus inline feature in month view will works only within the min max date range.

{% highlight c# %}

    int monthRange = 2;DateTime currentDate = DateTime.Now;
    
    //setting minimum display date
    
    DateTime minDate= new DateTime (currentDate.Year, currentDate.Month -     monthRange, currentDate.Day, 10, 0, 0);

    //setting maximum display date
    
    DateTime maxDate= new DateTime (currentDate.Year, currentDate.Month+     monthRange, currentDate.Day, 10, 0, 0);

    sfschedule.MinDisplayDate = minDate;
    sfschedule.MaxDisplayDate = maxDate;

    this.Content= sfschedule;

{% endhighlight %}

## Inline

By enabling `ShowAppointmentsInline` feature in `MonthView`, while touch the month view cell, appointments available in a particular day will be listed in inline View. 

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule
      x:Name="sfschedule" 
      ScheduleView="MonthView" 
      ShowAppointmentsInline="true" >
  </schedule:SfSchedule>
  
{% endhighlight %}

{% highlight c# %}

    SfSchedule sfschedule = new SfSchedule();
    sfschedule.ScheduleView = ScheduleView.MonthView
    sfschedule.ShowAppointmentsInline = true;
    this.Content= sfschedule;

{% endhighlight %}

{% endtabs %}

![](DateNavigationandGesture_images/Inline/Inline.png)

## FirstDay of the Week

By default schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by `FirstDayOfWeek` property of `SfSchedule`.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule FirstDayOfWeek="3"/>
    
{% endhighlight %}

{% highlight c# %}

    //setting first day of the week 
    sfschedule.FirstDayOfWeek = 3;

{% endhighlight %}

{% endtabs %}

> **NOTE**: Where 1-Sunday, 2-Monday, 3-Tuesday, 4-Wednesday, 5-Thursday, 6-Friday,7-Saturday.


![](DateNavigationandGesture_images/FirstDayOFWeek/FirstDayOfWeek.png)