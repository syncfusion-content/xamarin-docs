---

layout: post
title: TimeZone support in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Use TimeZone in SfSchedule control
platform: xamarin
control: SfSchedule
documentation: ug

---

## TimeZone

Schedule allows you to create appointments in various time zones and display them in the user's time zone or any other time zone. Appointments are rendered by recalculating Start and End time based on given time zone.

Consider the following scenario you are in North Carolina and you want to set up a meeting at 10 AM on North Carolina time. You have colleagues in London and Chennai and they also need to participate. The time for this meeting will be 3 PM (15:00) in London and 5.30 AM in Chennai. When you each view your calendar, you need to see the appointment displayed relative to your local time zone 5.30 am, 10 am, 3 pm respectively and it can be achieved by setting schedule time zone to default and Appointments time zone to `Eastern Standard Time (North Carolina)` [as you are in North Carolina and its time zone is Eastern Standard Time)

You can set specific time zone to schedule by using [TimeZone](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.TimeZone.html) Property of schedule. 
{% tabs %}
{% highlight XAML %}
<syncfusion:SfSchedule x:Name="schedule"  TimeZone="GMT Standard Time"></schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.TimeZone = "GMT Standard Time";
{% endhighlight %}
{% endtabs %}

### Creating Appointment's in different TimeZone
You can create appointments at different time zone using [StartTimeZone](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~StartTimeZone.html) and [EndTimeZone](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~EndTimeZone.html) property of the `Appointment`. The appointment's start time and end time calculated based on the given time zone information for start time and end time. You can set different time zones for `StartTimeZone` and `EndTimeZone` property.
You can use `StartTime` and `EndTime` property to get the exact Start Time and End Time of the appointment. By using [ActualStartTime](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~ActualStartTime.html) and [ActualEndTime](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~ActualEndTime.html) properties, you can get the exact appointment rendering time.

{% tabs %}	
{% highlight c# %}
appointment.StartTimeZone = "India Standard Time";
appointment.EndTimeZone = "India Standard Time";
		  
DateTime exactStartTime = appointment.StartTime;
DateTime exactEndTime = appointment.EndTime;
{% endhighlight %}
{% endtabs %}

>**NOTE**
* If the recurring appointment is converted to another time zone then the whole sequence will be recalculated according to the new time zone information.
If you create all day appointment, then it's start time and end times are set default as 12 am to 12 am so time zone is not applicable for all day appointments.

### Updating StartTime and EndTime after drag and drop appointment based on Time Zone.
After rescheduling an appointment using `drag and drop`, appointment’s start and end time value will be updated based on schedule time zone and appointment’s time zone. 

For an example, consider, your local time zone is `India Standard Time`, if you drag an appointment from 9 AM and drop this on 1 PM and the schedule's `TimeZone` is not set and the appointment's `StartTimeZone` and `EndTimeZone` has set as `AUS Central Standard Time (Darwin)` then appointment's start time and end time value will be converted from Local time zone to appointment time zone and the appointment’s start time will be saved at 9 AM,

if you set schedule's `TimeZone` as `AUS Central Standard Time (Darwin)` and the appointment's `StartTimeZone` and `EndTimeZone` as `Central Standard Time (Mexico)` then the appointment's start time and end time value has converted from schedule's time zone to appointment time zone and the appointment's start time will be saved at 3.30 AM of next day, 
if you set schedule's `TimeZone` as `AUS Central Standard Time (Darwin)` and appointment's time zone was not set then the appointment's start time and end time value converted from schedule time zone to UTC time zone and the appointment's start time will be saved at 9.30 PM.
