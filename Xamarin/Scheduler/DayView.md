---

layout: post
title: Customize DayView at Syncfusion SfSchedule for Xamarin.Forms
description: Learn how to customize the scheduler day view settings and its appearance in SfSchedule control in Xamarin.Forms
platform: xamarin
control: SfSchedule
documentation: ug

---


# Day View in Xamarin Scheduler (SfSchedule)

DayView is used to display a single day, current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

## ViewHeader Appearance
You can customize the default appearance of view header in [DayView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ScheduleView.html) by setting [BackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_BackgroundColor), [DayTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DayTextColor), [DateTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DateTextColor), [DayFontFamily](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DayFontFamily), [DateFontFamily](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DateFontFamily), [CurrentDateTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_CurrentDateTextColor), [CurrentDayTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_CurrentDayTextColor), [DayFontAttributes](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DayFontAttributes) [DateFontAttributes](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DateFontAttributes), [DayFontSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DayFontSize) and [DateFontSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DateFontSize) properties of [ViewHeaderStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html) property in [SfSchedule](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html).

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView = "DayView">
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
schedule.ScheduleView = ScheduleView.DayView;
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

![Schedule day view header appearance](daymodule_images/xamarin.forms.schedule-viewheader-appearance.png)

>**NOTE**
FontAttributes and FontFamily are native to the platform. Custom font and the font which are not available in the specified platform will not be applied.

You can customize the height of the ViewHeader in `DayView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ViewHeaderHeight) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView = "DayView"      ViewHeaderHeight="50" >          
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
schedule.ViewHeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

![Schedule day veiw header](daymodule_images/xamarin.forms-schedule-viewheader-height.png)

### Customize Font Appearance

you can change the appearance of Font by setting the  [DayFontFamily](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DayFontFamilyProperty) and [DateFontFamily](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html#Syncfusion_SfSchedule_XForms_ViewHeaderStyle_DateFontFamilyProperty) property of [ViewHeaderStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ViewHeaderStyle) property in Schedule.

{% tabs %}
{% highlight XAML %}
<schedule:ViewHeaderStyle.DayFontFamily>
  <OnPlatform x:TypeArguments="x:String" iOS="Lobster-Regular" Android="Lobster-Regular.ttf" WinPhone="Assets/Lobster-Regular.ttf#Lobster" />
</schedule:ViewHeaderStyle.DayFontFamily>
<schedule:ViewHeaderStyle.DateFontFamily>
  <OnPlatform x:TypeArguments="x:String" iOS="Lobster-Regular" Android="Lobster-Regular.ttf" WinPhone="Assets/Lobster-Regular.ttf#Lobster" />
</schedule:ViewHeaderStyle.DateFontFamily>
{% endhighlight %}
{% highlight c# %}
viewHeaderStyle.DayFontFamily = Device.OnPlatform("Lobster-Regular", "Lobster-Regular.ttf", "Assets/Lobster-Regular.ttf#Lobster");
viewHeaderStyle.DateFontFamily = Device.OnPlatform("Lobster-Regular", "Lobster-Regular.ttf", "Assets/Lobster-Regular.ttf#Lobster");
{% endhighlight %}
{% endtabs %}

![Schedule view header custom font](daymodule_images/xamarin.forms-schedule-custom-font-view-header.png)

Refer [this](https://help.syncfusion.com/xamarin/sfschedule/monthview#custom-font-setting-in-xamarinforms-android) to configure the custom fonts in Xamarin.Forms.


### ViewHeader Date Format
You can customize the date and day format of `SfSchedule` ViewHeader by using [DateFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayLabelSettings.html#Syncfusion_SfSchedule_XForms_DayLabelSettings_DateFormat) and [DayFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayLabelSettings.html#Syncfusion_SfSchedule_XForms_DayLabelSettings_DayFormat) properties of `DayLabelSettings`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule>
	<schedule:SfSchedule.DayViewSettings>
		<schedule:DayViewSettings>
			<schedule:DayViewSettings.DayLabelSettings>
				<schedule:DayLabelSettings DateFormat=“dd”>
					<schedule:DayLabelSettings.DayFormat>
						<OnPlatform x:TypeArguments="x:String" iOS="EEE d MMMM YY" Android="EEEE" WinPhone="dddd" />
						</schedule:DayLabelSettings.DayFormat>
				</schedule:DayLabelSettings>
			</schedule:DayViewSettings.DayLabelSettings>
		</schedule:DayViewSettings>
	</schedule:SfSchedule.DayViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.DayView;
//Creating new instance of DayViewSettings
DayViewSettings dayViewSettings = new DayViewSettings();
//Creating new instance of DayLabelSettings
DayLabelSettings dayLabelSettings = new DayLabelSettings();
//Customizing date format
dayLabelSettings.DateFormat = "dd";
dayLabelSettings.DayFormat = Device.OnPlatform("EEE d MMMM YY", "EEEE", "dddd");
dayViewSettings.DayLabelSettings = dayLabelSettings;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule viewheader custom date format](daymodule_images/xamarin.forms-schedule-viewheader-dateformat.png)

### ViewHeader Tapped Event
You can handle single tap action of ViewHeader by using [ViewHeaderTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html) event of `SfSchedule`. This event will be triggered when the ViewHeader is Tapped. This event contains [ViewHeaderTappedEventArgs](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderTappedEventArgs.html) argument which holds [DateTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.ViewHeaderTappedEventArgs.html#Syncfusion_SfSchedule_XForms_ViewHeaderTappedEventArgs_DateTime) details in it.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule"
                     ScheduleView="DayView"
                     ViewHeaderTapped="Handle_ViewHeaderTapped" >
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
//Creating  new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.DayView;
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
You can customize the interval of timeslots in `DayView` by setting [TimeInterval](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_TimeInterval)  property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule  x:Name="schedule"  ScheduleView="DayView" TimeInterval="180"/>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
schedule.TimeInterval = 180;
{% endhighlight %}
{% endtabs %}

![Schedule customize time interval day view](daymodule_images/xamarin.forms-schedule-timeinterval.png)

>**NOTE**
If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` value as "hh:mm". By default, TimeFormat value is `"hh a"`. You can refer [here](https://help.syncfusion.com/xamarin/sfschedule/dayview#time-label-formatting) for changing TimeFormat value.

## Change Time Interval Height
You can customize the interval height of timeslots in `DayView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_TimeIntervalHeight)  property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule  x:Name="schedule"  ScheduleView="DayView" TimeIntervalHeight="180"/>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% endtabs %}

![Schedule customize time slot height day view](daymodule_images/xamarin.forms-schedule-timeintervalheight.png)

### Full screen scheduler
Schedule time interval height can be adjusted based on screen height by changing the value of `TimeIntervalHeight` property to -1. It will auto-fit to the screen height and width.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule  x:Name="schedule"  ScheduleView="DayView" TimeIntervalHeight="-1"/>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
schedule.TimeIntervalHeight = -1;
{% endhighlight %}
{% endtabs %}

## Change Working hours

Working hours in `DayView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_WorkEndHour) properties of  [DayViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_DayViewSettings). You can also customize the working hours along with minutes by setting double value which will be converted to time.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
    <schedule:SfSchedule.DayViewSettings>
		<!--setting working hours properties -->
        <schedule:DayViewSettings 
            WorkStartHour="11.5"
            WorkEndHour="17.5">
            <schedule:DayViewSettings.DayLabelSettings>
                <schedule:DayLabelSettings TimeFormat="hh:mm"/>
            </schedule:DayViewSettings.DayLabelSettings>
        </schedule:DayViewSettings>
    </schedule:SfSchedule.DayViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of DayViewSettings
DayViewSettings dayViewSettings = new DayViewSettings();
DayLabelSettings dayLabelSettings = new DayLabelSettings();
dayLabelSettings.TimeFormat = "hh:mm";
dayViewSettings.WorkStartHour = 11.5;
dayViewSettings.WorkEndHour = 14.5;
dayViewSettings.DayLabelSettings = dayLabelSettings;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing working hours day view](daymodule_images/xamarin.forms-schedule-working-hours.png)

>**NOTE**
No need to specify the decimal point values for `WorkStartHour` and `WorkEndHour`, if you don’t want to set the minutes.

## Changing StartHour and EndHour

Default value for [StartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_EndHour) value is 0 to 24 to show all the time slots in `DayView`. You need to set [StartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_EndHour) property of `DayView`, to show only the required time duration for end users. You can also set `StartHour` and `EndHour` in double value which will be converted to time to show required time duration in minutes.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
    <schedule:SfSchedule.DayViewSettings>
        <!--setting working hours properties -->
        <schedule:DayViewSettings
            StartHour=“7.5”
            EndHour="18.5”>
            <schedule:DayViewSettings.DayLabelSettings>
                <schedule:DayLabelSettings TimeFormat="hh:mm" />
            </schedule:DayViewSettings.DayLabelSettings>
        </schedule:DayViewSettings>
    </schedule:SfSchedule.DayViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of DayViewSettings
DayViewSettings dayViewSettings = new DayViewSettings();
DayLabelSettings dayLabelSettings = new DayLabelSettings();
dayLabelSettings.TimeFormat = "hh:mm";
dayViewSettings.StartHour = 7.5;
dayViewSettings.EndHour = 18.5;
dayViewSettings.DayLabelSettings = dayLabelSettings;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing start and end hour day view](daymodule_images/xamarin.forms-schedule-starthour-endhour.png)

>**NOTE**
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `InvalidDataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException` will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If custom `TimeInterval` is given, then the number of time slots calculated based on given `TimeInterval` should result in integer value (total minutes % `TimeInterval` = 0), otherwise next immediate time interval that result in integer value when divide total minutes of a day will be considered. For example, if `TimeInterval`="135” (2 Hours 15 minutes) and total minutes = 1440 (24 Hours per day), then `TimeInterval` will be changed to "144” (1440%144=0) by considering (total minutes % `TimeInterval` = 0); it will return integer value for time slots rendering.
* If the custom `StartHour` and `EndHour` are given, then the number of time slots calculated based on given `StartHour` and `EndHour` should result in integer value, otherwise next immediate time interval will be considered until the result is integer value. For example, if `StartHour` is 9 (09:00AM), `EndHour` is 18.25 (06:15 PM), `TimeInterval` is 30 minutes, and total minutes = 555 ((18.25-9)*60), then the `TimeInterval` will be changed to "37” (555%37=0) by considering (total minutes % `TimeInterval` = 0); it will return integer value for time slots rendering.

## Timeslot Appearance
You can customize the appearance of timeslots in `DayView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours

You can customize the appearance of the WorkingHourTimeslot by its color using [TimeSlotColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_TimeSlotColor),[TimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_TimeSlotBorderColor), [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_TimeSlotBorderStrokeWidth), [VerticalLineColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_VerticalLineColor) and [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_VerticalLineStrokeWidth) properties of `DayViewSettings`.

{% tabs %}
{% highlight XAML %}

<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
    <schedule:SfSchedule.DayViewSettings>
     <!--setting DayView settings properties -->
       <schedule:DayViewSettings
          TimeSlotColor="#fcf3c9"
          TimeSlotBorderColor="#fceb9f"
          TimeSlotBorderStrokeWidth="5"
		  VerticalLineColor="LightGray"
          VerticalLineStrokeWidth="5">
        </schedule:DayViewSettings>
     </schedule:SfSchedule.DayViewSettings>
 </schedule:SfSchedule>
 
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of DayViewSettings
DayViewSettings dayViewSettings = new DayViewSettings();
dayViewSettings.TimeSlotBorderColor = Color.FromHex("#fceb9f");
dayViewSettings.TimeSlotColor = Color.FromHex("#fcf3c9");
dayViewSettings.TimeSlotBorderStrokeWidth = 5;
dayViewSettings.VerticalLineColor = Color.LightGray;
dayViewSettings.VerticalLineStrokeWidth = 5;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}
![Schedule customizing time slot appearance day view](daymodule_images/xamarin.forms-schedule-timeslot-appearance.png)

### Timeslot customization in Non Working hours

You can customize the appearance of the Non-workingHourTimeslots by its color using [NonWorkingHoursTimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_NonWorkingHoursTimeSlotBorderColor), [NonWorkingHoursTimeSlotColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_NonWorkingHoursTimeSlotColor), [VerticalLineColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_VerticalLineColor) and [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_VerticalLineStrokeWidth) properties of `DayViewSettings`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
 <schedule:SfSchedule.DayViewSettings>
   <!--setting Day view settings properties -->
	 <schedule:DayViewSettings
		NonWorkingHoursTimeSlotColor="#fcf3c9"
		NonWorkingHoursTimeSlotBorderColor="#fceb9f"
		TimeSlotBorderStrokeWidth="5"
		VerticalLineColor="LightGray"
        VerticalLineStrokeWidth="5">
	 </schedule:DayViewSettings>
 </schedule:SfSchedule.DayViewSettings>
</schedule:SfSchedule> 
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of DayViewSettings
DayViewSettings dayViewSettings = new DayViewSettings();
dayViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.FromHex("#fceb9f");
dayViewSettings.NonWorkingHoursTimeSlotColor = Color.FromHex("#fcf3c9");
dayViewSettings.TimeSlotBorderStrokeWidth = 5;
dayViewSettings.VerticalLineColor = Color.LightGray;
dayViewSettings.VerticalLineStrokeWidth = 5;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}
![Schedule non working hours day view](daymodule_images/xamarin.forms-schedule-nonworking-hours.png)

>**NOTE**
`TimeSlotBorderStrokeWidth`, `VerticalLineColor` and `VerticalLineStrokeWidth` properties common for both Working hours and Non-Working hour time slot customization.
`VerticalLineColor` and `VerticalLineStrokeWidth` properties applicable for Android only in `DayView`.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as non-accessible blocks by using [NonAccessibleBlocks](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_NonAccessibleBlocks) of `DayViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour using [StartTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.NonAccessibleBlock.html#Syncfusion_SfSchedule_XForms_NonAccessibleBlock_StartTime), [EndTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.NonAccessibleBlock.html#Syncfusion_SfSchedule_XForms_NonAccessibleBlock_EndTime), [Text](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.NonAccessibleBlock.html#Syncfusion_SfSchedule_XForms_NonAccessibleBlock_Text) and [Color](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.NonAccessibleBlock.html#Syncfusion_SfSchedule_XForms_NonAccessibleBlock_Color) properties of `NonAccessibleBlocks`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
	<!--setting non-accessing blocks-->
	<schedule:SfSchedule.DayViewSettings>
		<schedule:DayViewSettings>
			<schedule:DayViewSettings.NonAccessibleBlocks>
				<schedule:NonAccessibleBlock 
					 StartTime="13"
					 EndTime="14" 
					 Text="LUNCH" 
					 Color="Black" />
			</schedule:DayViewSettings.NonAccessibleBlocks>
		</schedule:DayViewSettings>
	</schedule:SfSchedule.DayViewSettings>
</schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of NonAccessibleBlock
NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock();
//Create new instance of NonAccessibleBlocksCollection
NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
DayViewSettings dayViewSettings = new DayViewSettings();
nonAccessibleBlock.StartTime = 13;
nonAccessibleBlock.EndTime = 14;
nonAccessibleBlock.Text = "LUNCH";
nonAccessibleBlock.Color = Color.Black;
nonAccessibleBlocksCollection.Add(nonAccessibleBlock);
dayViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}

![Schedule non accessible block day view](daymodule_images/xamarin.forms-schedule-nonaccessible-block.png)

>**NOTE**
Selection and related events will not be working in this blocks.

## Change first day of week
[FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_FirstDayOfWeek) of `SfSchedule` is not applicable for `DayView` as it displays only one day.

## Time Label Formatting

You can customize the format for the labels which are mentioning the time, by setting [TimeFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayLabelSettings.html#Syncfusion_SfSchedule_XForms_DayLabelSettings_TimeFormat) property of [DayLabelSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_DayLabelSettings) in `DayViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
DayViewSettings dayViewSettings = new DayViewSettings();
DayLabelSettings dayLabelSettings = new DayLabelSettings();
dayLabelSettings.TimeFormat = "hh mm";
dayViewSettings.DayLabelSettings = dayLabelSettings;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing time label day view](daymodule_images/xamarin.forms-schedule-timelabel-format.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayLabelSettings.html#Syncfusion_SfSchedule_XForms_DayLabelSettings_TimeLabelColor) property of `DayLabelSettings` in `DayViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of DayViewSettings
DayViewSettings dayViewSettings = new DayViewSettings();
//Create new instance of DayLabelSettings
DayLabelSettings dayLabelSettings = new DayLabelSettings();
dayLabelSettings.TimeLabelColor = Color.FromHex("#8282ff");
dayViewSettings.DayLabelSettings = dayLabelSettings;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule customizing time label appearance day view](daymodule_images/xamarin.forms-schedule-timelabel-appearance.png)

## Time Label Size

You can customize the size of the labels which are mentioning the time, by setting [TimeLabelSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayLabelSettings.html#Syncfusion_SfSchedule_XForms_DayLabelSettings_TimeLabelSize) property of `DayLabelSettings` in `DayViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of DayViewSettings
DayViewSettings dayViewSettings = new DayViewSettings();
//Create new instance of DayLabelSettings
DayLabelSettings dayLabelSettings = new DayLabelSettings();
//Customizing the size of the time label
dayLabelSettings.TimeLabelSize = 15;
dayViewSettings.DayLabelSettings = dayLabelSettings;
schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule cusotomizing time label size day view](daymodule_images/xamarin.forms-schedule-timelabel-size.png)

## Time ruler size customization

You can customize the size of time ruler in `DayView` by setting the [TimeRulerSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_TimeRulerSize) property in `DayViewSettings`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
     <schedule:SfSchedule.DayViewSettings>
          <schedule:DayViewSettings TimeRulerSize="0"/>
     </schedule:SfSchedule.DayViewSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
DayViewSettings dayViewSettings = new DayViewSettings();
dayViewSettings.TimeRulerSize = 0;
schedule.dayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}

![Schedule cusotomizing time ruler size day view](daymodule_images/xamarin.forms-schedule-dayview-timerulersizecustomization.jpg)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)
* [Programmatic selection](#programmatic-selection)

### Selection customization using style
You can customize the timeslot selection by by setting the [BackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SelectionStyle.html#Syncfusion_SfSchedule_XForms_SelectionStyle_BackgroundColor), [BorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SelectionStyle.html#Syncfusion_SfSchedule_XForms_SelectionStyle_BorderColor), [BorderThickness](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SelectionStyle.html#Syncfusion_SfSchedule_XForms_SelectionStyle_BorderThickness), [BorderCornerRadius](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SelectionStyle.html#Syncfusion_SfSchedule_XForms_SelectionStyle_BorderCornerRadius) properties to the [SelectionStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectionStyle) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
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
schedule.ScheduleView = ScheduleView.DayView;
//Create new instance of SelectionStyle
SelectionStyle selectionStyle = new SelectionStyle();
selectionStyle.BackgroundColor = Color.Blue;
selectionStyle.BorderColor = Color.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.BorderCornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %}

![Schedule customizing selectin style day view](daymodule_images/xamarin.forms-schedule-selection-style.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
	<schedule:SfSchedule.SelectionView>
		<Button 
		   BackgroundColor="#FF9800"
		   Text="+NewEvent" 
		   TextColor="White"/>
	</schedule:SfSchedule.SelectionView>
</schedule:SfSchedule> 
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
//Add the CustomView
Button customView = new Button();
customView.Text = "+NewEvent";
customView.BackgroundColor = Color.FromHex("#FF9800");
customView.TextColor = Color.White;
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %}

![Schedule customizing selection view day view](daymodule_images/xamarin.forms-schedule-selection-customview.png)

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

![Schedule customizing selection day view](daymodule_images/xamarin.forms-schedule-selection.png)

## Current time indicator
You can display the current time indicator in DayView by using the [ShowCurrentTimeIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_ShowCurrentTimeIndicator) property. And you can also customize the color of current time indicator by using the [CurrentTimeIndicatorColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_CurrentTimeIndicatorColor) property.

{% tabs %}
{% highlight XAML %}
<schedule:SfSchedule x:Name="schedule"
                                     ScheduleView = "DayView"
                                     ShowCurrentTimeIndicator="true"
                                     CurrentTimeIndicatorColor="Black">
</schedule:SfSchedule>
{% endhighlight %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.DayView;
schedule.ShowCurrentTimeIndicator = true;
scheduleCurrentTimeIndicatorColor = Color.Black;
{% endhighlight %}
{% endtabs %}

## See also

[How to get date and appointment details while tapping view header ?](https://www.syncfusion.com/kb/6203/how-to-get-date-and-appointment-details-while-tapping-view-header)
