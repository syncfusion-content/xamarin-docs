---
layout: post
title: Timeline view scheduler | Xamarin.Forms | Syncfusion
description: Xamarin.Forms scheduler timeline view displays the dates in a horizontal time axis with desired days count, displays events accurately across the time slots.
platform: xamarin
control: SfScheduler
documentation: ug
---

# Timeline View in Xamarin Scheduler (SfSchedule)

`TimelineView` displays the dates in horizontal time axis with the desired day's count. You can see the past or future dates by scrolling to the right or left. Each view displays events accurately across the time slots with an intuitive drag-and-drop feature. It provides support to highlight the selected region of time slots and handle interaction.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView"/> 
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for Xamarin.Forms from [here](https://github.com/SyncfusionExamples/Timeline-view).

![Timeline view in xamarin forms](timeline-view-images/xamarin-forms-timeline-view.png)

## Timeline view days count

You can customize the number of days in `TimelineView` using the [DaysCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_DaysCount) property of [TimelineViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html). By default, value of the timeline days count is -1, and single day will be visible.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <syncfusion:SfSchedule.TimelineViewSettings>
        <!--setting days count property-->
        <syncfusion:TimelineViewSettings 
            DaysCount="10" />
    </syncfusion:SfSchedule.TimelineViewSettings> 
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
//Customizing days count
timelineViewSettings.DaysCount = 10;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Timeline view in xamarin forms](timeline-view-images/xamarin-forms-timeline-view-days-count.png)

## Timeline view based on day, week, work week, and month.
 
You can achieve timeline day, timeline week, timeline work week, and timeline month view with the default value of `DaysCount` by dynamically switching between day, week, work week, and month view to timeline view with respective visible dates. 
 
>**NOTE**
For other value of `DaysCount`, only timeline view visible dates will be displayed as mentioned days count on dynamic view switching.

## Customized working hours

You can customize the [StartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_EndHour) properties of `TimelineView` to show only the required time duration for end users. You can also set `StartHour` and `EndHour` in double value, which will be converted to time to show the required time duration in minutes. The default value for `StartHour` and `EndHour` value is 0 to 24 to show all the time slots in `TimelineView`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <schedule:SfSchedule.TimelineViewSettings>
        <!--setting visible hours properties-->
        <schedule:TimelineViewSettings
            StartHour="09"
            EndHour="13">
        </schedule:TimelineViewSettings>
    </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>    
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.StartHour = 09;
timelineViewSettings.EndHour = 13;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Working hours customization in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-time-slot-custom-workinghour.png)

>**NOTE**
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `InvalidDataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException` will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If custom `TimeInterval` is given, then the number of time slots calculated based on given `TimeInterval` should result in integer value (total minutes % `TimeInterval` = 0), otherwise next immediate time interval that result in integer value when divide total minutes of a day will be considered. For example, if `TimeInterval`="135” (2 Hours 15 minutes) and total minutes = 1440 (24 Hours per day), then `TimeInterval` will be changed to "144” (1440%144=0) by considering (total minutes % TimeInterval = 0); it will return integer value for time slots rendering.
* If the custom `StartHour` and `EndHour` are given, then the number of time slots calculated based on given `StartHour` and `EndHour` should result in integer value, otherwise next immediate `TimeInterval` will be considered until the result is integer value. For example, if `StartHour` is 9 (09:00AM), `EndHour` is 18.25 (06:15 PM), `TimeInterval` is 30 minutes, and total minutes = 555 ((18.25-9)*60), then the `TimeInterval` will be changed to "37” (555%37=0) by considering (total minutes % `TimeInterval` = 0); it will return integer value for time slots rendering.

## Special time regions

You can restrict user interaction such as selection and highlight specific region of time in `TimelineView` by adding `SpecialTimeRegion` in the [SpecialTimeRegions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SpecialTimeRegions) property of `SfSchedule`. You need to set the [StartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeRegionSettings.html#Syncfusion_SfSchedule_XForms_TimeRegionSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeRegionSettings.html#Syncfusion_SfSchedule_XForms_TimeRegionSettings_EndHour) properties of [TimeRegionSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeRegionSettings.html) to create `SpecialTimeRegion`. You can also set `StartHour` and `EndHour` in double value, which will be converted to time to show the required time duration in minutes. By default, the values of `StartHour` and `EndHour` are 0.

### Special time region appearance

You can customize the appearance of `SpecialTimeRegion` using the [Color](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeRegionSettings.html#Syncfusion_SfSchedule_XForms_TimeRegionSettings_Color) and [TextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeRegionSettings.html#Syncfusion_SfSchedule_XForms_TimeRegionSettings_TextColor) properties of `TimeRegionSettings`.

### Selection restriction in time slots

You can enable/disable the touch interaction of `SpecialTimeRegion` using [CanEdit](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeRegionSettings.html#Syncfusion_SfSchedule_XForms_TimeRegionSettings_CanEdit) property of `TimeRegionSettings`. By default, its value is true.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <!--setting Special time regions property-->
    <schedule:SfSchedule.SpecialTimeRegions>
        <schedule:TimeRegionSettings 
            StartHour="12" 
            EndHour="13" 
            Text="Lunch"
            CanEdit="False"
            Color="#EAEAEA"
            TextColor="Black"/>
    </schedule:SfSchedule.SpecialTimeRegions>
</schedule:SfSchedule>     
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
ObservableCollection<TimeRegionSettings> specialTimeRegions = new ObservableCollection<TimeRegionSettings>();
//Setting Special time regions property
TimeRegionSettings timeRegionSettings = new TimeRegionSettings();
timeRegionSettings.StartHour = 12;
timeRegionSettings.EndHour = 13;
timeRegionSettings.Text = "Lunch";
timeRegionSettings.Color = Color.FromHex("#EAEAEA");
timeRegionSettings.TextColor = Color.Black;
timeRegionSettings.CanEdit = false;
specialTimeRegions.Add(timeRegionSettings);
schedule.SpecialTimeRegions = specialTimeRegions;
{% endhighlight %}
{% endtabs %}

![Special time region in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-special-time-region.png)

## Time interval

You can customize the interval of time slots in `TimelineView` by setting [TimeInterval](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_TimeInterval) property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView" TimeInterval="180"/>     
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView; 
schedule.TimeInterval = 180;
{% endhighlight %}
{% endtabs %}

![Time interval in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-time-interval.png)

>**NOTE**
If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` as “hh:mm”. By default, `TimeFormat` is "hh a". Refer to this [documentation](https://help.syncfusion.com/xamarin/sfschedule/weekview#time-label-formatting) for changing `TimeFormat` value.


## Time interval height 

You can customize the interval height of time slots in `TimelineView` by setting the [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_TimeIntervalHeight) property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView" TimeIntervalHeight="180"/>     
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView; 
schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% endtabs %}

![Time interval height in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-time-interval-height.png)

### Full screen scheduler
Schedule time interval height can be adjusted based on screen height by changing the value of `TimeIntervalHeight` property to -1. It will auto-fit to the screen height and width.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView" TimeIntervalHeight="-1"/>     
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView; 
schedule.TimeIntervalHeight = -1;
{% endhighlight %}
{% endtabs %}

>**NOTE**
In Timeline view, If the time slot duration such as `DaysCount` ,`StartHour`, or `EndHour` is within the width of the screen, the `TimeIntervalHeight` will automatically be adjusted to the screen, otherwise the `TimeIntervalHeight` will be adjusted to 100 offset value.

## Nonworking days

You can add the non-working days in `TimelineView` using [NonWorkingsDays](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_NonWorkingsDays) property of `TimelineViewSettings`. By default, there is no non-working day in `TimelineView`.

{% tabs %}
{% highlight c# %}
var nonWorkingDays = new ObservableCollection<DayOfWeek>();
nonWorkingDays.Add(DayOfWeek.Monday);
nonWorkingDays.Add(DayOfWeek.Friday);
var timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.NonWorkingsDays = nonWorkingDays;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

## First day of week

By default, schedule control will be rendered with Sunday as the first day of the week. It can be customized to any day of the week using the `FirstDayOfWeek` property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView" FirstDayOfWeek="3"/>   
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView; 
schedule.FirstDayOfWeek = 3;
{% endhighlight %}
{% endtabs %}

![First day of week in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-first-day-of-week.png)

>**NOTE**
In Timeline view, `FirstDayOfWeek` will be applied only when `DayCounts` property of `TimelineViewSettings` is 7.

## Appointment height

You can customize the height of the appointment in `TimelineView` using the [AppointmentHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_AppointmentHeight) property of `TimelineViewSettings`. By default, its value is 50.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <schedule:SfSchedule.TimelineViewSettings>
        <!--setting appointment height property-->
        <schedule:TimelineViewSettings
            AppointmentHeight="100" />
    </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Create new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.AppointmentHeight = 100;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Appointment height in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-appointment-height.png)

>**NOTE**
When a greater number of appointments is added in the same time slot, appointment height will be calculated automatically without considering the `AppointmentHeight` property to display all the appointment in the view.

## View header tapped event

You can handle single tap action of ViewHeader using the `ViewHeaderTapped` event of `SfSchedule`. This event occurs when the `ViewHeader` is tapped. This event contains `ViewHeaderTappedEventArgs` argument, which holds the details of `DateTime` in it.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" 
    ScheduleView="TimelineView "   
    ViewHeaderTapped="Handle_ViewHeaderTapped"> 
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
//Creating new instance of Schedule 
SfSchedule schedule = new SfSchedule(); 
schedule.ScheduleView = ScheduleView.TimelineView; 
schedule.ViewHeaderTapped += OnViewHeaderTapped;
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
private void OnViewHeaderTapped(object sender, ViewHeaderTappedEventArgs e) 
{ 
     var dateTime = e.DateTime; 
}
{% endhighlight %}
{% endtabs %}

## View header customization

You can customize the default appearance of view header in `TimelineView` by using [ViewHeaderStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ViewHeaderStyle) property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView =" TimelineView">
    <schedule:SfSchedule.ViewHeaderStyle>
        <schedule:ViewHeaderStyle
                BackgroundColor="#a9b1fc" 
                DateTextColor="Black" 
                DateFontFamily="Arial">
        </schedule:ViewHeaderStyle>
    </schedule:SfSchedule.ViewHeaderStyle>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
//Create new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.TimelineView;
//Customize the schedule view header
ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
viewHeaderStyle.BackgroundColor = Color.FromHex("#a9b1fc");
viewHeaderStyle.DateTextColor = Color.Black;
viewHeaderStyle.DateFontFamily = "Arial";
schedule.ViewHeaderStyle = viewHeaderStyle;
{% endhighlight %}
{% endtabs %}

![View header customization in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-view-header-customization.png)

>**NOTE**
`FontAttributes` and `FontFamily` are native to the platform. Custom font and the font that are not available in the specified platform will not be applied.

You can customize the height of `ViewHeader` in `TimelineView` by setting the [ViewHeaderHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ViewHeaderHeight) property of `SfSchedule.`

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView ="TimelineView " ViewHeaderHeight="50" />
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView; 
schedule.ViewHeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

![View header height in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-view-header-height.png)

### View header date format

You can customize the date format of `ViewHeader` in `TimelineView` using the [DateFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineLabelSettings.html#Syncfusion_SfSchedule_XForms_TimelineLabelSettings_DateFormat) property of `TimelineLabelSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule>
    <schedule:SfSchedule.TimelineViewSettings>
        <schedule:TimelineViewSettings>
            <schedule:TimelineViewSettings.LabelSettings>
                <schedule:TimelineLabelSettings>
                    <schedule:TimelineLabelSettings.DateFormat>
                        <OnPlatform x:TypeArguments="x:String" iOS="d EEE" Android="d EEE" WinPhone="%d ddd" />
                    </schedule:TimelineLabelSettings.DateFormat>
                </schedule:TimelineLabelSettings>
            </schedule:TimelineViewSettings.LabelSettings>
        </schedule:TimelineViewSettings>
    </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
//Creating new instance of TimelineLabelSettings
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
//Customizing date format
labelSettings.DateFormat = Device.OnPlatform("d EEE", "d EEE", "%d ddd");
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![View header date format in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-view-header-date-format.png)

## Timeslot customization

You can customize the appearance of time slots using the [Color](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_Color), [BorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_BorderColor) and [BorderWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_BorderWidth) properties of `TimelineViewSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <schedule:SfSchedule.TimelineViewSettings>
        <!--setting timeline view settings properties -->
        <schedule:TimelineViewSettings
            Color="#e8eaf9"
            BorderColor="#8490f9"
            BorderWidth="2" />
    </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Create new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.BorderColor = Color.FromHex("#8490f9");
timelineViewSettings.Color = Color.FromHex("#e8eaf9");
timelineViewSettings.BorderWidth = 2;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time slot customization in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-time-slot-customization.png)

## Time label customization

You can customize the format for the labels that mention the time by setting the [TimeFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineLabelSettings.html#Syncfusion_SfSchedule_XForms_TimelineLabelSettings_TimeFormat) property of [LabelSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_LabelSettings) in `TimelineViewSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <schedule:SfSchedule.TimelineViewSettings>
        <!--setting time format property--> 
        <schedule:TimelineViewSettings>
            <schedule:TimelineViewSettings.LabelSettings>
                <schedule:TimelineLabelSettings TimeFormat="hh:mm" />
            </schedule:TimelineViewSettings.LabelSettings>
        </schedule:TimelineViewSettings>
    </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
labelSettings.TimeFormat = "hh:mm";
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time label format in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-time-label-format.png)

### Time label appearance

You can customize the color for the labels that mention the time by setting the [TimeLabelColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineLabelSettings.html#Syncfusion_SfSchedule_XForms_TimelineLabelSettings_TimeLabelColor) property of `LabelSettings` in `TimelineViewSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <schedule:SfSchedule.TimelineViewSettings>
        <!--setting time format property-->
        <schedule:TimelineViewSettings>
            <schedule:TimelineViewSettings.LabelSettings>
                <schedule:TimelineLabelSettings TimeLabelColor="#8490f9" />
            </schedule:TimelineViewSettings.LabelSettings>
        </schedule:TimelineViewSettings>
    </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
labelSettings.TimeLabelColor = Color.FromHex("#8490f9");
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time label appearance in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-time-label-appearance.png)

### Time Label size

You can customize the size of the labels that mention the time by setting the [TimeLabelSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineLabelSettings.html#Syncfusion_SfSchedule_XForms_TimelineLabelSettings_TimeLabelSize) property of `LabelSettings` in `TimelineViewSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <schedule:SfSchedule.TimelineViewSettings>
        <!--setting time format property-->
        <schedule:TimelineViewSettings>
            <schedule:TimelineViewSettings.LabelSettings>
                <schedule:TimelineLabelSettings TimeLabelSize="15" />
            </schedule:TimelineViewSettings.LabelSettings>
        </schedule:TimelineViewSettings>
    </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
labelSettings.TimeLabelSize = 10;	
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time label size in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-time-label-size.png)

## Time ruler size customization

You can customize the height of time ruler in `TimelineView` by setting the [TimeRulerSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimelineViewSettings.html#Syncfusion_SfSchedule_XForms_TimelineViewSettings_TimeRulerSize) property in `TimelineViewSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
   <schedule:SfSchedule.TimelineViewSettings>
       <schedule:TimelineViewSettings TimeRulerSize="0"/>
   </schedule:SfSchedule.TimelineViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.TimelineView;
TimelineViewSettings timelineViewSettings = new DayViewSettings();
timelineViewSettings.TimeRulerSize = 0;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time ruler size in xamarin forms Timeline view](timeline-view-images/xamarin.forms-schedule-timelineview-timerulersizecustomization.jpg)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)
* [Programmatic selection](#programmatic-selection)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectionStyle) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
    <schedule:SfSchedule.SelectionStyle>
            <schedule:SelectionStyle 
                BackgroundColor="#8490f9"
                BorderColor="Black"
                BorderThickness="5" 
                BorderCornerRadius="5">
            </schedule:SelectionStyle>
    </schedule:SfSchedule.SelectionStyle>
</schedule:SfSchedule> 
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Create new instance of SelectionStyle
SelectionStyle selectionStyle = new SelectionStyle();
selectionStyle.BackgroundColor = Color.FromHex("#8490f9");
selectionStyle.BorderColor = Color.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.BorderCornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %}

![Selection style in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-selection-style.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="TimelineView">
  <schedule:SfSchedule.SelectionView>
	   <Button 
		   BackgroundColor="#FF9800" 
		   Text="+NewEvent" 
		   TextColor="White"/>
  </schedule:SfSchedule.SelectionView>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.TimelineView;
//Add the CustomView
Button customView = new Button();
customView.Text = "+NewEvent";
customView.BackgroundColor = Color.FromHex("#FF9800");
customView.TextColor = Color.White;
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %}

![Custom selection view in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-custom-selection-view.png)

### Programmatic selection
You can programmatically select the specific timeslot by setting corresponding date and time value to [SelectedDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectedDate) property of `SfSchedule`. By default, it is null.

{% tabs %}
{% highlight C# %}
// Setting a date and time to select
schedule.SelectedDate = new DateTime(2017, 10, 04, 10, 0, 0);
{% endhighlight %}
{% endtabs %}

You can clear the selection by setting [SelectedDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectedDate) as null.

{% tabs %}
{% highlight C# %}
// Setting null value to deselect
schedule.SelectedDate = null;
{% endhighlight %}
{% endtabs %}

![Programatic selection in xamarin forms Timeline view](timeline-view-images/xamarin-forms-timeline-view-programatic-selection.png)

>**NOTE**
* `SfSchedule` does not support multiple selection.

## Current time indicator
You can display the current time indicator in `TimelineView` by using the [ShowCurrentTimeIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ShowCurrentTimeIndicator) property.And you can also customize the color of current time indicator by using the [CurrentTimeIndicatorColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_CurrentTimeIndicatorColor) property

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule"
                                     ScheduleView = "TimelineView"
                                     ShowCurrentTimeIndicator="true"
                                     CurrentTimeIndicatorColor="Black">
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.TimelineView;
schedule.ShowCurrentTimeIndicator = true;
schedule.CurrentTimeIndicatorColor = Color.Black;
{% endhighlight %}
{% endtabs %}

## See also

[How to add multiple resource to Schedule (SfSchedule) in Xamarin.Forms](https://www.syncfusion.com/kb/11210/how-to-add-multiple-resource-to-schedule-sfschedule-in-xamarin-forms)

[How to customize time label of schedule in Xamarin.Forms?](https://www.syncfusion.com/kb/10879/how-to-customize-time-label-of-schedule-in-xamarin-forms)

