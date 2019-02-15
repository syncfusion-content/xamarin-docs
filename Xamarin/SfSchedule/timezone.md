---

layout: post
title: TimeZone support in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Use TimeZone in SfSchedule control
platform: xamarin
control: SfSchedule
documentation: ug

---

# Time Zone

Schedule allows you create appointments in various time zones and display them in users’ time zone or any other time zone. You can use a time zone in the following four different ways:
* Create appointments in different  time zones
* Display appointments based on the client’s  time zone
* Display appointments based on schedule  time zone
* Display appointments at the same time everywhere regardless of client’s time zone.

## Create appointments in different time zones
You can create appointments at different time zones using the [StartTimeZone](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~StartTimeZone.html) and [EndTimeZone](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~EndTimeZone.html) properties of [ScheduleAppointment](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment.html). An appointment’s start time and end time are calculated based on the given time zone information for the start time and end time. You can set different time zones to the StartTimeZone and EndTimeZone properties.

You can use the [StartTime](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~StartTime.html) and [EndTime](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~EndTime.html) properties of ScheduleAppointment to get the exact start time and end time of an appointment. By using the [ActualStartTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~ActualStartTime.html) and [ActualEndTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~ActualEndTime.html) properties, you can get exact appointment rendering time.

{% tabs %}	
{% highlight c# %}
appointment.StartTimeZone = "India Standard Time";
appointment.EndTimeZone = "India Standard Time";
		  
DateTime exactStartTime = appointment.StartTime;
DateTime exactEndTime = appointment.EndTime;
{% endhighlight %}
{% endtabs %}

>**NOTE**
* If the recurring appointment is converted to another time zone, then the whole sequence will be recalculated according to the new time zone information.
* If you create an all-day appointment, its start time and end time will be set to 12 A.M. and 12 A.M. by default, so time zone is not applicable for all-day appointments.
* Schedule supports daylight saving time.
* The time zone support is applicable for custom appointments too, so you need to map the corresponding property.
* You can use `TimeZone` for custom appointments by mapping the [StartTimeZoneMapping](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~StartTimeZoneMapping.html) and [EndTimeZoneMapping](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~EndTimeMapping.html) custom properties of [ScheduleAppointmentMapping](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping.html).


## Display Appointments based on client’s  time zone
You can display the appointments based on the client’s local time zone in schedule. For example, consider a scenario that you are in North Carolina and you want to set up a meeting at 10 A.M. on North Carolina time. You have colleagues in London and Chennai, and they also need to participate. The time for this meeting will be 3 P.M. (15:00) in London and 5.30 A.M. in Chennai. When you each view your calendar, you need to see the appointment displayed relative to your local time zones 5.30 A.M., 10 A.M., and 3 P.M., respectively. It can be achieved by setting schedule time zone to default (it will consider your device’s local time zone as schedule time zone) and appointment’s time zone to `Eastern Standard Time (North Carolina)` [as you are in North Carolina and its time zone is Eastern Standard Time].

## Display appointments based on schedule time zone
You can set specific time zone to schedule using the [TimeZone](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~TimeZone.html) property of schedule. On this scenario, the appointments will be displayed in UTC time when the `StartTimeZone` and `EndTimeZone` properties of `ScheduleAppointment` are set to null. The appointments will be displayed in UTC time based on the given schedule time zone.

{% tabs %}  
{% highlight xaml %}
<syncfusion:SfSchedule 
	x:Name="schedule"  
	TimeZone="GMT Standard Time">
</schedule:SfSchedule>
{% endhighlight %}   
{% highlight c# %}
schedule.TimeZone = "GMT Standard Time";
{% endhighlight %}  
{% endtabs %}   

## Display appointments at same time everywhere regardless of client’s  time zone
You can display appointments at the same time everywhere without considering the time zone when you set the `TimeZone` property of schedule, the `StartTimeZone`, and `EndTimeZone` properties of `ScheduleAppointment` to null. The appointments will be displayed based on the given `StartTime` and `EndTime` of appointment everywhere without considering the time zone.


## Updating StartTime and EndTime after drag and drop appointment based on Time Zone.
After rescheduling an appointment using `drag and drop`, appointment’s start and end time value will be updated based on schedule time zone and appointment’s time zone. 

For an example, consider, your local time zone is `India Standard Time`, if you drag an appointment from 9 AM and drop this on 1 PM and the schedule's `TimeZone` is not set and the appointment's `StartTimeZone` and `EndTimeZone` has set as `AUS Central Standard Time (Darwin)` then appointment's start time and end time value will be converted from Local time zone to appointment time zone and the appointment’s start time will be saved at 9 AM,

if you set schedule's `TimeZone` as `AUS Central Standard Time (Darwin)` and the appointment's `StartTimeZone` and `EndTimeZone` as `Central Standard Time (Mexico)` then the appointment's start time and end time value has converted from schedule's time zone to appointment time zone and the appointment's start time will be saved at 3.30 AM of next day, 
if you set schedule's `TimeZone` as `AUS Central Standard Time (Darwin)` and appointment's time zone was not set then the appointment's start time and end time value converted from schedule time zone to UTC time zone and the appointment's start time will be saved at 10.30 PM.
