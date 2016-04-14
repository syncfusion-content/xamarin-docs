---

layout: post
title: Localization in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Localize the SfSchedule control
platform: Xamarin.Forms
control: SfSchedule
documentation: ug

---


# LOCALIZATION 

Schedule control is available with complete localization support. Localization can be specified by setting the `Locale` property of the control. In the format of `Language code` followed by `Country code`.  Based on the locale specified the strings in the control such as Date, time, days are localized accordingly.

By default schedule control is available with **en**-**US** locale. 

As the subject of the appointments are given in the application level, it can be set as localized strings as per the requirement. To know more about settings the subject refer [Schedule Appointments](/xamarin/sfschedule/populating-appointment "Schedule Appointments").

{% highlight c# %}
    
    //creating new instance for schedule
    SfSchedule sfschedule = new SfSchedule();
    //setting schedule view 
    sfschedule.ScheduleView=(ScheduleView.WeekView);
    //setting locale for the control 
    sfschedule.Locale=("fr","FR");
    this.Content= sfschedule;
    
{% endhighlight %}

![](Localization_images/Locale.png)