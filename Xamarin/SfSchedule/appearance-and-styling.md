---
layout: post
title: Appearance & Stylings in Schedule
description: Learn how to Customize appointment and month cell.
platform: Xamarin
control: SfSchedule
documentation: ug
---

# Appearance & Styling

## MonthCell Customization

Schedule views are designed as per the native calendar control with some enriched user interface for the control interaction and usability. Month view cell contains the date along with its appointments if available. 

You can customize the MonthView in two ways, 

* MonthViewCellStyle property.
* MonthCellLoadedEvent.

**Using MonthViewCellStyle property**

MonthView can be customized by setting monthViewCellStyle properties such as TextColor,TextStyle,BackgroundColor to the `MonthViewCellStyle` property of schedule.

{% tabs %}

{% highlight xaml %}

    <schedule:MonthViewCellStyle BackgroundColor="Gray"
        TextSize="12" 
        TextColor="Blue">
	</schedule:MonthViewCellStyle>
	
{% endhighlight %}

{% highlight C# %}

    MonthViewCellStyle monthViewCellStyle = new MonthViewCellStyle();
    monthViewCellStyle.BackgroundColor = Color.Gray;
    monthViewCellStyle.TextColor = Color.Blue;
    monthViewCellStyle.TextSize = 12;
    monthViewCellStyle.TextStyle=Font.SystemFontOfSize(12, FontAttributes.Bold);
    sfschedule.MonthCellStyle = monthViewCellStyle;
	
{% endhighlight %}

{% endtabs %}

**Using MonthCellLoaded Event**

You can customize the month view during runtime using `OnMonthCellLoaded Event`. In OnMonthCellLoaded event, the properties such as cellStyle,appointments,date,view and boolean properties such as isToday,isPreviousMonthDate,isNextMonthDate,isBlackOutDate are passed in the `MonthCellLoadedEventArgs`.

Month cells can be customized using the `cellStyle` property as follows,

{% highlight C# %}
    
    sfschedule.OnMonthCellLoadedEvent += (object sender, MonthCellLoadedEventArgs args) =>
		{
		    if (args.isToday)
			{
				//setting Month Cell style properties
				args.cellStyle.BackgroundColor = Color.Gray;
				args.cellStyle.TextColor = Color.Blue;
				args.cellStyle.TextSize = 12;
				args.cellStyle.TextStyle = Font.SystemFontOfSize(12, FontAttributes.Bold);
				}
			};

{% endhighlight %}

You can also add an object in the month cell view using `view` property passed through `MonthCellLoadedEventArgs`.

{% highlight C# %}

	sfschedule.OnMonthCellLoadedEvent += (object sender, MonthCellLoadedEventArgs args) =>
		{
			Button button = new Button();
			button.BackgroundColor = Color.Green;
			args.view = button;
		}
		
{% endhighlight %}

![](Appearance/Appearance1.jpeg)

## Appointment Customization.

`ScheduleAppointment` created in schedule are arranged based on its duration, where the appointments viewed through day, week and work week view  are positioned in the timeslots.

You can customize the Schedule Appointments in two ways.

* AppointmentStyle property.
* AppointmentLoadedEvent.

**Using AppointmentStyle property**

Schedule Appointment can be customized by setting appointmentstyle properties such as TextColor,TextStyle,BorderColor,BorderCornerRadius,BorderWidth,SelectionBorderColor,SelectionTextColor to the `AppointmentStyle` property of schedule.

{% tabs %}

{% highlight xaml %}

    <schedule:AppointmentStyle BorderWidth="10" 
		TextColor="Red"
		BorderCornerRadius="10" 
		TextSize="12"
		SelectionTextColor="Yellow" 
		SelectionBorderColor="Yellow"
		BorderColor="Blue">
	</schedule:AppointmentStyle>
	
{% endhighlight %}

{% highlight C# %}

    AppointmentStyle appointmentStyle = new AppointmentStyle();
	appointmentStyle.TextColor = Color.Red;
	appointmentStyle.TextStyle = Font.SystemFontOfSize(15,FontAttributes.Bold);
	appointmentStyle.BorderColor = Color.Blue;
	appointmentStyle.BorderCornerRadius = 12;
	appointmentStyle.BorderWidth = 10;
	appointmentStyle.SelectionBorderColor = Color.Yellow;
	appointmentStyle.SelectionTextColor = Color.Yellow;
	sfschedule.AppointmentStyle = appointmentStyle;
	
{% endhighlight %}

{% endtabs %}

**Using AppointmentLoaded Event**

You can customize the appointment view during runtime using `OnAppointmentLoaded Event`.In OnAppointmentLoaded event, the properties such as appointmentStyle,appointment,view,Bounds are passed in the `AppointmentLoadedEventArgs`.

ScheduleAppointment can be customized using the `appointmentStyle` property.

{% highlight C# %}

    sfschedule.OnAppointmentLoadedEvent += (object sender, AppointmentLoadedEventArgs args) =>
	{
		args.appointmentStyle.TextColor = Color.Red;
		args.appointmentStyle.TextStyle = Font.SystemFontOfSize(15, FontAttributes.Bold);
		args.appointmentStyle.BorderColor = Color.Blue;
		args.appointmentStyle.BorderCornerRadius = 12;
		args.appointmentStyle.BorderWidth = 10;
		args.appointmentStyle.SelectionBorderColor = Color.Yellow;
		args.appointmentStyle.SelectionTextColor = Color.Yellow;
	};

{% endhighlight %}

You can also add an object in the appointment view using `view` property passed through `AppointmentLoadedEventArgs`.

{% highlight C# %}

    Button button = new Button();
    button.BackgroundColor = Color.Green;
    args.view = button;
	
{% endhighlight %}

>**Note** : You can only get appointment properties such as subject,location,StartTime,EndTime,etc from the `AppointmentLoadedEventArgs`.

![](Appearance/appointCust.png)

## Panel Customization

### Custom Day View

#### Date Time Formating

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `DayViewSettings`.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule>
        <schedule:SfSchedule.DayViewSettings>
        <schedule:DayViewSettings VerticalLineColor="Green"
        VerticalLineStrokeWidth="5">
        </schedule:DayViewSettings>
        </schedule:SfSchedule.DayViewSettings>
    </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}
    
    DayViewSettings dayviewsettings = new DayViewSettings();
    dayviewsettings.VerticalLineColor = Color.Green;
	dayviewsettings.VerticalLineStrokeWidth = 5;
	
    sfschedule.DayViewSettings = dayViewSettings;
    this.content = sfschedule;
    
 {% endhighlight %} 
 
 {% endtabs %}
 
#### Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule>
        <schedule:SfSchedule.DayViewSettings>
            <!--setting working hours properties -->
            <schedule:DayViewSettings
            NonWorkingHoursTimeSlotColor="Silver"
            NonWorkingHoursTimeSlotBorderColor="Gray"
            TimeSlotColor="Yellow"
            TimeSlotBorderColor="Aqua"
            TimeSlotBorderStrokeWidth="5">
            </schedule:DayViewSettings>
        </schedule:SfSchedule.DayViewSettings>
    </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight C# %}

    //setting working hours properties 
    DayViewSettings dayViewSettings = new DayViewSettings ();
    dayviewsettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
    dayviewsettings.NonWorkingHoursTimeSlotColor = Color.Silver;
    dayviewsettings.TimeSlotColor = Color.Yellow;
    dayviewsettings.TimeSlotBorderColor = Color.Aqua;
    dayviewsettings.TimeSlotBorderStrokeWidth = 5;
    sfschedule.DayViewSettings = dayviewsettings;
    
{% endhighlight %}

{% endtabs %}

#### All Day Appointments Panel

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `DayViewSettings`.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule.DayViewSettings>
		<schedule:DayViewSettings
			AllDayAppointmentLayoutColor="Fuchsia">
		</schedule:DayViewSettings>
	</schedule:SfSchedule.DayViewSettings>
	
{% endhighlight %}

{% highlight c# %}

    dayviewsettings.AllDayAppointmentLayoutColor = Color.Pink; 

 {% endhighlight %} 
 
 {% endtabs %}

### Custom Week View

#### Date Time Formating

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WeekViewSettings`.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule ScheduleView="WeekView">
        <schedule:SfSchedule.WeekViewSettings>
        <schedule:WeekViewSettings 
            VerticalLineColor="Green"
            VerticalLineStrokeWidth="5">
          </schedule:WeekViewSettings>
        </schedule:SfSchedule.WeekViewSettings>
    </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}
    
    WeekViewSettings weekViewSettings = new WeekViewSettings ();
    weekViewSettings.VerticalLineColor = Color.Green;
    weekViewSettings.VerticalLineStrokeWidth = 5;
    sfschedule.WeekViewSettings = weekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule ScheduleView="WeekView">
        <schedule:SfSchedule.WeekViewSettings>
			<!--setting week view settings properties -->
		    <schedule:WeekViewSettings
			NonWorkingHoursTimeSlotColor="Silver"
			NonWorkingHoursTimeSlotBorderColor="Gray"
			TimeSlotColor="Yellow"
			TimeSlotBorderColor="Aqua" 
			TimeSlotBorderStrokeWidth="5">
            </schedule:WeekViewSettings>
        </schedule:SfSchedule.WeekViewSettings>
     </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}

    //setting week view settings properties
    WeekViewSettings weekViewSettings = new WeekViewSettings ();
    weekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
    weekViewSettings.NonWorkingHoursTimeSlotColor = Color.Silver;
    weekViewSettings.TimeSlotBorderColor = Color.Aqua;
    weekViewSettings.TimeSlotColor = Color.Yellow;
    weekViewSettings.TimeSlotBorderStrokeWidth = 5;
    sfschedule.WeekViewSettings = weekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### All Day Appointments Panel

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `WeekViewSettings`.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule ScheduleView="WeekView">
        <schedule:SfSchedule.WeekViewSettings>
			<!--setting week view settings properties -->
			<schedule:WeekViewSettings
			AllDayAppointmentLayoutColor="Fuchsia"/>
        </schedule:SfSchedule.WeekViewSettings>
     </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}

    //setting week view settings properties
    WeekViewSettings weekViewSettings = new WeekViewSettings ();
    weekViewSettings.AllDayAppointmentLayoutColor = Color.Pink;
    sfschedule.WeekViewSettings = weekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

### Custom Work Week View

#### Date Time Formating

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WorkWeekViewSettings`.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule ScheduleView="WorkWeekView">
        <schedule:SfSchedule.WorkWeekViewSettings>
		    <schedule:WeekViewSettings 
				VerticalLineColor="Green"
				VerticalLineStrokeWidth="5">
          </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
     </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
    workWeekViewSettings.VerticalLineColor = Color.Green;
    workWeekViewSettings.VerticalLineStrokeWidth = 5;
    sfschedule.WorkWeekViewSettings = (workWeekViewSettings);
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### Working Hours 

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule ScheduleView="WorkWeekView">
        <schedule:SfSchedule.WorkWeekViewSettings>
			<!--setting workweek view settings properties -->
			<schedule:WorkWeekViewSettings
			NonWorkingHoursTimeSlotColor="Silver"
			NonWorkingHoursTimeSlotBorderColor="Gray"
			TimeSlotColor="Yellow"
			TimeSlotBorderColor="Aqua" 
			TimeSlotBorderStrokeWidth="5">
          </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
     </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    //setting workweekviewsettings properties
    WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
    workWeekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
    workWeekViewSettings.NonWorkingHoursTimeSlotColor = Color.Silver;
    workWeekViewSettings.TimeSlotBorderColor = Color.Aqua;
    workWeekViewSettings.TimeSlotColor = Color.Yellow;
    workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
    sfschedule.WorkWeekViewSettings = workWeekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### All Day Appointments Panel

You can change the all day appointment panel color using the property `AllDayAppointmentLayoutColor` of `WorkWeekViewSettings`.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule ScheduleView="WorkWeekView">
        <schedule:SfSchedule.WorkWeekViewSettings>
			<!--setting workweek view settings properties -->
			<schedule:WorkWeekViewSettings
			AllDayAppointmentLayoutColor="Fuchsia">
          </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
     </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    //setting workweekviewsettings properties
    WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
    workWeekViewSettings.AllDayAppointmentLayoutColor = Color.Pink;
    sfschedule.WorkWeekViewSettings = workWeekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

## Inline view Customization.

You can able to know the details of appointments in inline using `MonthAppointmentInlineTapped` event in `Schedule`.Details of the selected  appointment and the corresponding date is passed through `MonthInlineAppointmentTappedEventArgs` as `selectedAppointment` and `selectedDate` respectively.

{% highlight C# %}
    
    sfschedule.MonthInlineAppointmentTapped += (object sender, MonthInlineAppointmentTappedEventArgs args) =>
	{
		var appointment = args.selectedAppointment;
		var date= args.selectedDate;
	};

{% endhighlight %}

![](Appearance/Appearance2.jpeg)

![](Appearance/Appearance3.jpeg)