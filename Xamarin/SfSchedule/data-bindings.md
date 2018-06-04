---

layout: post
title: Populating Appointments in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Populate Appointments in SfSchedule control
platform: xamarin
control: SfSchedule
documentation: ug

---


# Appointments

[SfSchedule](https://help.syncfusion.com/cr/xamarin/sfschedule) control has a built-in capability to handle the appointment arrangement internally based on the [ScheduleAppointmentCollection](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentCollection.html). [ScheduleAppointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment.html) is a class, which holds the details about the appointment to be rendered in schedule.

{% tabs %}
{% highlight c# %}
// Creating an instance for schedule appointment collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
//Adding schedule appointment in schedule appointment collection 
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{ 
	StartTime = new DateTime(2017, 05, 08, 10, 0, 0), 
	EndTime = new DateTime(2017, 05, 08, 12, 0, 0), 
	Subject = "Meeting", 
	Location = "Hutchison road", 
}); 

//Adding schedule appointment collection to DataSource of SfSchedule
schedule.DataSource=scheduleAppointmentCollection;
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/appointment.png)

## Minimum Appointment Height

[MinHeight](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~MinHeight.html) of an appointment is to set an arbitrary height to appointments when it has minimum duration, so that the subject can be readable.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.DayView;
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
    StartTime = new DateTime(2018, 2, 13, 09, 0, 0),
    EndTime = new DateTime(2018, 2, 13, 09, 0, 0),
    Subject = "Client Meeting",
    MinHeight = 30,
    Color = Color.FromHex("#FFD80073")
});
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
    StartTime = new DateTime(2018, 2, 13, 11, 0, 0),
    EndTime = new DateTime(2018, 2, 13, 12, 0, 0),
    Subject = "Anniversary",
    Color = Color.FromHex("#FFA2C139")
});
schedule.DataSource = scheduleAppointmentCollection;

this.Content = schedule;
{% endhighlight %}
{% endtabs %}

 ![](PopulatingAppointments_images/minheight.png)

>**NOTE**
* `MinHeight` value will be set, when the an appointment height (duration) value lesser than MinHeight. 
* Appointment height (duration) value will be set, when the appointment height (duration) value greater than `MinHeight`.
* TimeInterval value will be set, when Minimum Height greater than TimeInterval with lesser appointment height (duration).
* `MinHeight` has ScheduleAppointmentMapping Support.
* All day Appointment does not support `MinHeight`.

## Mapping
Schedule supports full data binding to any type of IEnumerable source. Specify the [ScheduleAppointmentMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping.html) attributes to map the properties in the underlying data source to the schedule appointments.

| Property Name | Description |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| [StartTimeMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~StartTimeMapping.html) | This property is to map the property name of custom class which is equivalent for StartTime of ScheduleAppointment. |
| [EndTimeMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~EndTimeMapping.html) | This property is to map the property name of custom class which is equivalent for EndTime of ScheduleAppointment. |
| [SubjectMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~SubjectMapping.html) | This property is to map the property name of custom class which is equivalent for Subject of ScheduleAppointment. |
| [ColorMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~ColorMapping.html) | This property is to map the property name of custom class which is equivalent for Color of ScheduleAppointment. |
| [IsAllDayMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~IsAllDayMapping.html) | This property is to map the property name of custom class which is equivalent for IsAllDay of ScheduleAppointment. |
| [RecurrenceRuleMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~RecurrenceRuleMapping.html) | This property is to map the property name of custom class which is equivalent for RecurrenceRule of ScheduleAppointment. |
| [NotesMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~NotesMapping.html) | This property is to map the property name of custom class which is equivalent for Notes of ScheduleAppointment. |
| [LocationMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~LocationMapping.html) | This property is to map the property name of custom class which is equivalent for Location of ScheduleAppointment. |
| [IsRecursiveMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~IsRecursiveMapping.html) | This property is to map the property name of custom class which is equivalent for IsRecursive of ScheduleAppointment. |
| [MinHeightMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointmentMapping~MinHeightMapping.html) | This property is to map the property name of custom class which is equivalent for MinHeight of ScheduleAppointment. |

N> CustomAppointment class should contain two DateTime fields and a string field as mandatory.

### Creating custom Appointments
You can create a custom class `Meeting` with mandatory fields `From`, `To` and `EventName`.

{% tabs %}
{% highlight c# %}
/// <summary>   
/// Represents custom data properties.   
/// </summary> 
public class Meeting
{
	public string EventName { get; set; }
	public DateTime From { get; set; }
	public DateTime To { get; set; }
	public Color Color { get; set; }
} 
{% endhighlight %}
{% endtabs %}

N> You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

You can map those properties of `Meeting` class with our SfSchedule control by using [AppointmentMapping](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~AppointmentMapping.html).
{% tabs %}
{% highlight xaml %} 
<syncfusion:SfSchedule x:Name="schedule" ScheduleView="DayView" DataSource="{Binding Meetings}">
	<syncfusion:SfSchedule.AppointmentMapping>
		<syncfusion:ScheduleAppointmentMapping
			SubjectMapping="EventName" 
			ColorMapping="Color"
			StartTimeMapping="From"
			EndTimeMapping="To">
		</syncfusion:ScheduleAppointmentMapping>
	</syncfusion:SfSchedule.AppointmentMapping>
</syncfusion:SfSchedule> 
{% endhighlight %}
{% highlight c# %}
//Schedule data mapping for custom appointments
ScheduleAppointmentMapping dataMapping = new ScheduleAppointmentMapping();
dataMapping.SubjectMapping = "EventName";
dataMapping.StartTimeMapping = "From";
dataMapping.EndTimeMapping = "To";
dataMapping.ColorMapping = "Color";
schedule.AppointmentMapping = dataMapping;
{% endhighlight %}
{% endtabs %} 

You can schedule meetings for a day by setting `From` and `To` of `Meeting` class. Create meetings of type `ObservableCollection <Meeting>` and assign those appointments collection `Meetings` to the `DataSource` property which is of `IEnumerable` type.

{% tabs %}
{% highlight c# %}
// Creating instance for custom appointment class
Meeting meeting = new Meeting();
// Setting start time of an event
meeting.From = new DateTime(2017,05,08, 10, 0, 0);
// Setting end time of an event
meeting.To = meeting.From.AddHours(1);
// Setting start time for an event
meeting.EventName = "Anniversary";
// Setting color for an event
meeting.Color = Color.Green; 
// Creating instance for collection of custom appointments
var Meetings = new ObservableCollection<Meeting>();
// Adding a custom appointment in CustomAppointmentCollection
Meetings.Add(meeting);
// Adding custom appointments in DataSource of SfSchedule
schedule.DataSource = Meetings;
{% endhighlight %} 
{% endtabs %}

## Spanned Appointments
Spanned Appointment is an appointment which lasts more than 24 hours.

{% tabs %}
{% highlight c# %}
public ObservableCollection<Meeting> Meetings { get; set; } 
// Creating instance for collection of custom appointments
Meetings = new ObservableCollection<Meeting>();
// Creating instance for custom appointment class
Meeting meeting = new Meeting();
// Setting start time of an event
meeting.From = new DateTime(2017,05,08, 10, 0, 0);
// Setting end time of an event
meeting.To = meeting.From.AddDays(2).AddHours(1);
// Setting start time for an event
meeting.EventName = "Anniversary";
// Setting color for an event
meeting.Color = Color.Green;
// Adding a custom appointment in CustomAppointmentCollection
Meetings.Add(meeting);

//Adding schedule appointment collection to DataSource of SfSchedule
schedule.DataSource= Meetings ; 
{% endhighlight %} 
{% endtabs %}

![](PopulatingAppointments_images/span.png)

## All Day Appointments
All-Day appointment is an appointment which is scheduled for a whole day. It can be set by using `IsAllDay` property in the `ScheduleAppointment`.

{% tabs %}
{% highlight c# %}
// Creating an instance for schedule appointment collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
//Adding schedule appointment in schedule appointment collection 
scheduleAppointmentCollection.Add(new ScheduleAppointment()
{
	StartTime = new DateTime(2017, 05, 08, 10, 0, 0),
	EndTime = new DateTime(2017, 05, 10, 12, 0, 0),
	Subject = "Meeting",
	Location = "Hutchison road",
	IsAllDay = true
}); 
//Adding schedule appointment collection to DataSource of SfSchedule
schedule.DataSource=scheduleAppointmentCollection;
{% endhighlight %} 
{% endtabs %}

### All-Day Appointment Panel
All-day appointment doesn't block out entire time slot in SfSchedule, rather it will render in separate layout exclusively for all-day appointment. It can be enabled by setting [ShowAllDay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~ShowAllDay.html) property of `DayViewSettings`, `WeekViewSettings` and `WorkWeekViewSettings` of `DayView`, `WeekView` and `WorkWeekView` respectively.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.WeekView;
WeekViewSettings weekViewSeetings = new WeekViewSettings();
weekViewSeetings.ShowAllDay = true;
schedule.WeekViewSettings = weekViewSeetings;
{% endhighlight %} 
{% endtabs %}

All-Day panel background can be customized by setting [AllDayAppointmentLayoutColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~AllDayAppointmentLayoutColor.html) of the respective view settings.

{% tabs %}
{% highlight c# %}
weekViewSeetings.AllDayAppointmentLayoutColor = Color.Silver; 
{% endhighlight %} 
{% endtabs %}

![](PopulatingAppointments_images/allday.png)

## Recurrence Appointment
Recurring appointment on a daily, weekly, monthly, or yearly interval. Recurring appointments can be created by enabling `IsRecursive` property in Schedule appointments.

### Recurrence Rule
The `RecurrenceRule` is a string value, that contains the details of the recurrence appointments like repeat type - daily/weekly/monthly/yearly, how many times it needs to be repeated, the interval duration and also the time period to render the appointment, etc.
[RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~RecurrenceRule.html) has the following properties and based on this property value, the recurrence appointments are rendered in the SfSchedule control with its respective time period.

| PropertyName | Purpose |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| FREQ | Maintains the Repeat type value of the appointment. (Example: Daily, Weekly, Monthly, Yearly, Every week day) Example: FREQ=DAILY;INTERVAL=1 |
| INTERVAL | Maintains the interval value of the appointments. For example, when you create the daily appointment at an interval of 2, the appointments are rendered on the days Monday, Wednesday and Friday. (creates the appointment on all days by leaving the interval of one day gap) Example: FREQ=DAILY;INTERVAL=1 |
| COUNT | It holds the appointment’s count value. For example, when the recurrence appointment count value is 10, it means 10 appointments are created in the recurrence series. Example: FREQ=DAILY;INTERVAL=1;COUNT=10 |
| UNTIL | This property is used to store the recurrence end date value. For example, when you set the end date of appointment as 6/30/2014, the UNTIL property holds the end date value when the recurrence actually ends. Example: FREQ=DAILY;INTERVAL=1;UNTIL=8/25/2014 |
| BYDAY | It holds the “DAY” values of an appointment to render.For example, when you create the weekly appointment, select the day(s) from the day options (Monday/Tuesday/Wednesday/Thursday/Friday/Saturday/Sunday).  When Monday is selected, the first two letters of the selected day “MO” is stored in the “BYDAY” property.  When you select multiple days, the values are separated by commas. Example: FREQ=WEEKLY;INTERVAL=1;BYDAY=MO,WE;COUNT=10 |
| BYMONTHDAY | This property is used to store the date value of the Month while creating the Month recurrence appointment. For example, when you create a Monthly recurrence appointment in the date 3, it means the BYMONTHDAY holds the value 3 and creates the appointment on 3rd day of every month. Example: FREQ=MONTHLY;BYMONTHDAY=3;INTERVAL=1;COUNT=10 |
| BYMONTH | This property is used to store the index value of the selected Month while creating the yearly appointments. For example, when you create the yearly appointment in the Month June, it means the index value for June month is 6 and it is stored in the BYMONTH field.  The appointment is created on every 6th month of a year. Example: FREQ=YEARLY;BYMONTHDAY=16;BYMONTH=6;INTERVAL=1;COUNT=10 |
| BYSETPOS | This property is used to store the index value of the week. For example, when you create the monthly appointment in second week of the month, the index value of the second week (2) is stored in BYSETPOS. Example: FREQ=MONTHLY;BYDAY=MO;BYSETPOS=2;UNTIL=8/11/2014 |

### Recurrence Pattern
Recurrence pattern used in the control are in iCal standard. Schedule control supports all four types of [recurrence patterns](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceType.html).

| RecurrenceType | RecurrenceProperties | Description |
|----------------|-------------------------|---------------------------------------------------------------|
| Daily | [DailyNDays](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~DailyNDays.html) | Gets or sets the event to recur on a daily N intervals basis. |
|  | [IsDailyEveryNDays](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsDailyEveryNDays.html) | Checks whether the event occurs Daily Every N days. |
| Weekly | [IsWeeklySunday ](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsWeeklySunday.html)| Checks whether the event occurs every Sunday of week |
|  | [IsWeeklyMonday](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsWeeklyMonday.html) | Checks whether the event occurs every Monday of week |
|  | [IsWeeklyTuesday](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsWeeklyTuesday.html) | Checks whether the event occurs every Tuesday of week |
|  | [IsWeeklyWednesday](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsWeeklyWednesday.html) | Checks whether the event occurs every Wednesday of week |
|  | [IsWeeklyThursday](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsWeeklyThursday.html) | Checks whether the event occurs every Thursday of week |
|  | [IsWeeklyFriday](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsWeeklyFriday.html) | Checks whether the event occurs every Friday of week |
|  | [IsWeeklySaturday](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsWeeklySaturday.html) | Checks whether the event occurs every Saturday of week |
|  | [NthWeek](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~NthWeek.html) | Gets or sets the event only nth week of the year. |
|  | [WeekDay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~WeekDay.html) | Gets or sets the event every week day. |
|  | [WeeklyEveryNWeeks](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~WeeklyEveryNWeeks.html) | Gets or sets the event every N Weeks. |
| Monthly | [SpecificMonth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~SpecificMonth.html) | Gets or sets the event in a specific month. |
|  | [SpecificMonthDay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~SpecificMonthDay.html) | Gets or sets the event in a specific month day. |
|  | [IsMonthlySpecific](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsMonthlySpecific.html) | Checks whether the event is Monthly specific event |
|  | [MonthlyEveryNMonths](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~MonthlyEveryNMonths.html) | Gets or sets the event every N Months. |
|  | [MonthlyNthWeek](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~MonthlyNthWeek.html) | Gets or sets the event nth week of every month. |
|  | [MonthlySpecificMonthDay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~MonthlySpecificMonthDay.html) | Gets or sets the event specific month day of Month. |
|  | [MonthlyWeekDay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~MonthlyWeekDay.html) | Gets or sets the event every week day of month. |
| Yearly | [IsYearlySpecific](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsYearlySpecific.html) | Checks whether the event is Yearly Specific. |
|  | [YearlyEveryNYears](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~YearlyEveryNYears.html) | Gets or sets the event occurs every N Years. |
|  | [YearlyGenericMonth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~YearlyGenericMonth.html) | Gets or sets the event occurs in generic month. |
|  | [YearlyNthWeek](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~YearlyNthWeek.html) | Gets or sets the event occurs yearly nth week. |
|  | [YearlySpecificMonth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~YearlySpecificMonth.html) | Gets or sets the event occurs yearly specific month. |
|  | [YearlySpecificMonthDay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~YearlySpecificMonthDay.html) | Gets or sets the event occurs yearly specific month day. |
|  | [YearlyWeekDay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~YearlyWeekDay.html) | Gets or sets the event occurs yearly week day. |
|  | [EveryNYears](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~EveryNYears.html) | Gets or sets the event every N Years. |
| Common | [IsRangeEndDate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsRangeEndDate.html) | Checks whether the event has Range end date |
|  | [IsRangeNoEndDate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsRangeNoEndDate.html) | Checks whether the event has No Range end date |
|  | [IsRangeRecurrenceCount](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsRangeRecurrenceCount.html) | Checks whether the event has recurrence count. |
|  | [RangeEndDate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~RangeEndDate.html) | Gets or sets the event range end date. |
|  | [RangeStartDate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~RangeStartDate.html) | Gets or sets the event range start date. |
|  | [RangeRecurrenceCount](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~RangeRecurrenceCount.html) | Gets or sets the event range recurrence count. |
|  | [IsSpecific](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceProperties~IsSpecific.html) | Checks whether the event occurs in Specific recurrence type. |

Find the following `RecurrenceRule` possibilities available in the Schedule control while creating the recurrence appointment.

| PossibilityType | Description | RecurrenceProperties | Examples |
|-----------------|----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Daily | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Daily, DailyNDays = 1, IsDailyEveryNDays = true, IsRangeNoEndDate = true | FREQ=DAILY; INTERVAL=1 |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Daily, DailyNDays = 1, IsDailyEveryNDays = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 15 | FREQ=DAILY; INTERVAL=1; COUNT=5 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Daily, DailyNDays = 1, IsDailyEveryNDays = true, IsRangeEndDate = true, RangeEndDate = new DateTime(2017, 06, 20) | FREQ=DAILY; INTERVAL=1; UNTIL=06/20/2017 |
|  | Appointment is created with Every (Interval) | RecurrenceType = RecurrenceType.Daily, DailyNDays = 2, IsDailyEveryNDays = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=DAILY; INTERVAL=2; COUNT=10 |
| Weekly | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyWednesday = true, IsWeeklyFriday = true, IsRangeNoEndDate = true | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO, WE, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyThursday = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=1; BYDAY=TH; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsRangeEndDate = true, RangeEndDate = new DateTime(2017, 07, 20) | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO; UNTIL=07/20/2017 |
|  | Appointment is created with selecting multiple day | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 2, IsWeeklyMonday = true, IsWeeklyWednesday = true, IsWeeklyFriday = true IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=WEEKLY; INTERVAL=2; BYDAY=MO, WE, FR; COUNT=10 |
| Every Day | Appointment is created with Ends Never | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyTuesday = true, IsWeeklyWednesday = true, IsWeeklyThursday = true, IsWeeklyFriday = true, IsRangeNoEndDate = true | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR |
|  | Appointment is created with Ends After | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyTuesday = true, IsWeeklyWednesday = true, IsWeeklyThursday = true, IsWeeklyFriday = true, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; COUNT=10 |
|  | Appointment is created with Ends On | RecurrenceType = RecurrenceType.Weekly, WeeklyEveryNWeeks = 1, IsWeeklyMonday = true, IsWeeklyTuesday = true, IsWeeklyWednesday = true, IsWeeklyThursday = true, IsWeeklyFriday = true, IsRangeEndDate = true, RangeEndDate = new DateTime(2017, 07, 15) | FREQ=WEEKLY; BYDAY=MO, TU, WE, TH, FR; UNTIL=07/15/2017 |
| Monthly | Appointment is created with selected date Ends Never | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, IsMonthlySpecific = true, MonthlySpecificMonthDay = 15, IsRangeNoEndDate = true | FREQ=MONTHLY; BYMONTHDAY=15; INTERVAL=1 |
|  | Appointment is created with selected date and Ends After | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, IsMonthlySpecific = true, MonthlySpecificMonthDay = 16, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=MONTHLY; BYMONTHDAY=16; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and Ends On | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, IsMonthlySpecific = true, MonthlySpecificMonthDay = 16, IsRangeEndDate = true, RangeEndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYMONTHDAY=17; INTERVAL=1; UNTIL=06/11/2018 |
|  | Appointment is created with selected day Ends Never | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, MonthlyNthWeek = 2, MonthlyWeekDay = 6, IsRangeNoEndDate = true | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=2; INTERVAL=1 |
|  | Appointment is created with selected day and Ends After | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, MonthlyNthWeek = 4, MonthlyWeekDay = 4, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=MONTHLY; BYDAY=WE; BYSETPOS=4; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected day and Ends On | RecurrenceType = RecurrenceType.Monthly, MonthlyEveryNMonths = 1, MonthlyNthWeek = 4, MonthlyWeekDay = 6, IsRangeEndDate = true, RangeEndDate = new DateTime(2018, 06, 11) | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=4; INTERVAL=1; UNTIL=06/11/2018 |
| Yearly | Appointment is created with selected date and month Ends Never | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, YearlyEveryNYears = 1, YearlySpecificMonth = 12, YearlySpecificMonthDay = 15, IsRangeNoEndDate = true | FREQ=YEARLY; BYMONTHDAY=15; BYMONTH=12; INTERVAL=1 |
|  | Appointment is created with selected date and month Ends After | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, YearlyEveryNYears = 1, YearlySpecificMonth = 12, YearlySpecificMonthDay = 10, IsRangeRecurrenceCount = true, RangeRecurrenceCount = 10 | FREQ=YEARLY; BYMONTHDAY=10; BYMONTH=12; INTERVAL=1; COUNT=10 |
|  | Appointment is created with selected date and month Ends On | RecurrenceType = RecurrenceType.Yearly, IsYearlySpecific = true, YearlyEveryNYears = 1, YearlySpecificMonth = 12, YearlySpecificMonthDay = 12, IsRangeEndDate = true, RangeEndDate = new DateTime(2018, 06, 11) | FREQ=YEARLY; BYMONTHDAY=12; BYMONTH=12; INTERVAL=1; UNTIL=06/11//2018 |

N> `SfSchedule` does not support Editing and Deleting of Recurring appointment's occurrences.

### Adding Recurrence Appointment using Recurrence Builder
Schedule appointment [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~RecurrenceRule.html) is used to populate the required recurring appointment collection in a specific pattern. `RRULE` can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

{% tabs %}
{% highlight c# %}
// Creating an instance for schedule appointment collection
ScheduleAppointmentCollection scheduleAppointmentCollection = new ScheduleAppointmentCollection();
//Adding schedule appointment in schedule appointment collection 
var scheduleAppointment = new ScheduleAppointment()
{
	StartTime = new DateTime(2017, 05, 08, 10, 0, 0),
	EndTime = new DateTime(2017, 05, 08, 12, 0, 0),
	Subject = "Occurs every alternate day",
	IsRecursive = true
};

//Adding schedule appointment in schedule appointment collection
scheduleAppointmentCollection.Add(scheduleAppointment);

//Adding schedule appointment collection to DataSource of SfSchedule
schedule.DataSource=scheduleAppointmentCollection; 

// Creating recurrence rule
RecurrenceProperties recurrenceProperties = new RecurrenceProperties();
recurrenceProperties.RecurrenceType = RecurrenceType.Daily;
recurrenceProperties.IsRangeRecurrenceCount = true;
recurrenceProperties.DailyNDays = 2;
recurrenceProperties.IsDailyEveryNDays = true;
recurrenceProperties.RangeRecurrenceCount = 10;
recurrenceProperties.RecurrenceRule = DependencyService.Get<IRecurrenceBuilder>().RRuleGenerator(recurrenceProperties, scheduleAppointment.StartTime, scheduleAppointment.EndTime);

// Setting recurrence rule to schedule appointment
scheduleAppointment.RecurrenceRule = recurrenceProperties.RecurrenceRule; 
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/recurrence.png)

### Creating Custom Recurrence Appointment using Recurrence Builder
For creating custom recurrence appointment you need to create a custom class `Meeting` with mandatory fields `From`, `To`, `EventName`, `IsRecursive` and `RecurrenceRule`.

{% tabs %}
{% highlight c# %}
/// <summary>
/// Represents custom data properties.
/// </summary>
public class Meeting
{
	public string EventName { get; set; }
	public DateTime From { get; set; }
	public DateTime To { get; set; }
	public Color Color { get; set; }
	public bool IsRecursive { get; set; }
	public string RecurrenceRule { get; set; }
}
{% endhighlight %}
{% endtabs %}

N> You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

You can map those properties of `Meeting` class with our SfSchedule control by using `ScheduleAppointmentMapping`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule x:Name="schedule" ScheduleView="DayView" DataSource="{Binding Meetings}">
	<syncfusion:SfSchedule.AppointmentMapping>
		<syncfusion:ScheduleAppointmentMapping
			SubjectMapping="EventName"
			ColorMapping="Color"
			StartTimeMapping="From"
			EndTimeMapping="To"
			IsRecursiveMapping="IsRecursive"
			RecurrenceRuleMapping="RecurrenceRule">
		</syncfusion:ScheduleAppointmentMapping>
	</syncfusion:SfSchedule.AppointmentMapping>
</syncfusion:SfSchedule>
{% endhighlight %}
{% highlight c# %}
// Schedule data mapping for custom appointments
ScheduleAppointmentMapping dataMapping = new ScheduleAppointmentMapping();
dataMapping.SubjectMapping = "EventName";
dataMapping.StartTimeMapping = "From";
dataMapping.EndTimeMapping = "To";
dataMapping.ColorMapping = "Color";
dataMapping.IsRecursiveMapping = "IsRecursive";
dataMapping.RecurrenceRuleMapping = "RecurrenceRule";
schedule.AppointmentMapping = dataMapping;
{% endhighlight %}
{% endtabs %}

You can schedule recurring meetings for daily, weekly, monthly, or yearly interval by setting `IsRecursive` and `RecurrenceRule` of `Meeting` class. Create meetings of type `ObservableCollection <Meeting>` and assign those appointments collection `Meetings` to the `DataSource` property which is of `IEnumerable` type.

{% tabs %}
{% highlight c# %}
// Creating instance for custom appointment class
Meeting meeting = new Meeting();
// Setting start time of an event
meeting.From = new DateTime(2017, 06, 11, 10, 0, 0);
// Setting end time of an event
meeting.To = meeting.From.AddHours(2);
// Setting start time for an event
meeting.EventName = "Client Meeting";
// Setting color for an event
meeting.Color = Color.Green;
// Setting whether the event is recurring
meeting.IsRecursive = true;

// Creating recurrence rule
RecurrenceProperties recurrenceProperties = new RecurrenceProperties();
recurrenceProperties.RecurrenceType = RecurrenceType.Weekly;
recurrenceProperties.WeeklyEveryNWeeks = 1;
recurrenceProperties.IsWeeklySunday = false;
recurrenceProperties.IsWeeklyMonday = true;
recurrenceProperties.IsWeeklyTuesday = false;
recurrenceProperties.IsWeeklyWednesday = true;
recurrenceProperties.IsWeeklyThursday = false;
recurrenceProperties.IsWeeklyFriday = true;
recurrenceProperties.IsWeeklySaturday = false;
recurrenceProperties.IsRangeRecurrenceCount = true;
recurrenceProperties.RangeRecurrenceCount = 10;
recurrenceProperties.RecurrenceRule = DependencyService.Get<IRecurrenceBuilder>().RRuleGenerator(recurrenceProperties, meeting.From, meeting.To);

// Setting recursive rule for an event
meeting.RecurrenceRule = recurrenceProperties.RecurrenceRule;

// Creating instance for collection of custom appointments
var Meetings = new ObservableCollection<Meeting>();
// Adding a custom appointment in CustomAppointmentCollection
Meetings.Add(meeting);

// Adding custom appointments in DataSource of SfSchedule
schedule.DataSource = Meetings;
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for Xamarin.Forms from
here [Recurrence_Appointment](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Recurrence_Appointment-1708142299.zip).

>**NOTE**
In Schedule "Xamarin.Forms UWP", there is no need to set IsRecursive property for recurrence appointments. When a RecurrenceRule is set to schedule appointment, value of IsRecursive property will be set as true automatically for these appointments. So even if IsRecursive is set as false, there will be no effect on recurring appointments.

![](PopulatingAppointments_images/RecurrenceAppointment.png)

## Appearance Customization
The default appearance of the appointment can be customized by using the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle.html) property and [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs.html). The event and property is used to customize or override the default template of the Appointments.

* [Customize appearance using Style](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-style) 
* [Customize appearance using Event](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-event) 
* [Customize appearance using Custom View](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-custom-view)
* [Customize appearance using DataTemplate](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-datatemplate)
* [Customize appearance using DataTemplateSelector](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-datatemplateselector)

### Customize appearance using Style
Schedule appointment can be customized by setting appointment style properties such as [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~TextColor.html), [FontFamily](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~FontFamily.html), [FontSize](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~FontSize.html), [FontAttributes](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~FontAttributes.html), [BorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~BorderColor.html), [BorderCornerRadius](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~BorderCornerRadius.html), [BorderWidth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~BorderWidth.html) to the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle.html) property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfSchedule x:Name="schedule" ScheduleView="DayView" DataSource="{Binding Meetings}">
    <syncfusion:SfSchedule.AppointmentStyle>
         <syncfusion:AppointmentStyle
                       BorderWidth="10"
                       TextColor="Red"
                       BorderCornerRadius="10"
                       FontSize = "25"
                       FontAttributes = "Bold"
                       FontFamily = "Arial"
                       BorderColor="Blue">
    </syncfusion:AppointmentStyle>
</syncfusion:SfSchedule.AppointmentStyle>
</syncfusion:SfSchedule>
{% endhighlight %}
{% highlight c# %}
//Creating Appointment style
AppointmentStyle appointmentStyle = new AppointmentStyle();
appointmentStyle.TextColor = Color.Red;
appointmentStyle.FontSize = 25;
appointmentStyle.FontAttributes = FontAttributes.Bold;
appointmentStyle.FontFamily = "Arial";
appointmentStyle.BorderColor = Color.Blue;
appointmentStyle.BorderCornerRadius = 12;
appointmentStyle.BorderWidth = 10;

//Setting Appointment Style
schedule.AppointmentStyle = appointmentStyle;
{% endhighlight %}
{% endtabs %} 

![](PopulatingAppointments_images/style.png)

### Customize appearance using Event
Schedule appointment can be customized during runtime using [OnAppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~OnAppointmentLoadedEvent_EV.html). `ScheduleAppointment` style can be customized using the `appointmentStyle` property.

[AppointmentLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs.html) has below properties,

•	[appointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~appointment.html) – Contains the appointments values.
•	[appointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~appointmentStyle.html) – Gets and sets the appointments style.
•	[view](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~view.html) -  Sets the Custom UI for Appointments.
•	[Bounds](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~Bounds.html) – Contains the UI bounds of appointment.

{% tabs %}
{% highlight c# %}
schedule.OnAppointmentLoadedEvent += Schedule_OnAppointmentLoadedEvent;

...

private void Schedule_OnAppointmentLoadedEvent(object sender, AppointmentLoadedEventArgs args)
{
	if (args.appointment != null && (args.appointment as Meeting) != null && (args.appointment as Meeting).IsAllDay)
	{
		args.appointmentStyle.BorderColor = Color.Red;
		args.appointmentStyle.TextColor  = Color.White
		args.appointmentStyle.BorderCornerRadius = 12;
		args.appointmentStyle.BorderWidth = 10;
	}
	else 
	{
		args.appointmentStyle.BorderColor = Color.Blue;
		args.appointmentStyle.TextColor = Color.Red;
		args.appointmentStyle.BorderCornerRadius = 12;
		args.appointmentStyle.BorderWidth = 10;
	}
}
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/appointmentstyle_event.png)

>**NOTE**
FontAttributes and FontFamily are native to the platform. Custom font and the font which are not available in the specified platform will not be applied.

## Customize appearance using Custom View
Default appointment UI can be changed using `view` property passed through `AppointmentLoadedEventArgs`.


{% tabs %}
{% highlight c# %} 
schedule.OnAppointmentLoadedEvent += Schedule_OnAppointmentLoadedEvent;

private void Schedule_OnAppointmentLoadedEvent(object sender, AppointmentLoadedEventArgs args)
{
	if(args.appointment == null  || (args.appointment as Meeting) == null)
		return;
	if ((args.appointment as Meeting).IsAllDay)
	{
		Label label = new Label();
		label.BackgroundColor = (args.appointment as Meeting).Color;
		label.Text = (args.appointment as Meeting).EventName;
		args.view = label;
	}
	else if ((args.appointment as Meeting).EventName == "Retrospective" )
	{
		Button button = new Button();
		button.Image = "Meeting.png";
		button.BackgroundColor = (args.appointment as Meeting).EventName;
		args.view = button;
	}
	else 
	{
		Button button = new Button();
		button.Image = "Cake.png";
		button.BackgroundColor = (args.appointment as Meeting).EventName;
		args.view = button;
	}
}
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/appointmentstyle_customview.png)

## Drag and Drop Appointments
Appointments can be rescheduled using the drag and drop operation. To perform drag-and-drop operations within the schedule, enable the [AllowAppointmentDrag](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AllowAppointmentDrag.html) property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name=“schedule”
ScheduleView="WeekView"
AllowAppointmentDrag="true">
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.AllowAppointmentDrag = true;
{% endhighlight %}
{% endtabs %}

By long-pressing the appointment you can hold and start dragging to next time slots and it can be handled by below ways.

* [Handle dragging based on the appointment](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#handle-dragging-based-on-the-appointment)
* [Get the dragging appointment position](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#get-the-dragging-appointment-position)
* [Handle Appointment Dropping](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#handle-dppointment-dropping)

### Handle dragging based on the appointment
Using [AppointmentDragStarting](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~AppointmentDragStarting_EV.html) event you can get the appointment details and can handle whether the appointment can drag or not. This event will trigger when the appointment is started  dragging. The [AppointmentDragStartingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDragStartingEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDragStartingEventArgs~Appointment.html) - Gets the dragged appointment details.
[Cancel](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDragStartingEventArgs~Cancel.html)- Appointment dragging can be handled (enable/disable) using this boolean property.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragStarting += Schedule_AppointmentDragStarting;

...

private void Schedule_AppointmentDragStarting(object sender, AppointmentDragStartingEventArgs e)
{
var appointment = e.Appointment;
e.Cancel = false;
}
{% endhighlight %}
{% endtabs %}

### Get the dragging appointment position
Using [AppointmentDragOver](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~AppointmentDragOver_EV.html) event you can get the dragging appointment details, position, time of the particular location. The event will continuously triggered when the appointment is being dragged. The [AppointmentDragEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs~Appointment.html) - Gets the dragging appointment details.
[DraggingPoint](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs~DraggingPoint.html)- Gets the dragging point (X, Y) of the appointment in Schedule.
[DraggingTime](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs~DraggingTime.html)- Gets the dragging time of the appointment in Schedule

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragOver += Schedule_AppointmentDragOver;

...

private void Schedule_AppointmentDragOver(object sender, AppointmentDragEventArgs e)
{
var appointment = e.Appointment;
var draggingPoint = e.DraggingPoint;
var draggingTime = e.DraggingTime;
}
{% endhighlight %}
{% endtabs %}

### Handle Appointment Dropping
Using [AppointmentDrop](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~AppointmentDrop_EV.html) event you can get the dropped appointment details, position, time and you can handle whether the appointment can be dropped to the specific position or not. This event will trigger after dropping the appointment. The [AppointmentDropEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs~Appointment.html) - Gets the dropped appointment details.
[Cancel](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs~Cancel.html)- Appointment dropping can be handled (enable / disable) using this Boolean property.
[DropTime](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs~DropTime.html)- Gets the dropped time of the appointment in Schedule

{% tabs %}
{% highlight c# %}
schedule.AppointmentDrop += Schedule_AppointmentDrop;

...

private void Schedule_AppointmentDrop(object sender, AppointmentDropEventArgs e)
{
var appointment = e.Appointment;
e.Cancel = false;
var dropTime = e.DropTime;
}
{% endhighlight %}
{% endtabs %}

### Drag and Drop Settings
Using [DragDropSettings](http://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~DragDropSettings.html) property of schedule can handle the behavior of drag and drop in Schedule. The `DragDropSettings` contains the following properties,

[AllowNavigate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DragDropSettings~AllowNavigate.html) - Using this boolean property can handle the Appointment dragging, whether navigate to next/previous view or not while dragging the appointment to the endpoint of the current view in Schedule.
[AutoNavigationDelay](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DragDropSettings~AutoNavigationDelay.html) - Using this `TimeSpan` property can handle the navigation time to switch to next/previous view when navigating to next/previous view while holding the dragged appointment.
[AllowScroll](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DragDropSettings~AllowScroll.html) - Using this boolean property can handle the Appointment dragging, whether scroll (below/above) the Schedule or not while dragging the appointment to the endpoint of the current view in Schedule.
[ShowTimeIndicator](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DragDropSettings~ShowTimeIndicator.html) - Using this boolean property can handle the time indicator whether it should visible or not, which shows the dragged appointment current position time in time text slots.
[TimeIndicatorStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DragDropSettings~TimeIndicatorStyle.html) - Using this property can handle the time indicator style which contains [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.TimeIndicatorStyle~TextColor.html), [TextSize](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.TimeIndicatorStyle~TextSize.html) and [TextFormat](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.TimeIndicatorStyle~TextFormat.html).

{% tabs %}
{% highlight c# %}
DragDropSettings dragDropSettings = new DragDropSettings();
dragDropSettings.AllowNavigate = true;
dragDropSettings.AllowScroll = false;
var timeSpan = new TimeSpan(0, 0, 0, 1, 0);
dragDropSettings.AutoNavigationDelay = timeSpan;
dragDropSettings.ShowTimeIndicator = true;
dragDropSettings.TimeIndicatorStyle = timeIndicatorStyle;
schedule.DragDropSettings = dragDropSettings;
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
TimeIndicatorStyle timeIndicatorStyle = new TimeIndicatorStyle();
timeIndicatorStyle.TextColor = Color.Blue;
timeIndicatorStyle.TextSize = 13;
timeIndicatorStyle.TextFormat = "hh : mm";
{% endhighlight %}
{% endtabs %}

>**Notes**
* While dropping appointment to `AllDay` panel from time slots, appointment start and end time will change to 12.00 AM.
* While dropping appointment to time slots from `AllDay` panel, appointment duration will change as one (1) hour from the dropped time.
* Doesn't support control to control drag and drop.

## Customize appearance using DataTemplate
The default appearance of the Appointment can be customized by using the [AppointmentTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~AppointmentTemplate.html) property of the Schedule.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule
        x:Name="schedule"
        AppointmentTemplate="{Binding AppointmentTemplate}">
        <schedule:SfSchedule.BindingContext>
            <samplelocal:DayAppointmentDataTemplate />
        </schedule:SfSchedule.BindingContext>
</schedule:SfSchedule>
{% endhighlight %}
{% endtabs %}

### Creating a DataTemplate

{% tabs %}
{% highlight c# %}
public class DayAppointmentDataTemplate : DataTemplate
{
    public DataTemplate AppointmentTemplate { get; set; }

    public DayAppointmentDataTemplate()
    {
        AppointmentTemplate = new DataTemplate(() =>
        {
            return new Button
            {
                Text = "Template",
                TextColor = Color.White,
                BackgroundColor = Color.LightGreen
            };
        });
    }
}
{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/dayappointmenttemplate.png)

## Customize appearance using DataTemplateSelector
`DataTemplateSelector` can be used to choose a `DataTemplate` at runtime based on the value of a data-bound to Schedule appointment property through `AppointmentTemplate`. It provides multiple DataTemplates to be enabled for Schedule appointments, to customize the appearance of particular Appointment.

{% tabs %}
{% highlight xaml %}
<ContentPage.Resources>
    <ResourceDictionary>
        <samplelocal:AppointmentDataTemplateSelector x:Key="appointmentDataTemplateSelector" />
    </ResourceDictionary>
</ContentPage.Resources>

<ContentPage.Content>
    <schedule:SfSchedule
            AppointmentTemplate="{StaticResource appointmentDataTemplateSelector}">
            <schedule:SfSchedule.BindingContext>
                <samplelocal:AppointmentDataTemplateSelector />
            </schedule:SfSchedule.BindingContext>
    </schedule:SfSchedule>
</ContentPage.Content>

{% endhighlight %}
{% endtabs %}

### Creating a DataTemplateSelector

{% tabs %}
{% highlight c# %}

public class AppointmentDataTemplateSelector : DataTemplateSelector
{
    public DataTemplate DayAppointmentTemplate { get; set; }
    public DataTemplate AllDayAppointmentTemplate { get; set; }

    public AppointmentDataTemplateSelector()
    {
        DayAppointmentTemplate = new DataTemplate(typeof(DayAppointmentTemplate));
        AllDayAppointmentTemplate = new DataTemplate(typeof(AllDayAppointmentTemplate));
    }

    protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
    {
        if ((item as ScheduleAppointment).IsAllDay)
            return AllDayAppointmentTemplate;
        else
            return DayAppointmentTemplate;
    }
}

{% endhighlight %}
{% endtabs %}

Used button to display day appointment and Label to display all day appointment.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="UTF-8"?>
<!--<Button as Template for day Appointment>-->
<Button xmlns="http://xamarin.com/schemas/2014/forms"
        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
        x:Class="ScheduleUG.DayAppointmentTemplate"
        BackgroundColor="{Binding Color}"
        HorizontalOptions="FillAndExpand"
        VerticalOptions="FillAndExpand"
        Text="{Binding Subject}"
        TextColor="White"
        Image="{Binding Subject}">
</Button>

    .......

<?xml version="1.0" encoding="UTF-8"?>
<!--<Label as Template for all day Appointment>-->
<Label xmlns="http://xamarin.com/schemas/2014/forms"
        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
        x:Class="ScheduleUG.AllDayAppointmentTemplate"
        BackgroundColor="{Binding Color}"
        Text="{Binding Subject}"
        HorizontalOptions="FillAndExpand"
        VerticalOptions="CenterAndExpand"
        TextColor="White" FontSize="15"
        HorizontalTextAlignment="Center"
        VerticalTextAlignment="Center">
</Label>

{% endhighlight %}
{% endtabs %}

![](PopulatingAppointments_images/appointmenttemplate.png)

### Customize Font Appearance

you can change the appearance of Font by setting the  [FontFamily](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~FontFamily.html) property of [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle.html) property in Schedule.

{% tabs %}
{% highlight xaml %}
<schedule:AppointmentStyle.FontFamily>
	 <OnPlatform x:TypeArguments="x:String" iOS="Lobster-Regular" Android="Lobster-Regular.ttf" WinPhone="Assets/Lobster-Regular.ttf#Lobster" />
</schedule:AppointmentStyle.FontFamily>
{% endhighlight %}
{% highlight c# %}
appointmentStyle.FontFamily = Device.OnPlatform("Lobster-Regular", "Lobster-Regular.ttf", "Assets/Lobster-Regular.ttf#Lobster");
{% endhighlight %}
{% endtabs %} 

![](PopulatingAppointments_images/customfontappointment.png)

Refer [this](https://help.syncfusion.com/xamarin/sfschedule/monthview#custom-font-setting-in-xamarinforms-android) to configure the custom fonts in Xamarin.Forms.

## Selection
Schedule control has built-in events to handle tapped, double tapped and long pressed touch actions.

•	[CellTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~CellTapped_EV.html)
•	[CellDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~CellDoubleTapped_EV.html)
•	[CellLongPressed](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~CellLongPressed_EV.html)

These events will be triggered while perform respective touch actions in timeslots, month cells and in appointments. All the three events contain the same argument [CellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.CellTappedEventArgs.html) which holds selected appointment and date time details in it.

• [Appointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.CellTappedEventArgs~Appointment.html) - Contains the selected appointment value when tapped on the appointment. It will be null when tapped on the timeslot. Selected occurrence of a recurring appointment's value will be same as the master appointment, except the date values. So selected occurrence's date can be obtained from the args.DateTime value.
• [Appointments](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.CellTappedEventArgs~Appointments.html) - Contains appointments value of Tapped month cell.
• [DateTime](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.CellTappedEventArgs~Datetime.html) - Contains selected time slot DateTime value.

>N Occurrences can be handled from tapped event when single occurrence remains unmodified.

{% tabs %}
{% highlight c# %}
schedule.CellTapped += Schedule_CellTapped;
schedule.CellDoubleTapped += Schedule_CellDoubleTapped;
schedule.CellLongPressed += Schedule_CellLongPressed;

...

private void Schedule_CellTapped(object sender, CellTappedEventArgs e)
{
}
private void Schedule_CellDoubleTapped(object sender, CellTappedEventArgs e)
{
}
private void Schedule_CellLongPressed(object sender, CellTappedEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

### Commands
Schedule commands allow data bindings to make method calls directly to a ViewModel, which supports tapped, double tapped, long pressed touch actions and visible date changed action.

•    [CellTappedCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~CellTappedCommand.html)
•    [CellDoubleTappedCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~CellDoubleTappedCommand.html)
•    [CellLongPressedCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~CellLongPressedCommand.html)
•    [VisibleDatesChangedCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~VisibleDatesChangedCommand.html)

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule
	CellTappedCommand="{Binding ScheduleCellTapped}"
	CellDoubleTappedCommand="{Binding ScheduleCellDoubleTapped}"
	CellLongPressedCommand="{Binding ScheduleCellLongPressed}"
	VisibleDatesChangedCommand="{Binding ScheduleVisibleDatesChanged}">
	<schedule:SfSchedule.BindingContext>
		<samplelocal:ScheduleViewModel />
	</schedule:SfSchedule.BindingContext>
</schedule:SfSchedule>

{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
public class ScheduleViewModel
{
	public ICommand ScheduleCellTapped { get; set; }
	public ICommand ScheduleCellDoubleTapped { get; set; }
	public ICommand ScheduleCellLongPressed { get; set; }
	public ICommand ScheduleVisibleDatesChanged { get; set; }

	public ScheduleViewModel()
	{
		ScheduleCellTapped = new Command<CellTappedEventArgs>(CellTapped);
		ScheduleCellDoubleTapped = new Command<CellTappedEventArgs>(DoubleTapped);
		ScheduleCellLongPressed = new Command<CellTappedEventArgs>(LongPressed);
		ScheduleVisibleDatesChanged = new Command<VisibleDatesChangedEventArgs>(VisibleDatesChanged);
	}

	private void CellTapped(CellTappedEventArgs args)
	{
		var selectedDateTime = args.Datetime;
	}

	private void DoubleTapped(CellTappedEventArgs args)
	{
		var selectedDateTime = args.Datetime;
	}

	private void LongPressed(CellTappedEventArgs args)
	{
		var selectedDateTime = args.Datetime;
	}

	private void VisibleDatesChanged(VisibleDatesChangedEventArgs args)
	{
		var visibleDates = args.visibleDates;
	}
}

{% endhighlight %}
{% endtabs %}

### Selection customization
The default selection of an appointment can be customized by using [SelectionBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~SelectionBorderColor.html), [SelectionTextColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~SelectionTextColor.html) properties in `AppointmentStyle` property of `SfSchedule`. The property is used to customize or override the default selection of the appointments.

N> `BorderWidth` value must be set to highlight `SelectionBorderColor`.

{% tabs %}
{% highlight xaml %} 
<syncfusion:SfSchedule x:Name="schedule" ScheduleView="DayView" DataSource="{Binding Meetings}">
	<syncfusion:SfSchedule.AppointmentStyle>
		<syncfusion:AppointmentStyle 
			SelectionTextColor="Yellow" 
			SelectionBorderColor="Yellow">
		</syncfusion:AppointmentStyle>
	</syncfusion:SfSchedule.AppointmentStyle>    
</syncfusion:SfSchedule> 
{% endhighlight %}
{% highlight c# %}
//Creating an appointment style
AppointmentStyle appointmentStyle = new AppointmentStyle();
appointmentStyle.SelectionBorderColor = Color.Yellow;
appointmentStyle.SelectionTextColor = Color.Yellow;

//Setting an appointment style
schedule.AppointmentStyle = appointmentStyle;
{% endhighlight %}
{% endtabs %} 

![](PopulatingAppointments_images/selection.png)
