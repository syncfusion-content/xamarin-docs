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

![](PopulatingAppointments_images/appointment.png)

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

N> CustomAppointment class should contain two DateTime fields and a string field as mandatory.

### Creating custom Appointments
You can create a custom class `Meeting` with mandatory fields `From`, `To` and `EventName`.
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

N> You can inherit this class from `INotifyPropertyChanged` for dynamic changes in custom data.

You can map those properties of `Meeting` class with our SfSchedule control by using `ScheduleAppointmentMapping`.
{% tabs %}
{% highlight c# %}

        //Schedule data mapping for custom appointments
        ScheduleAppointmentMapping dataMapping = new ScheduleAppointmentMapping();
        dataMapping.SubjectMapping = "EventName";
        dataMapping.StartTimeMapping = "From";
        dataMapping.EndTimeMapping = "To";
        dataMapping.ColorMapping = "Color";
        schedule.AppointmentMapping = dataMapping;

{% endhighlight %}
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
{% endtabs %} 

You can schedule meetings for a day by setting `From` and `To` of `Meeting` class. Create meetings of type `ObservableCollection <Meeting>` and assign those appointments collection `Meetings` to the `DataSource` property which is of `IEnumerable` type.

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

## Spanned Appointments
Spanned Appointment is an appointment which lasts more than 24 hours.

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

![](PopulatingAppointments_images/span.png)

## All Day Appointments
All-Day appointment is an appointment which is scheduled for a whole day. It can be set by using `IsAllDay` property in the `ScheduleAppointment`.

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

### All-Day Appointment Panel
All-day appointment doesn't block out entire time slot in SfSchedule, rather it will render in separate layout exclusively for all-day appointment. It can be enabled by setting `ShowAllDay` property of `DayViewSettings`, `WeekViewSettings` and `WorkWeekViewSettings` of `DayView`, `WeekView` and `WorkWeekView` respectively.

{% highlight c# %}

            schedule.ScheduleView = ScheduleView.WeekView;
        WeekViewSettings weekViewSeetings = new WeekViewSettings();
        weekViewSeetings.ShowAllDay = true;
        schedule.WeekViewSettings = weekViewSeetings;

{% endhighlight %} 

All-Day panel background can be customized by setting `AllDayAppointmentLayoutColor` 
of the respective view settings.

{% highlight c# %}

            weekViewSeetings.AllDayAppointmentLayoutColor = Color.Silver; 

{% endhighlight %} 

![](PopulatingAppointments_images/allday.png)

## Recurrence Appointment
Recurring an appointment on a daily, weekly, monthly, or yearly interval. Recursive appointments can be created by enabling `IsRecursive` property in Schedule appointments. 

### Recurrence Pattern
Recurrence pattern used in the control are in iCal standard. Schedule control supports all four types of [recurrence patterns](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.RecurrenceType.html).

| RecurrenceType | RecurrenceProperties | Description |
|----------------|-------------------------|---------------------------------------------------------------|
| Daily | DailyNDays | Gets or sets the event to recur on a daily N intervals basis. |
|  | IsDailyEveryNDays | Checks whether the event occurs Daily Every N days. |
| Weekly | IsWeeklySunday | Checks whether the event occurs every Sunday of week |
|  | IsWeeklyMonday | Checks whether the event occurs every Monday of week |
|  | IsWeeklyTuesday | Checks whether the event occurs every Tuesday of week |
|  | IsWeeklyWednesday | Checks whether the event occurs every Wednesday of week |
|  | IsWeeklyThursday | Checks whether the event occurs every Thursday of week |
|  | IIsWeeklyFriday | Checks whether the event occurs every Friday of week |
|  | IsWeeklySaturday | Checks whether the event occurs every Saturday of week |
|  | NthWeek | Gets or sets the event only nth week of the year. |
|  | WeekDay | Gets or sets the event every week day. |
|  | WeeklyEveryNWeeks | Gets or sets the event every N Weeks. |
| Monthly | SpecificMonth | Gets or sets the event in a specific month. |
|  | SpecificMonthDay | Gets or sets the event in a specific month day. |
|  | IsMonthlySpecific | Checks whether the event is Monthly specific event |
|  | MonthlyEveryNMonths | Gets or sets the event every N Months. |
|  | MonthlyNthWeek | Gets or sets the event nth week of every month. |
|  | MonthlySpecificMonthDay | Gets or sets the event specific month day of Month. |
|  | MonthlyWeekDay | Gets or sets the event every week day of month. |
| Yearly | IsYearlySpecific | Checks whether the event is Yearly Specific. |
|  | YearlyEveryNYears | Gets or sets the event occurs every N Years. |
|  | YearlyGenericMonth | Gets or sets the event occurs in generic month. |
|  | YearlyNthWeek | Gets or sets the event occurs yearly nth week. |
|  | YearlySpecificMonth | Gets or sets the event occurs yearly specific month. |
|  | YearlySpecificMonthDay | Gets or sets the event occurs yearly specific month day. |
|  | YearlyWeekDay | Gets or sets the event occurs yearly week day. |
|  | EveryNYears | Gets or sets the event every N Years. |
| Common | IsRangeEndDate | Checks whether the event has Range end date |
|  | IsRangeNoEndDate | Checks whether the event has No Range end date |
|  | IsRangeRecurrenceCount | Checks whether the event has recurrence count. |
|  | RangeEndDate | Gets or sets the event range end date. |
|  | RangeStartDate | Gets or sets the event range start date. |
|  | RangeRecurrenceCount | Gets or sets the event range recurrence count. |
|  | IsSpecific | Checks whether the event occurs in Specific recurrence type. |

### Adding Recurrence Appointment using Recurrence Builder
Schedule appointment [RecurrenceRule](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleAppointment~RecurrenceRule.html) is used to populate the required recursive appointment collection in a specific pattern. `RRULE` can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

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
        recurrenceProperties.IsWeeklySunday = false;
        recurrenceProperties.IsWeeklyMonday = true;
        recurrenceProperties.IsWeeklyTuesday = false;
        recurrenceProperties.IsWeeklyWednesday = false;
        recurrenceProperties.IsWeeklyThursday = false;
        recurrenceProperties.IsWeeklyFriday = false;
        recurrenceProperties.IsWeeklySaturday = false;
        recurrenceProperties.RangeRecurrenceCount = 10;
        recurrenceProperties.RecurrenceRule = DependencyService.Get<IRecurrenceBuilder>().RRuleGenerator(recurrenceProperties, scheduleAppointment.StartTime, scheduleAppointment.EndTime);

    // Setting recurrence rule to schedule appointment
        scheduleAppointment.RecurrenceRule = recurrenceProperties.RecurrenceRule; 

{% endhighlight %} 

![](PopulatingAppointments_images/recurrence.png)

## Appearance Customization
The default appearance of the appointment can be customized by using the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle.html) property and [AppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs.html). The event and property is used to customize or override the default template of the Appointments.

* [Customize appearance using Style](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-style) 
* [Customize appearance using Event](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-event) 
* [Customize appearance using Custom View](https://help.syncfusion.com/xamarin/sfschedule/data-bindings#customize-appearance-using-custom-view) 

### Customize appearance using Style
Schedule appointment can be customized by setting appointment style properties such as [TextColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~TextColor.html), [TextStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~TextStyle.html), [BorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~BorderColor.html), [BorderCornerRadius](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~BorderCornerRadius.html), [BorderWidth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~BorderWidth.html) to the [AppointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle.html) property of `SfSchedule`.
{% tabs %} 
{% highlight c# %}

        //Creating Appointment style 
        AppointmentStyle appointmentStyle = new AppointmentStyle();
        appointmentStyle.TextColor = Color.Red;
        appointmentStyle.TextStyle = Font.SystemFontOfSize(15, FontAttributes.Bold);
        appointmentStyle.BorderColor = Color.Blue;
        appointmentStyle.BorderCornerRadius = 12;
        appointmentStyle.BorderWidth = 10;

		//Setting Appointment Style 
        schedule.AppointmentStyle = appointmentStyle;

{% endhighlight %}
{% highlight xaml %} 
 
     <syncfusion:SfSchedule x:Name="schedule" ScheduleView="DayView" DataSource="{Binding Meetings}">
        <syncfusion:SfSchedule.AppointmentStyle>
             <syncfusion:AppointmentStyle BorderWidth="10" 
                TextColor="Red" 
                BorderCornerRadius="10" 
                TextSize="12"
                BorderColor="Blue">
        </syncfusion:AppointmentStyle>
    </syncfusion:SfSchedule.AppointmentStyle>    
  </syncfusion:SfSchedule>
 
{% endhighlight %}
{% endtabs %} 

![](PopulatingAppointments_images/style.png)

### Customize appearance using Event
Schedule appointment can be customized during runtime using [OnAppointmentLoadedEvent](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule+OnAppointmentLoadedEventHandler.html). `ScheduleAppointment` style can be customized using the `appointmentStyle` property.

[AppointmentLoadedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs.html) has below properties,

•	[appointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~appointment.html) – Contains the appointments values.
•	[appointmentStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~appointmentStyle.html) – Gets and sets the appointments style.
•	[view](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~view.html) -  Sets the Custom UI for Appointments.
•	[Bounds](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentLoadedEventArgs~Bounds.html) – Contains the UI bounds of appointment.

{% highlight c# %} 
 
     schedule.OnAppointmentLoadedEvent += Schedule_OnAppointmentLoadedEvent;
 
    private void Schedule_OnAppointmentLoadedEvent(object sender, AppointmentLoadedEventArgs args)
    {
	if (args.appointment != null && (args.appointment as Meeting).EventName == "Meeting")
        {
        args.appointmentStyle.BorderColor = Color.Blue;
        args.appointmentStyle.BorderCornerRadius = 12;
        args.appointmentStyle.BorderWidth = 10;
        }
    }
 
{% endhighlight %}

## Customize appearance using Custom View
Default appointment UI can be changed using `view` property passed through `AppointmentLoadedEventArgs`.

{% highlight c# %} 
 
    schedule.OnAppointmentLoadedEvent += Schedule_OnAppointmentLoadedEvent;

    private void Schedule_OnAppointmentLoadedEvent(object sender, AppointmentLoadedEventArgs args)
    {
        Button button = new Button();
        button.BackgroundColor = Color.Green;
        if (args.appointment != null)
            button.Text = (args.appointment as Meeting).EventName;
        args.view = button;
    }
 
{% endhighlight %}

## Selection
Schedule control has built-in events to handle tapped, double tapped and long pressed touch actions.

•	[CellTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule+CellTappedEventHandler.html)
•	[CellDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule+CellTappedEventHandler.html)
•	[CellLongPressed](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule+CellTappedEventHandler.html)

These events will be triggered while perform respective touch actions in timeslots, month cells and in appointments. All the three events contain the same argument [CellTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.CellTappedEventArgs.html) which holds selected appointment and date time details in it.

• [Appointment](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.CellTappedEventArgs~Appointment.html) -  Contains the selected appointment value, it will be null, if any time slots selected. Recurrence appointment`s occurrence will have master appointment value. 
• [DateTime](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.CellTappedEventArgs~Datetime.html) - Contains selected time slot DateTime value.

>N Selected Recurrence appointment`s occurrence value will be master appointment value and the value can be handled based on the master appointment and DateTime (DateTime will be selected date).

{% highlight c# %} 
 
        schedule.CellTapped += Schedule_CellTapped;
	schedule.CellDoubleTapped += Schedule_CellDoubleTapped;
	schedule.CellLongPressed += Schedule_CellLongPressed;


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

### Selection customization
The default selection of an appointment can be customized by using [SelectionBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~SelectionBorderColor.html), [SelectionTextColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.AppointmentStyle~SelectionTextColor.html) properties in `AppointmentStyle` property of `SfSchedule`. The property is used to customize or override the default selection of the appointments.

N> `BorderWidth` value must be set to highlight `SelectionBorderColor`.

{% tabs %} 
{% highlight c# %} 
 
    //Creating an appointment style 
        AppointmentStyle appointmentStyle = new AppointmentStyle();
        appointmentStyle.SelectionBorderColor = Color.Yellow;
        appointmentStyle.SelectionTextColor = Color.Yellow;

    //Setting an appointment style 
        schedule.AppointmentStyle = appointmentStyle;
 
{% endhighlight %}
  
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
{% endtabs %} 

![](PopulatingAppointments_images/selection.png)
