---

layout: post
title: Customize the Schedule DayView at SfSchedule control for Xamarin.Forms
description: Learn how to Customize the schedule DayView in SfSchedule control
platform: xamarin.Forms
control: SfSchedule
documentation: ug

---


# DayView

DayView is used to display a single day, current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

## ViewHeader Appearance
You can customize the default appearance of view header in [DayView](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleView.html) by using [ViewHeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html) property of [SfSchedule](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule.html).

{% tabs %}
{% highlight c# %}

            //Create new instance of Schedule
			SfSchedule schedule = new SfSchedule();
			schedule.ScheduleView = ScheduleView.DayView;
			//Customize the schedule view header
			ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
			viewHeaderStyle.BackgroundColor = Color.FromHex("#009688");
			viewHeaderStyle.DayTextColor = Color.FromHex("#FFFFFF");
			viewHeaderStyle.DateTextColor = Color.FromHex("#FFFFFF");
			viewHeaderStyle.DayTextStyle = Font.OfSize("Arial", 15);
			viewHeaderStyle.DateTextStyle = Font.OfSize("Arial", 15);
			schedule.ViewHeaderStyle = viewHeaderStyle;
			
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView = "DayView">
        <schedule:SfSchedule.ViewHeaderStyle>
          <schedule:ViewHeaderStyle
              BackgroundColor="#009688" 
              DayTextColor="#FFFFFF" 
              DateTextColor="#FFFFFF" 
              DayTextStyle="Arial,15" 
              DateTextStyle="Arial,15">
        </schedule:ViewHeaderStyle>
     </schedule:SfSchedule.ViewHeaderStyle>
    </schedule:SfSchedule>

{% endhighlight %}
{% endtabs %}

![](daymodule_images/viewheaderappearance_day.png)

>**Note**:  FontAttributes and FontFamily are native to the platform. Custom font and the font which are not available in the specified platform will not be applied.

You can customize the height of the ViewHeader in `DayView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~ViewHeaderHeight.html) property of `SfSchedule`.

{% tabs %}

{% highlight C# %}

    schedule.ScheduleView = ScheduleView.DayView;
	schedule.ViewHeaderHeight = 50;
			
{% endhighlight %}

{% highlight XAML %}

     <schedule:SfSchedule x:Name="schedule" ScheduleView = "DayView"      ViewHeaderHeight="50" >
           
{% endhighlight %}

{% endtabs %}
![](daymodule_images/viewheaderheight_day.png)

## Change Time Interval
You can customize the interval of timeslots in `DayView` by setting [TimeInterval](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~TimeInterval.html)  property of `SfSchedule`.

{% tabs %}
{% highlight C# %}

    schedule.ScheduleView = ScheduleView.DayView;
    schedule.TimeInterval = 120;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule  x:Name="schedule"  ScheduleView="DayView" TimeInterval="120"/> 
{% endhighlight %}
{% endtabs %}

![](daymodule_images/timeinterval_day.png)

## Change Time Interval Height
You can customize the interval height of timeslots in `DayView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~TimeIntervalHeight.html)  property of `SfSchedule`.

{% tabs %}
{% highlight C# %}

    schedule.ScheduleView = ScheduleView.DayView;
    schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule  x:Name="schedule"  ScheduleView="DayView" TimeIntervalHeight="180"/>
{% endhighlight %}
{% endtabs %}

![](daymodule_images/dayview_height.png)

## Change Working hours

Working hours in `DayView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~WorkStartHour.html) and [WorkEndHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~WorkEndHour.html) properties of  [DayViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings.html).

{% tabs %}
{% highlight C# %}

            schedule.ScheduleView = ScheduleView.DayView;
			//Create new instance of DayViewSettings
			DayViewSettings dayViewSettings = new DayViewSettings();
			dayViewSettings.WorkStartHour = 10;
			dayViewSettings.WorkEndHour = 18;
			schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
       <schedule:SfSchedule.DayViewSettings>
                <!--setting working hours properties -->
           <schedule:DayViewSettings 
                WorkStartHour="10" 
                WorkEndHour="18">
           </schedule:DayViewSettings>
       </schedule:SfSchedule.DayViewSettings>
</schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %}
![](daymodule_images/changeworkinghours_day.png)

>**Note**:
`WorkStartHour` and `WorkEndHour` should be in integer value to represent hours.

## Timeslot Appearance
You can customize the appearance of timeslots in `DayView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours

You can customize the appearance of the WorkingHourTimeslot by its color using [TimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~TimeSlotColor.html),[TimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~TimeSlotBorderColor.html) and [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~TimeSlotBorderStrokeWidth.html) properties of `DayViewSettings`.

{% tabs %}
{% highlight C# %}

            schedule.ScheduleView = ScheduleView.DayView;
			//Create new instance of DayViewSettings
			DayViewSettings dayViewSettings = new DayViewSettings();
			dayViewSettings.TimeSlotBorderColor = Color.Aqua;
			dayViewSettings.TimeSlotColor = Color.Yellow;
			dayViewSettings.TimeSlotBorderStrokeWidth = 5;
			schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% highlight XAML %}

     <schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
        <schedule:SfSchedule.DayViewSettings>
         <!--setting Dayview settings properties -->
           <schedule:DayViewSettings
              TimeSlotColor="Yellow"
              TimeSlotBorderColor="Aqua" 
              TimeSlotBorderStrokeWidth="5">
            </schedule:DayViewSettings>
         </schedule:SfSchedule.DayViewSettings>
     </schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %}
![](daymodule_images/timeslotappearance_day.png)

### Timeslot customization in Non Working hours

You can customize the appearance of the Non-workingHourTimeslots by its color using [NonWorkingHoursTimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~NonWorkingHoursTimeSlotBorderColor.html), [NonWorkingHoursTimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~NonWorkingHoursTimeSlotColor.html) properties of `DayViewSettings`.

{% tabs %}

{% highlight C# %}

        schedule.ScheduleView = ScheduleView.DayView;
		//Create new instance of DayViewSettings
		DayViewSettings dayViewSettings = new DayViewSettings();
		dayViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Aqua;
		dayViewSettings.NonWorkingHoursTimeSlotColor = Color.Yellow;
		schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="DayView">
     <schedule:SfSchedule.DayViewSettings>
       <!--setting Day view settings properties -->
         <schedule:DayViewSettings
            NonWorkingHoursTimeSlotColor="Yellow"
            NonWorkingHoursTimeSlotBorderColor="Aqua" 
            TimeSlotBorderStrokeWidth="5">
         </schedule:DayViewSettings>
     </schedule:SfSchedule.DayViewSettings>
    </schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %}
![](daymodule_images/nonworkinghours_day.png)

>**Note**:
`TimeSlotBorderStrokeWidth` property common for both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as non-accessible blocks by using [NonAccessibleBlocks](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~NonAccessibleBlocks.html) of `DayViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}

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
![](daymodule_images/non-accessibleblock_day.png)
>**Note**:
Selection and related events will not be working in this blocks.

## Change first day of week
[FirstDayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~FirstDayOfWeek.html) of `SfSchedule` is not applicable for `DayView` as it displays only one day.

## Time Label Formatting

You can customize the format for the labels which are mentioning the time, by setting [TimeFormat](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayLabelSettings~TimeFormat.html) property of [DayLabelSettings](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayViewSettings~DayLabelSettings.html) in `DayViewSettings`.
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
![](daymodule_images/timelabelformat_day.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.DayLabelSettings~TimeLabelColor.html) property of `DayLabelSettings` in `DayViewSettings`.
{% tabs %}

{% highlight C# %}

            schedule.ScheduleView = ScheduleView.DayView;
			//Create new instance of DayViewSettings
			DayViewSettings dayViewSettings = new DayViewSettings();
			//Create new instance of DayLabelSettings
			DayLabelSettings dayLabelSettings = new DayLabelSettings();
			dayLabelSettings.TimeLabelColor = Color.Blue;
			dayViewSettings.DayLabelSettings = dayLabelSettings;
			schedule.DayViewSettings = dayViewSettings;
{% endhighlight %}
{% endtabs %}
![](daymodule_images/timelabelappearance_day.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectionStyle.html) property of `SfSchedule`.

{% tabs %}
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
{% endtabs %}
![](daymodule_images/selectionstyle_day.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectionView.html) property of `SfSchedule`.

{% tabs %}

{% highlight C# %}

            schedule.ScheduleView = ScheduleView.DayView;
			//Add the CustomView 
			Button customView = new Button();
			customView.Text = "+NewEvent";
			customView.BackgroundColor = Color.FromHex("#FF9800");
			customView.TextColor = Color.White;
			schedule.SelectionView = customView;
{% endhighlight %}

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
{% endtabs %}
![](daymodule_images/selectioncustomview_day.png)

### Programmatic selection
You can programmatically select the specific timeslot by setting corresponding date and time value to [SelectedDate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectedDate.html) property of `SfSchedule`. By default, it is null.

{% highlight C# %}

    // Setting a date and time to select
    schedule.SelectedDate = new DateTime(2017, 08, 02, 10, 0, 0)

{% endhighlight %}

You can clear the selection by setting [SelectedDate](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectedDate.html) as null.

{% highlight C# %}

    // Setting null value to deselect
    schedule.SelectedDate = null

{% endhighlight %}

You can download the entire source code of this demo for Xamarin.Forms from here [Date_Selection](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Date_Selection1072247797.zip)

>**Note**: `SfSchedule` does not support multiple selection.
>**Note**: `SfSchedule` supports two-way binding of `SelectedDate` property.

