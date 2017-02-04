---
layout: post
title: Appearance & Stylings in Schedule
description: Learn how to Customize appointment and month cell.
platform: Xamarin
control: SfSchedule
documentation: ug
---

# Appearance & Styling

## Header Customization

You can customize the header of the Schedule using `HeaderStyle` and `HeaderHeight` property in schedule.

### Header Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% highlight c# %}

	sfSchedule.HeaderHeight = 50;

{% endhighlight %}

### Labels

you can change the header format and style using `HeaderStyle` property in schedule.

#### Fonts and colors

You can change the backgroundcolor,text style and text size using properties such as `BackgroundColor`,`TextStyle`, `TextSize` of Header using `HeaderStyle` property in schedule.

{% highlight c# %}

	HeaderStyle headerStyle = new HeaderStyle();
	headerStyle.BackgroundColor = Color.Transparent;
	headerStyle.TextStyle = Font.Default;
	headerStyle.TextSize = 12;
	headerStyle.TextColor=Color.Black;
	schedule.HeaderStyle = headerStyle;

{% endhighlight %}

## View Header Customization

You can customize the header of the Schedule using `ViewHeaderStyle` and `ViewHeaderHeight` property in schedule.

### Labels

#### Fonts and Colors

You can change the backgroundcolor,text style and text size using properties such as `BackgroundColor`,`DateTextStyle`, `DayTextStyle`, `DayTextColor`, `DateTextColor`,`DateTextSize`, `DayTextSize` of ViewHeader using `ViewHeaderStyle` property in schedule.

{% highlight c# %}

	ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
	viewHeaderStyle.BackgroundColor = Color.Transparent;
	viewHeaderStyle.DayTextColor = Color.Black;
	viewHeaderStyle.DateTextColor = Color.Gray;
	viewHeaderStyle.DateTextSize = 15;
	viewHeaderStyle.DayTextSize = 10;
	viewHeaderStyle.DateTextStyle = Font.Default;
	viewHeaderStyle.DayTextStyle = Font.Default;
	schedule.ViewHeaderStyle = viewHeaderStyle;

{% endhighlight %}

### ViewHeader Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% highlight c# %}

	sfSchedule.ViewHeaderHeight = 50;

{% endhighlight %}

## Timeslots customization

### Custom Day View

#### Non-Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `DayViewSettings`.

{% tabs %}

{% highlight xaml %}

	<schedule:SfSchedule>
	<schedule:SfSchedule.DayViewSettings>
	<!--setting working hours properties -->
	<schedule:DayViewSettings
	NonWorkingHoursTimeSlotColor="Silver"
	NonWorkingHoursTimeSlotBorderColor="Gray">
	</schedule:DayViewSettings>
	</schedule:SfSchedule.DayViewSettings>
	</schedule:SfSchedule>

{% endhighlight %}

{% highlight C# %}

	//setting working hours properties 
	DayViewSettings dayViewSettings = new DayViewSettings ();
	dayviewsettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
	dayviewsettings.NonWorkingHoursTimeSlotColor = Color.Silver;
	sfschedule.DayViewSettings = dayviewsettings;

{% endhighlight %}

{% endtabs %}

#### Timeslots 

You can differentiate working hours with non-working hour timeslots by its color using `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.

{% tabs %}

{% highlight xaml %}

	<schedule:SfSchedule>
	<schedule:SfSchedule.DayViewSettings>
	<!--setting working hours properties -->
	<schedule:DayViewSettings
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
	dayviewsettings.TimeSlotColor = Color.Yellow;
	dayviewsettings.TimeSlotBorderColor = Color.Aqua;
	dayviewsettings.TimeSlotBorderStrokeWidth = 5;
	sfschedule.DayViewSettings = dayviewsettings;

{% endhighlight %}

{% endtabs %}

#### Lines

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

#### Labels

You can change the format,colors,size of text using `TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `DayLabelSettings` in `DayViewSettings`.

{% highlight c# %}

	DayViewSettings dayViewSettings = new DayViewSettings();
	DayLabelSettings dayLabelSettings = new DayLabelSettings();
	dayLabelSettings.TimeFormat = "hh mm";
	dayLabelSettings.TimeLabelColor = Color.Blue;
	dayLabelSettings.TimeLabelSize = 10;
	dayViewSettings.DayLabelSettings = dayLabelSettings;
	sfSchedule.DayViewSettings = dayViewSettings;

{% endhighlight %}

#### All Day Appointments Color

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

![](AppearanceAndStyling_images/DayViewAppearance/DayView.png) 

### Custom Week View

#### Non-Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `WeekViewSettings`.

{% tabs %}

{% highlight xaml %}

	<schedule:SfSchedule ScheduleView="WeekView">
	<schedule:SfSchedule.WeekViewSettings>
	<!--setting week view settings properties -->
	<schedule:WeekViewSettings
	NonWorkingHoursTimeSlotColor="Silver"
	NonWorkingHoursTimeSlotBorderColor="Gray">
	</schedule:WeekViewSettings>
	</schedule:SfSchedule.WeekViewSettings>
	</schedule:SfSchedule>

{% endhighlight %}

{% highlight c# %}

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings ();
	weekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
	weekViewSettings.NonWorkingHoursTimeSlotColor = Color.Silver;
	sfschedule.WeekViewSettings = weekViewSettings;
	this.Content= sfschedule;

{% endhighlight %}

{% endtabs %}

#### Timeslots

You can differentiate working hours with non-working hour timeslots by its color using `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.

{% tabs %}

{% highlight xaml %}

	<schedule:SfSchedule ScheduleView="WeekView">
	<schedule:SfSchedule.WeekViewSettings>
	<!--setting week view settings properties -->
	<schedule:WeekViewSettings
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
	weekViewSettings.TimeSlotBorderColor = Color.Aqua;
	weekViewSettings.TimeSlotColor = Color.Yellow;
	weekViewSettings.TimeSlotBorderStrokeWidth = 5;
	sfschedule.WeekViewSettings = weekViewSettings;
	this.Content= sfschedule;

{% endhighlight %}

{% endtabs %}

#### Lines

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

#### Labels

You can change the format,colors,size,style of text using `TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `WeekLabelSettings` in `WeekViewSettings`.

{% highlight c# %}

	WeekViewSettings weekViewSettings = new WeekViewSettings();
	WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
	weekLabelSettings.TimeFormat = "hh mm";
	weekLabelSettings.TimeLabelColor = Color.Blue;
	weekLabelSettings.TimeLabelSize = 10;
	weekViewSettings.WeekLabelSettings = weekLabelSettings;
	sfSchedule.WeekViewSettings = weekViewSettings;

{% endhighlight %}

#### All Day Appointments Color

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

![](AppearanceAndStyling_images/WeekViewAppearance/WeekView.png)

### Custom Work Week View

#### Non-Working Hours 

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, properties of `WorkWeekViewSettings`.

{% tabs %}

{% highlight xaml %}

	<schedule:SfSchedule ScheduleView="WorkWeekView">
	<schedule:SfSchedule.WorkWeekViewSettings>
	<!--setting workweek view settings properties -->
	<schedule:WorkWeekViewSettings
	NonWorkingHoursTimeSlotColor="Silver"
	NonWorkingHoursTimeSlotBorderColor="Gray">
	</schedule:WorkWeekViewSettings>
	</schedule:SfSchedule.WorkWeekViewSettings>
	</schedule:SfSchedule>

{% endhighlight %}

{% highlight c# %}

	//setting workweekviewsettings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
	workWeekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
	workWeekViewSettings.NonWorkingHoursTimeSlotColor = Color.Silver;
	sfschedule.WorkWeekViewSettings = workWeekViewSettings;
	this.Content= sfschedule;

{% endhighlight %}

{% endtabs %}

#### Timeslots 

You can also differentiate working hours with non-working hour timeslots by its color using `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.

{% tabs %}

{% highlight xaml %}

	<schedule:SfSchedule ScheduleView="WorkWeekView">
	<schedule:SfSchedule.WorkWeekViewSettings>
	<!--setting workweek view settings properties -->
	<schedule:WorkWeekViewSettings
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
	workWeekViewSettings.TimeSlotBorderColor = Color.Aqua;
	workWeekViewSettings.TimeSlotColor = Color.Yellow;
	workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
	sfschedule.WorkWeekViewSettings = workWeekViewSettings;
	this.Content= sfschedule;

{% endhighlight %}

{% endtabs %}

#### Lines

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

#### Labels

You can change the format , colors, size, style of text using `TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `WorkWeekLabelSettings` in `WorkWeekViewSettings`.

{% highlight c# %}

	WorkWeekViewSettings workweekViewSettings = new WorkWeekViewSettings();
	WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
	workWeekLabelSettings.TimeFormat = "hh mm";
	workWeekLabelSettings.TimeLabelColor = Color.Blue;
	workWeekLabelSettings.TimeLabelSize = 10;
	workweekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
	sfSchedule.WorkWeekViewSettings = workweekViewSettings;

{% endhighlight %}

#### All Day Appointments Color

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

![](AppearanceAndStyling_images/WorkWeekViewAppearance/WorkWeekView.png)

### Interval

You can change the time interval and time interval height using `TimeInterval` and `TimeIntervalHeight` in schedule.

{% tabs %}

{% highlight xaml %}

	<schedule:SfSchedule ScheduleView="WeekView" 
	TimeInterval="5"
	TimeIntervalHeight="10" >
	</schedule:SfSchedule>

{% endhighlight %}

{% highlight c# %}

	sfSchedule.TimeInterval = 5;
	sfSchedule.TimeIntervalHeight = 10;

{% endhighlight %}

{% endtabs %}

![](Appearance/Appearance2.jpeg)
