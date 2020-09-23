---

layout: post
title: Customize WorkWeekView at Syncfusion SfSchedule for Xamarin.Forms
description: Learn how to customize the scheduler work week view settings and its appearance in SfSchedule control in Xamarin.Forms
platform: xamarin
control: SfSchedule
documentation: ug

---


# Work Week View in Xamarin Scheduler (SfSchedule)

WorkWeekView is to view only working days of a particular week. By default, Saturday and Sunday are the non-working days. You can be customize it with any days of a Week. Appointments arranged in timeslots based on its duration with respective day of the week.


## ViewHeader Appearance
You can customize the default appearance of view header in [WorkWeekView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ScheduleView.html) by using [ViewHeaderStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html) property of [SfSchedule](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html).

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView ="WorkWeekView">
 <schedule:SfSchedule.ViewHeaderStyle>
	 <schedule:ViewHeaderStyle
		BackgroundColor="#009688" 
		DayTextColor="#FFFFFF" 
		DateTextColor="#FFFFFF" 
		DayFontFamily="Arial" 
		DateFontFamily="Arial">
	 </schedule:ViewHeaderStyle>
  </schedule:SfSchedule.ViewHeaderStyle>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
//Create new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Customize the schedule view header
ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
viewHeaderStyle.BackgroundColor = Color.FromHex("#009688");
viewHeaderStyle.DayTextColor = Color.FromHex("#FFFFFF");
viewHeaderStyle.DateTextColor = Color.FromHex("#FFFFFF");
viewHeaderStyle.DayFontFamily = "Arial";
viewHeaderStyle.DateFontFamily = "Arial";
schedule.ViewHeaderStyle = viewHeaderStyle;
{% endhighlight %}
{% endtabs %} 

![Schedule view header appearance work week view](workweekview_images/xamarin.forms.schedule-viewheader-appearance.png)

>**NOTE**
FontAttributes and FontFamily are native to the platform. Custom font and the font which are not available in the specified platform will not be applied.

You can customize the height of the ViewHeader in `WeekView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ViewHeaderHeight) property of `SfSchedule`.

{% tabs %} 
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.ViewHeaderHeight = 50;		
{% endhighlight %}

{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView ="WorkWeekView" ViewHeaderHeight="50" />     
{% endhighlight %}
{% endtabs %}

![Schedule view header height work week view](workweekview_images/xamarin.forms-schedule-viewheader-height.png)

### Customize Font Appearance

you can change the appearance of Font by setting the  [DayFontFamily](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DayFontFamilyProperty) and [DateFontFamily](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DateFontFamilyProperty) property of [ViewHeaderStyle](https://help.syncfusion.com/xamarin/sfschedule/dayview#viewheader-appearance) property in Schedule.

{% tabs %}
{% highlight XAML %}
<schedule:ViewHeaderStyle.DayFontFamily>
		<OnPlatform x:TypeArguments="x:String" iOS="Lobster-Regular" Android="Lobster-Regular.ttf" WinPhone="Assets/Lobster-Regular.ttf#Lobster" />
</schedule:HeaderStyle.DayFontFamily>
<schedule:ViewHeaderStyle.DateFontFamily>
		<OnPlatform x:TypeArguments="x:String" iOS="Lobster-Regular" Android="Lobster-Regular.ttf" WinPhone="Assets/Lobster-Regular.ttf#Lobster" />
</schedule:HeaderStyle.DateFontFamily>
{% endhighlight %}
{% highlight c# %}
viewHeaderStyle.DayFontFamily = Device.OnPlatform("Lobster-Regular", "Lobster-Regular.ttf", "Assets/Lobster-Regular.ttf#Lobster");
viewHeaderStyle.DateFontFamily = Device.OnPlatform("Lobster-Regular", "Lobster-Regular.ttf", "Assets/Lobster-Regular.ttf#Lobster");
{% endhighlight %}
{% endtabs %} 

![Schedule customizing view header work week view](workweekview_images/xamarin.forms-schedule-custom-font-view-header.png)

Refer [this](https://help.syncfusion.com/xamarin/sfschedule/monthview#custom-font-setting-in-xamarinforms-android) to configure the custom fonts in Xamarin.Forms.

### ViewHeader Date Format
You can customize the date and day format of `SfSchedule` ViewHeader by using [DateFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekLabelSettings_DateFormat) and [DayFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekLabelSettings_DayFormat) properties of `WorkWeekLabelSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule>
	<schedule:SfSchedule.WorkWeekViewSettings>
		<schedule:WorkWeekViewSettings>
			<schedule:WorkWeekViewSettings.WorkWeekLabelSettings>
				<schedule:WorkWeekLabelSettings DateFormat=“dd”>
					<schedule:WorkWeekLabelSettings.DayFormat>
						<OnPlatform x:TypeArguments="x:String" iOS="EEEE" Android="EEEE" WinPhone="dddd" />
					</schedule:WorkWeekLabelSettings.DayFormat>
				</schedule:WorkWeekLabelSettings>
			</schedule:WorkWeekViewSettings.WorkWeekLabelSettings>
		</schedule:WorkWeekViewSettings>
	</schedule:SfSchedule.WorkWeekViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Creating new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
//Creating new instance of WorkWeekLabelSettings
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
//Customizing date format
workWeekLabelSettings.DateFormat = "dd";
workWeekLabelSettings.DayFormat = Device.OnPlatform("EEEE", "EEEE", "dddd");
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing date format work week view](workweekview_images/xamarin.forms-schedule-viewheader-dateformat.png)

### ViewHeader Tapped Event
You can handle single tap action of ViewHeader by using [ViewHeaderTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html) event of `SfSchedule`. This event will be triggered when the ViewHeader is Tapped. This event contains [ViewHeaderTappedEventArgs](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderTappedEventArgs.html) argument which holds [DateTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderTappedEventArgs.html#Syncfusion_SfSchedule_XForms_ViewHeaderTappedEventArgs_DateTime) details in it.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule"
                     ScheduleView="WorkWeekView"
                     ViewHeaderTapped="Handle_ViewHeaderTapped" >
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
//Creating  new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.ViewHeaderTapped += Handle_ViewHeaderTapped;
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
private void Handle_ViewHeaderTapped(object sender, ViewHeaderTappedEventArgs e)
{
    var dateTime = e.DateTime;
}
{% endhighlight %}
{% endtabs %}

## Change Time Interval
You can customize the interval of timeslots in `WorkWeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_TimeInterval)  property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView" TimeInterval="180"/>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.TimeInterval = 180;
{% endhighlight %}
{% endtabs %} 

![Schedule customizing time interval work week view](workweekview_images/xamarin.forms-schedule-timeinterval.png)

>**NOTE**
If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` value as "hh:mm". By default, TimeFormat value is `"hh a"`. You can refer [here](https://help.syncfusion.com/xamarin/sfschedule/workweekview#time-label-formatting) for changing TimeFormat value.

## Change Time Interval Height
You can customize the interval height of timeslots in `WorkWeekView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_TimeIntervalHeight)  property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule  x:Name="schedule"  ScheduleView="WorkWeekView" TimeIntervalHeight="180"/>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% endtabs %}

![Schedule customizing time interval height work week view](workweekview_images/xamarin.forms-schedule-timeintervalheight.png)

### Full screen scheduler
Schedule time interval height can be adjusted based on screen height by changing the value of `TimeIntervalHeight` property to -1. It will auto-fit to the screen height and width.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule  x:Name="schedule"  ScheduleView="WorkWeekView" TimeIntervalHeight="-1"/>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.TimeIntervalHeight = -1;
{% endhighlight %}
{% endtabs %}

## Change Working hours

Working hours in `WorkWeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_WorkEndHour) properties of [WorkWeekViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_WorkWeekViewSettings). You can also customize the working hours along with minutes by setting double value which will be converted to time.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
    <schedule:SfSchedule.WorkWeekViewSettings>
        <!--setting working hours properties -->
        <schedule:WorkWeekViewSettings
            WorkStartHour="11.5"
            WorkEndHour="17.5">
            <schedule:WorkWeekViewSettings.WorkWeekLabelSettings>
                <schedule:WorkWeekLabelSettings TimeFormat="hh:mm" />
            </schedule:WorkWeekViewSettings.WorkWeekLabelSettings>
        </schedule:WorkWeekViewSettings>
    </schedule:SfSchedule.WorkWeekViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeFormat = "hh:mm";
workWeekViewSettings.WorkStartHour = 11.5;
workWeekViewSettings.WorkEndHour = 14.5;
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing working hours work week view](workweekview_images/xamarin.forms-schedule-working-hours.png)

>**NOTE**
No need to specify the decimal point values for `WorkStartHour` and `WorkEndHour`, if you don’t want to set the minutes.

## Changing StartHour and EndHour

Default value for [StartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_EndHour) value is 0 to 24 to show all the time slots in `WorkWeekView`. You need to set [StartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_EndHour) property of 'WorkWeekView', to show only the required time duration for end users. You can also set `StartHour` and `EndHour` in double value which will be converted to time to show required time duration in minutes.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
    <schedule:SfSchedule.WorkWeekViewSettings>
        <!--setting working hours properties -->
        <schedule:WorkWeekViewSettings
                StartHour =”7.5”
                EndHour =”18.5”>
        </schedule:WorkWeekViewSettings>
        <schedule:WorkWeekViewSettings.WorkWeekLabelSettings>
            <schedule:WorkWeekLabelSettings TimeFormat="hh:mm" />
        </schedule:WorkWeekViewSettings.WorkWeekLabelSettings>
    </schedule:SfSchedule.WorkWeekViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeFormat = "hh:mm";
workWeekViewSettings.StartHour = 7.5;
workWeekViewSettings.EndHour = 18.5;
workWeekViewSettings.WeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing start and end hour work week view](workweekview_images/xamarin.forms-schedule-starthour-endhour.png)

>**NOTE**
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `InvalidDataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException` will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If custom `TimeInterval` is given, then the number of time slots calculated based on given `TimeInterval` should result in integer value (total minutes % `TimeInterval` = 0), otherwise next immediate time interval that result in integer value when divide total minutes of a day will be considered. For example, if `TimeInterval`="135” (2 Hours 15 minutes) and total minutes = 1440 (24 Hours per day), then `TimeInterval` will be changed to "144” (1440%144=0) by considering (total minutes % `TimeInterval` = 0); it will return integer value for time slots rendering.
* If the custom `StartHour` and `EndHour` are given, then the number of time slots calculated based on given `StartHour` and `EndHour` should result in integer value, otherwise next immediate time interval will be considered until the result is integer value. For example, if `StartHour` is 9 (09:00AM), `EndHour` is 18.25 (06:15 PM), `TimeInterval` is 30 minutes, and total minutes = 555 ((18.25-9)*60), then the `TimeInterval` will be changed to "37” (555%37=0) by considering (total minutes % `TimeInterval` = 0); it will return integer value for time slots rendering.

## Changing NonWorking Days
You can customize the Non-Working days of a week by using [NonWorkingsDays](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_NonWorkingsDays) property of `WorkWeekViewSettings`.
{% tabs %}
{% highlight C# %}
var nonWorkingDays = new ObservableCollection<DayOfWeek>();
nonWorkingDays.Add(DayOfWeek.Monday);
nonWorkingDays.Add(DayOfWeek.Friday);
var workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.NonWorkingsDays = nonWorkingDays;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}


## Timeslot Appearance
You can customize the appearance of timeslots in `WeekView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours

You can customize the appearance of the working hour timeslots by its color using[TimeSlotColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_TimeSlotColor), [TimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_TimeSlotBorderColor), [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_VerticalLineStrokeWidth),  [VerticalLineColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_VerticalLineColor) and  [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_TimeSlotBorderStrokeWidth) properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
	<schedule:SfSchedule.WorkWeekViewSettings>
	<!--setting work week view settings properties -->
		<schedule:WorkWeekViewSettings
			TimeSlotColor="#fcf3c9"
			TimeSlotBorderColor="#fceb9f"
			TimeSlotBorderStrokeWidth="5"
			VerticalLineStrokeWidth="5" 
			VerticalLineColor="LightGray">
		</schedule:WorkWeekViewSettings>
	</schedule:SfSchedule.WorkWeekViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.TimeSlotBorderColor = Color.FromHex("#fceb9f") ;
workWeekViewSettings.VerticalLineColor = Color.LightGray;
workWeekViewSettings.TimeSlotColor = Color.FromHex("#fcf3c9");
workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
workWeekViewSettings.VerticalLineStrokeWidth = 5;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %} 

![Schedule customizing time slot appearance work week view](workweekview_images/xamarin.forms-schedule-timeslot-appearance.png)

### Timeslot customization in Non Working hours

You can customize the appearance of the non-working hour timeslots by its color using [NonWorkingHoursTimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_NonWorkingHoursTimeSlotBorderColor),[NonWorkingHoursTimeSlotColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_NonWorkingHoursTimeSlotColor),`VerticalLineStrokeWidth`, `VerticalLineColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
	<schedule:SfSchedule.WorkWeekViewSettings>
	<!--setting work week view settings properties -->
		<schedule:WorkWeekViewSettings
			NonWorkingHoursTimeSlotColor="#fcf3c9"
			NonWorkingHoursTimeSlotBorderColor="#fceb9f"
			TimeSlotBorderStrokeWidth="5"
			VerticalLineStrokeWidth="5" 
			VerticalLineColor="LightGray">
		</schedule:WorkWeekViewSettings>
	</schedule:SfSchedule.WorkWeekViewSettings>
</schedule:SfSchedule> 
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.FromHex("#fceb9f") ;
workWeekViewSettings.VerticalLineColor = Color.LightGray;
workWeekViewSettings.NonWorkingHoursTimeSlotColor = Color.FromHex("#fcf3c9");
workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
workWeekViewSettings.VerticalLineStrokeWidth = 5;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %} 

![Schedule non working hours work week view](workweekview_images/xamarin.forms-schedule-nonworking-hours.png)

>**NOTE**
`TimeSlotBorderStrokeWidth`and ` VerticalLineStrokeWidth` properties are common to both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as Non-accessible blocks by using [NonAccessibleBlocks](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_NonAccessibleBlocks) of `WorkWeekViewSettings` so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
    <!--setting non-accessing blocks-->
    <schedule:SfSchedule.WorkWeekViewSettings>
        <schedule:WorkWeekViewSettings>
            <schedule:WorkWeekViewSettings.NonAccessibleBlocks>
                <schedule:NonAccessibleBlock
                    StartTime="13"
                    EndTime="14"
                    Text="LUNCH"
                    Color="Black" />
            </schedule:WorkWeekViewSettings.NonAccessibleBlocks>
        </schedule:WorkWeekViewSettings>
    </schedule:SfSchedule.WorkWeekViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of NonAccessibleBlock
NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock();
//Create new instance of NonAccessibleBlocksCollection
NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
nonAccessibleBlock.StartTime = 13;
nonAccessibleBlock.EndTime = 14;
nonAccessibleBlock.Text = "LUNCH";
nonAccessibleBlock.Color = Color.Black;
nonAccessibleBlocksCollection.Add(nonAccessibleBlock);
workWeekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %} 

![Schedule non accessible block work week view](workweekview_images/xamarin.forms-schedule-nonaccessible-block.png)

>**NOTE**
Selection and related events will not be working in this blocks.

## Change first day of week
By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using[FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_FirstDayOfWeek) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView" FirstDayOfWeek="3"/>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.FirstDayOfWeek = 3;
{% endhighlight %}
{% endtabs %} 

![Schedule first day of week work week view](workweekview_images/xamarin.forms.schedule-firstday-of-week.png)

## Time Label Formatting

You can customize the format for the labels which are mentioning the time, by setting [TimeFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekLabelSettings_TimeFormat) property of [WorkWeekLabelSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_WorkWeekLabelSettings) in `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
WorkWeekViewSettings workweekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeFormat = "hh mm";
workweekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workweekViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule time label format work week view](workweekview_images/xamarin.forms-schedule-timelabel-format.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekLabelSettings_TimeLabelColor) property of `WorkWeekLabelSettings` in `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
//Create new instance of WorkWeekLabelSettings
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeLabelColor = Color.FromHex("#8282ff");
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing time label appearence work week view](workweekview_images/xamarin.forms-schedule-timelabel-appearance.png)

## Time Label Size

You can customize the size of the labels which are mentioning the time, by setting [TimeLabelSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekLabelSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekLabelSettings_TimeLabelSize) property of `WorkWeekLabelSettings` in `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
//Create new instance of WorkWeekLabelSettings
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
//Customizing the size of the time label
workWeekLabelSettings.TimeLabelSize = 15;
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizint time label size work week view](workweekview_images/xamarin.forms-schedule-timelabel-size.png)

## Time ruler size customization

You can customize the size of time ruler in `WorkWeekView` by setting the [TimeRulerSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.WorkWeekViewSettings.html#Syncfusion_SfSchedule_XForms_WorkWeekViewSettings_TimeRulerSize) property in `WorkWeekViewSettings`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
   <schedule:SfSchedule.WorkWeekViewSettings>
        <schedule:WorkWeekViewSettings TimeRulerSize="0"/>
   </schedule:SfSchedule.WorkWeekViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.TimeRulerSize = 0;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customization of time ruler size work week view](workweekview_images/xamarin.forms-schedule-workweekview-timerulersizecustomization.jpg)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)
* [Programmatic selection](#programmatic-selection)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectionStyle) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
		<schedule:SfSchedule.SelectionStyle>
			<schedule:SelectionStyle 
			   BackgroundColor="Blue" 
			   BorderColor="Black" 
			   BorderThickness="5" 
			   BorderCornerRadius="5">
			</schedule:SelectionStyle>
		</schedule:SfSchedule.SelectionStyle>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of SelectionStyle
SelectionStyle selectionStyle = new SelectionStyle();
selectionStyle.BackgroundColor = Color.Blue;
selectionStyle.BorderColor = Color.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.BorderCornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %} 

![Schedule customizing selection style work week view](workweekview_images/xamarin.forms-schedule-selection-style.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
	<schedule:SfSchedule.SelectionView>
	  <Button
		  BackgroundColor="#FF9800" 
		  Text="+NewEvent" 
		  TextColor="White"/>
	</schedule:SfSchedule.SelectionView>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Add the CustomView
Button customView = new Button();
customView.Text = "+NewEvent";
customView.BackgroundColor = Color.FromHex("#FF9800");
customView.TextColor = Color.White;
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %} 

![Schedule cusotmizing selection view in work week view](workweekview_images/xamarin.forms-schedule-selection-customview.png)

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

You can download the entire source code of this demo for Xamarin.Forms from here [Date_Selection](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Date_Selection1072247797.zip)

>**NOTE**
* `SfSchedule` does not support multiple selection.
* `SfSchedule` supports two-way binding of `SelectedDate` property.

![Schedule customizing selection work week view](workweekview_images/xamarin.forms-schedule-selection.png)

## Current time indicator
You can display the current time indicator in `WorkWeekView` by using the [ShowCurrentTimeIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ShowCurrentTimeIndicator) property.And you can also customize the color of current time indicator by using the [CurrentTimeIndicatorColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_CurrentTimeIndicatorColor) property

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule"
                                     ScheduleView = "WorkWeekView"
                                     ShowCurrentTimeIndicator="true"
                                     CurrentTimeIndicatorColor="Black">
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.ShowCurrentTimeIndicator = true;
schedule.CurrentTimeIndicatorColor = Color.Black;
{% endhighlight %}
{% endtabs %}

