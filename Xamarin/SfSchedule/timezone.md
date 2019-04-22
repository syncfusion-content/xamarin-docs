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
* Display appointments at the same time everywhere regardless of client’s time zone

We have added the following Time Zone's for the respective countries to cover all the time zone regions, you can use any of the time zone's from the following list for schedule time zone.
<table>
<th>Time Zone</th>
<th>Region</th>
</tr>
<tr>
<td>
AUS Central Standard Time
</td>
<td>
Australia/Darwin
</td>
</tr>
<tr>
<td>
AUS Eastern Standard Time
</td>
<td>
Australia/Sydney
</td>
</tr>
<tr>
<td>
Afghanistan Standard Time
</td>
<td>
Asia/Kabul
</td>
</tr>
<tr>
<td>
Alaskan Standard Time
</td>
<td>
America/Anchorage
</td>
</tr>
<tr>
<td>
Arab Standard Time
</td>
<td>
Asia/Riyadh
</td>
</tr>
<tr>
<td>
Arabian Standard Time
</td>
<td>
Etc/GMT-4
</td>
</tr>
<tr>
<td>
Arabic Standard Time
</td>
<td>
Asia/Baghdad
</td>
</tr>
<tr>
<td>
Argentina Standard Time
</td>
<td>
America/Buenos_Aires
</td>
</tr>
<tr>
<td>
Atlantic Standard Time
</td>
<td>
America/Halifax
</td>
</tr>
<tr>
<td>
Azerbaijan Standard Time
</td>
<td>
Asia/Baku
</td>
</tr>
<tr>
<td>
Azores Standard Time
</td>
<td>
Atlantic/Azores
</td>
</tr>
<tr>
<td>
Bahia Standard Time
</td>
<td>
America/Bahia
</td>
</tr>
<tr>
<td>
Bangladesh Standard Time
</td>
<td>
Asia/Dhaka
</td>
</tr>
<tr>
<td>
Belarus Standard Time
</td>
<td>
Europe/Minsk
</td>
</tr>
<tr>
<td>
Canada Central Standard Time
</td>
<td>
America/Regina
</td>
</tr>
<tr>
<td>
Cape Verde Standard Time
</td>
<td>
Atlantic/Cape_Verde
</td>
</tr>
<tr>
<td>
Caucasus Standard Time
</td>
<td>
Asia/Yerevan
</td>
</tr>
<tr>
<td>
Cen. Australia Standard Time
</td>
<td>
Australia/Adelaide
</td>
</tr>
<tr>
<td>
Central America Standard Time
</td>
<td>
America/Guatemala
</td>
</tr>
<tr>
<td>
Central Asia Standard Time
</td>
<td>
Asia/Almaty
</td>
</tr>
<tr>
<td>
Central Brazilian Standard Time
</td>
<td>
America/Cuiaba
</td>
</tr>
<tr>
<td>
Central Europe Standard Time
</td>
<td>
Europe/Budapest
</td>
</tr>
<tr>
<td>
Central European Standard Time
</td>
<td>
Europe/Warsaw
</td>
</tr>
<tr>
<td>
Central Pacific Standard Time
</td>
<td>
Pacific/Guadalcanal
</td>
</tr>
<tr>
<td>
Central Standard Time
</td>
<td>
America/Chicago
</td>
</tr>
<tr>
<td>
China Standard Time
</td>
<td>
Asia/Shanghai
</td>
</tr>
<tr>
<td>
Dateline Standard Time
</td>
<td>
Etc/GMT+12
</td>
</tr>
<tr>
<td>
E. Africa Standard Time
</td>
<td>
Africa/Nairobi
</td>
</tr>
<tr>
<td>
E. Australia Standard Time
</td>
<td>
Australia/Brisbane
</td>
</tr>
<tr>
<td>
E. South America Standard Time
</td>
<td>
America/Sao_Paulo
</td>
</tr>
<tr>
<td>
Eastern Standard Time
</td>
<td>
America/New_York
</td>
</tr>
<tr>
<td>
Egypt Standard Time
</td>
<td>
Africa/Cairo
</td>
</tr>
<tr>
<td>
Ekaterinburg Standard Time
</td>
<td>
Asia/Yekaterinburg
</td>
</tr>
<tr>
<td>
FLE Standard Time
</td>
<td>
Europe/Kiev
</td>
</tr>
<tr>
<td>
Fiji Standard Time
</td>
<td>
Pacific/Fiji
</td>
</tr>
<tr>
<td>
GMT Standard Time
</td>
<td>
Europe/London
</td>
</tr>
<tr>
<td>
GTB Standard Time
</td>
<td>
Europe/Bucharest
</td>
</tr>
<tr>
<td>
Georgian Standard Time
</td>
<td>
Asia/Tbilisi
</td>
</tr>
<tr>
<td>
Greenland Standard Time
</td>
<td>
America/Godthab
</td>
</tr>
<tr>
<td>
Greenwich Standard Time
</td>
<td>
Atlantic/Reykjavik
</td>
</tr>
<tr>
<td>
Hawaiian Standard Time
</td>
<td>
Pacific/Honolulu
</td>
</tr>
<tr>
<td>
India Standard Time
</td>
<td>
Asia/Calcutta
</td>
</tr>
<tr>
<td>
Iran Standard Time
</td>
<td>
Asia/Tehran
</td>
</tr>
<tr>
<td>
Israel Standard Time
</td>
<td>
Asia/Jerusalem
</td>
</tr>
<tr>
<td>
Jordan Standard Time
</td>
<td>
Asia/Amman
</td>
</tr>
<tr>
<td>
Kaliningrad Standard Time
</td>
<td>
Europe/Kaliningrad
</td>
</tr>
<tr>
<td>
Korea Standard Time
</td>
<td>
Asia/Seoul
</td>
</tr>
<tr>
<td>
Libya Standard Time
</td>
<td>
Africa/Tripoli
</td>
</tr>
<tr>
<td>
Line Islands Standard Time
</td>
<td>
Pacific/Kiritimati
</td>
</tr>
<tr>
<td>
Magadan Standard Time
</td>
<td>
Asia/Magadan
</td>
</tr>
<tr>
<td>
Mauritius Standard Time
</td>
<td>
Indian/Mauritius
</td>
</tr>
<tr>
<td>
Middle East Standard Time
</td>
<td>
Asia/Beirut
</td>
</tr>
<tr>
<td>
Montevideo Standard Time
</td>
<td>
America/Montevideo
</td>
</tr>
<tr>
<td>
Morocco Standard Time
</td>
<td>
Africa/Casablanca
</td>
</tr>
<tr>
<td>
Mountain Standard Time
</td>
<td>
America/Denver
</td>
</tr>
<tr>
<td>
Mountain Standard Time (Mexico)
</td>
<td>
America/Chihuahua
</td>
</tr>
<tr>
<td>
Myanmar Standard Time
</td>
<td>
Asia/Rangoon
</td>
</tr>
<tr>
<td>
N. Central Asia Standard Time
</td>
<td>
Asia/Novosibirsk
</td>
</tr>
<tr>
<td>
Namibia Standard Time
</td>
<td>
Africa/Windhoek
</td>
</tr>
<tr>
<td>
Nepal Standard Time
</td>
<td>
Asia/Kathmandu
</td>
</tr>
<tr>
<td>
New Zealand Standard Time
</td>
<td>
Pacific/Auckland
</td>
</tr>
<tr>
<td>
Newfoundland Standard Time
</td>
<td>
America/St_Johns
</td>
</tr>
<tr>
<td>
North Asia East Standard Time
</td>
<td>
Asia/Irkutsk
</td>
</tr>
<tr>
<td>
North Asia Standard Time
</td>
<td>
Asia/Krasnoyarsk
</td>
</tr>
<tr>
<td>
Pacific SA Standard Time
</td>
<td>
America/Santiago
</td>
</tr>
<tr>
<td>
Pacific Standard Time
</td>
<td>
America/Los_Angeles
</td>
</tr>
<tr>
<td>
Pacific Standard Time (Mexico)
</td>
<td>
America/Santa_Isabel
</td>
</tr>
<tr>
<td>
Pakistan Standard Time
</td>
<td>
Asia/Karachi
</td>
</tr>
<tr>
<td>
Paraguay Standard Time
</td>
<td>
America/Asuncion
</td>
</tr>
<tr>
<td>
Romance Standard Time
</td>
<td>
Europe/Paris
</td>
</tr>
<tr>
<td>
Russia Time Zone 10
</td>
<td>
Asia/Srednekolymsk
</td>
</tr>
<tr>
<td>
Russia Time Zone 11
</td>
<td>
Asia/Kamchatka
</td>
</tr>
<tr>
<td>
Russia Time Zone 3
</td>
<td>
Europe/Samara
</td>
</tr>
<tr>
<td>
Russian Standard Time
</td>
<td>
Europe/Moscow
</td>
</tr>
<tr>
<td>
SA Eastern Standard Time
</td>
<td>
America/Cayenne
</td>
</tr>
<tr>
<td>
SA Pacific Standard Time
</td>
<td>
America/Bogota
</td>
</tr>
<tr>
<td>
SA Western Standard Time
</td>
<td>
America/La_Paz
</td>
</tr>
<tr>
<td>
SE Asia Standard Time
</td>
<td>
Asia/Bangkok
</td>
</tr>
<tr>
<td>
Samoa Standard Time
</td>
<td>
Pacific/Apia
</td>
</tr>
<tr>
<td>
Singapore Standard Time
</td>
<td>
Asia/Singapore
</td>
</tr>
<tr>
<td>
South Africa Standard Time
</td>
<td>
Africa/Johannesburg
</td>
</tr>
<tr>
<td>
Sri Lanka Standard Time
</td>
<td>
Asia/Colombo
</td>
</tr>
<tr>
<td>
Syria Standard Time
</td>
<td>
Asia/Damascus
</td>
</tr>
<tr>
<td>
Taipei Standard Time
</td>
<td>
Asia/Taipei
</td>
</tr>
<tr>
<td>
Tasmania Standard Time
</td>
<td>
Australia/Hobart
</td>
</tr>
<tr>
<td>
Tokyo Standard Time
</td>
<td>
Asia/Tokyo
</td>
</tr>
<tr>
<td>
Tonga Standard Time
</td>
<td>
Pacific/Tongatapu
</td>
</tr>
<tr>
<td>
Turkey Standard Time
</td>
<td>
Europe/Istanbul
</td>
</tr>
<tr>
<td>
US Eastern Standard Time
</td>
<td>
America/Indianapolis
</td>
</tr>
<tr>
<td>
US Mountain Standard Time
</td>
<td>
America/Phoenix
</td>
</tr>
<tr>
<td>
UTC
</td>
<td>
America/Danmarkshavn
</td>
</tr>
<tr>
<td>
UTC+12
</td>
<td>
Pacific/Tarawa
</td>
</tr>
<tr>
<td>
UTC-02
</td>
<td>
America/Noronha
</td>
</tr>
<tr>
<td>
UTC-11
</td>
<td>
Pacific/Midway
</td>
</tr>
<tr>
<td>
Ulaanbaatar Standard Time
</td>
<td>
Asia/Ulaanbaatar
</td>
</tr>
<tr>
<td>
Venezuela Standard Time
</td>
<td>
America/Caracas
</td>
</tr>
<tr>
<td>
Vladivostok Standard Time
</td>
<td>
Asia/Vladivostok
</td>
</tr>
<tr>
<td>
W. Australia Standard Time
</td>
<td>
Australia/Perth
</td>
</tr>
<tr>
<td>
W. Central Africa Standard Time
</td>
<td>
Africa/Lagos
</td>
</tr>
<tr>
<td>
W. Europe Standard Time
</td>
<td>
Europe/Berlin
</td>
</tr>
<tr>
<td>
West Asia Standard Time
</td>
<td>
Asia/Tashkent
</td>
</tr>
<tr>
<td>
West Pacific Standard Time
</td>
<td>
Pacific/Port Moresby
</td>
</tr>
<tr>
<td>
Yakutsk Standard Time
</td>
<td>
Asia/Yakutsk
</td>
</tr>
</table>

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
