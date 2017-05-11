---
title: Localization in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Localize the SfSchedule control
platform: xamarin
control: SfSchedule
documentation: ug
---

# Localization 

Schedule control is available with complete localization support. Localization can be specified by setting the `Locale` property of the control. In the format of `Language code`.

## Locale

Based on the locale specified the strings in the control such as Date, time, days are localized accordingly.

By default schedule control is available with **en**-**US** locale. 

As the subject of the appointments are given in the application level, it can be set as localized strings as per the requirement. To know more about settings the subject refer [Schedule Appointments](/xamarin/sfschedule/data-bindings "Schedule Appointments").

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule
    x:Name="schedule" 
    ScheduleView="WeekView"
    Locale="fr">
    </schedule:SfSchedule>
	
{% endhighlight %}

{% highlight c# %}

    //creating new instance for schedule
    SfSchedule schedule = new SfSchedule();
    //setting schedule view 
    schedule.ScheduleView=(ScheduleView.WeekView);
    //setting locale for the control 
    schedule.Locale= "fr";
    this.Content= schedule;

{% endhighlight %}

{% endtabs %}

>**NOTE** AM/PM in the timeline will not be localized in the Schedule views.

![](Localization_images/Localization.png)
