---

layout: post
title: Customize the Schedule WeekView at SfSchedule control for Xamarin.Forms
description: Learn how to Customize the schedule WeekView in SfSchedule control
platform: xamarin.Forms
control: SfSchedule
documentation: ug

---


# WeekView

WeekView is to view all days of a particular week. Appointments will be arranged based on the dates on the week in respective timeslots.

## ViewHeader Appearance:
You can customize the default appearance of view header in [WeekView](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleView.html) by using [ViewHeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html) property of [SfSchedule](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule.html).

{% tabs %}

{% highlight c# %}

            //Create new instance of Schedule
			SfSchedule schedule = new SfSchedule();
			schedule.ScheduleView = ScheduleView.WeekView;
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

    <schedule:SfSchedule x:Name="schedule" ScheduleView ="WeekView">
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

![](daymodule_images/viewheader_appearance_week.png)

>**Note**:  FontAttributes and FontFamily are native to the platform. Custom font and the font which are not available in the specified platform will not be applied.
    
You can customize the height of the ViewHeader in `WeekView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~ViewHeaderHeight.html) property of `SfSchedule`.

{% tabs %}

{% highlight C# %}

        schedule.ScheduleView = ScheduleView.WeekView;
		schedule.ViewHeaderHeight = 50;
			
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView ="WeekView"           ViewHeaderHeight="50" /> 
           
{% endhighlight %}
{% endtabs %}
![](daymodule_images/viewheaderheight_week.png)

## Change Time Interval
You can customize the interval of timeslots in `WeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~TimeInterval.html)  property of `SfSchedule`.

{% tabs %}

{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WeekView;
	schedule.TimeInterval = 120;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView" TimeInterval="120"/> 
{% endhighlight %}
{% endtabs %}
![](daymodule_images/timeinterval_week.png)

## Change Time Interval Height
You can customize the interval height of timeslots in `WeekView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~TimeIntervalHeight.html)  property of `SfSchedule`.

{% tabs %}
{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WeekView;
    schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule  x:Name="schedule"  ScheduleView="WeekView" TimeIntervalHeight="180"/>
{% endhighlight %}
{% endtabs %}

![](daymodule_images/weekview_height.png)

## Change Working hours

You can hide the time slots by setting [StartHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~StartHour.html) and [EndHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~EndHour.html) properties of [WeekViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~WeekViewSettings.html). Default value for StartHour and EndHour will be 0 to 24 hours. 
Working hours in `WeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~WorkStartHour.html) and [WorkEndHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~WorkEndHour.html) properties of   [WeekViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~WeekViewSettings.html).

{% tabs %}

{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WeekView;
			//Create new instance of WeekViewSettings
			WeekViewSettings weekViewSettings = new WeekViewSettings();
			weekViewSettings.StartHour = 08;
			weekViewSettings.EndHour = 15;
			weekViewSettings.WorkStartHour = 09;
			weekViewSettings.WorkEndHour = 16;
			schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
         <schedule:SfSchedule.WeekViewSettings>
                <!--setting working hours properties -->
                <schedule:WeekViewSettings 
				     WorkStartHour="08" 
                     WorkEndHour="15"
                     WorkStartHour="09" 
                     WorkEndHour="16">
                </schedule:WeekViewSettings>
          </schedule:SfSchedule.WeekViewSettings>
    </schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %}
![](daymodule_images/changeworkinghours_week.png)

>**Note**:
•	`WorkStartHour` and `WorkEndHour` should be in integer value to represent hours.
•	`StartHour` must be greater than 0 and `EndHour` must be lesser than 24, otherwise exception will thrown.
•	`EndHour` value must be greater than `StartHour`, otherwise exception will thrown.
•	 Before `StartHour` and after `EndHour` values, Schedule UI such as Appointments and NonAccessibleBlocks will be clipped.

## Timeslot Appearance:
You can customize the appearance of timeslots in `WeekView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours

You can customize the appearance of the working hour timeslots by its color using[TimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~TimeSlotColor.html) ,[TimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~TimeSlotBorderColor.html), [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~VerticalLineStrokeWidth.html), [VerticalLineColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~VerticalLineColor.html) and [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~TimeSlotBorderStrokeWidth.html) properties of`WeekViewSettings`.

{% tabs %}

{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WeekView;
			//Create new instance of WeekViewSettings
			WeekViewSettings weekViewSettings = new WeekViewSettings();
			weekViewSettings.TimeSlotBorderColor = Color.Aqua;
			weekViewSettings.VerticalLineColor = Color.Blue;
			weekViewSettings.TimeSlotColor = Color.Yellow;
			weekViewSettings.TimeSlotBorderStrokeWidth = 5;
			weekViewSettings.VerticalLineStrokeWidth = 5;
			schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
      <schedule:SfSchedule.WeekViewSettings>
        <!--setting week view settings properties -->
         <schedule:WeekViewSettings
             TimeSlotColor="Yellow"
             TimeSlotBorderColor="Aqua" 
             TimeSlotBorderStrokeWidth="5"
             VerticalLineStrokeWidth="5" 
             VerticalLineColor="Blue">
         </schedule:WeekViewSettings>
       </schedule:SfSchedule.WeekViewSettings>
    </schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %}
![](daymodule_images/timeslotappearance_week.png)

### Timeslot customization in Non Working hours

You can customize the appearance of the non-working hour timeslots by its color using [NonWorkingHoursTimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~NonWorkingHoursTimeSlotBorderColor.html), [NonWorkingHoursTimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~NonWorkingHoursTimeSlotColor.html), `VerticalLineStrokeWidth`, `VerticalLineColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.

{% tabs %}

{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WeekView;
	//Create new instance of WeekViewSettings
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Aqua;
	weekViewSettings.VerticalLineColor = Color.Blue;
	weekViewSettings.NonWorkingHoursTimeSlotColor = Color.Yellow;
	weekViewSettings.TimeSlotBorderStrokeWidth = 5;
	weekViewSettings.VerticalLineStrokeWidth = 5;
	schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
     <schedule:SfSchedule.WeekViewSettings>
      <!--setting week view settings properties -->
        <schedule:WeekViewSettings
            NonWorkingHoursTimeSlotColor="Yellow"
            NonWorkingHoursTimeSlotBorderColor="Aqua" 
            TimeSlotBorderStrokeWidth="5"
            VerticalLineStrokeWidth="5" 
            VerticalLineColor="Blue">
        </schedule:WeekViewSettings>
     </schedule:SfSchedule.WeekViewSettings>
    </schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %}
![](daymodule_images/non-working hours_week.png)

>**Note**:
` TimeSlotBorderStrokeWidth`and ` VerticalLineStrokeWidth` properties are common to both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as Non-accessible blocks by using[NonAccessibleBlocks](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~NonAccessibleBlocks.html) of `WeekViewSettings` so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}

{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WeekView;
	//Create new instance of NonAccessibleBlock
	NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock();
	//Create new instance of NonAccessibleBlocksCollection
	NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	nonAccessibleBlock.StartTime = 13;
	nonAccessibleBlock.EndTime = 14;
	nonAccessibleBlock.Text = "LUNCH";
	nonAccessibleBlock.Color = Color.Black;
	nonAccessibleBlocksCollection.Add(nonAccessibleBlock);
	weekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;
	schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}

{% highlight XAML %}

        <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
            <!--setting non-accessing blocks-->
            <schedule:SfSchedule.WeekViewSettings>
                <schedule:WeekViewSettings>
                    <schedule:WeekViewSettings.NonAccessibleBlocks>
                        <schedule:NonAccessibleBlock 
                             StartTime="13"
                             EndTime="14"  
                             Text="LUNCH"
                             Color="Black" />
                    </schedule:WeekViewSettings.NonAccessibleBlocks>
                </schedule:WeekViewSettings>
            </schedule:SfSchedule.WeekViewSettings>
        </schedule:SfSchedule>  
{% endhighlight %}
{% endtabs %}
![](daymodule_images/non-accessibleblock_week.png)

>**Note**:
Selection and related events will not be working in this blocks.

## Change first day of week
By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using[FirstDayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~FirstDayOfWeek.html) property of `SfSchedule`.

{% tabs %}

{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WeekView;
	schedule.FirstDayOfWeek = 3;
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView"        FirstDayOfWeek="3"/>
{% endhighlight %}
{% endtabs %}
![](daymodule_images/firstdayofweek_week.png)

## Time Label Formatting

You can customize the format for the labels which are mentioning the time, by setting [TimeFormat](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekLabelSettings~TimeFormat.html) property of [WeekLabelSettings](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekViewSettings~WeekLabelSettings.html) in `WeekViewSettings`.

{% tabs %}
{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WeekView;
			WeekViewSettings weekViewSettings = new WeekViewSettings();
			WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
			weekLabelSettings.TimeFormat = "hh mm";
			weekViewSettings.WeekLabelSettings = weekLabelSettings;
			schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}
![](daymodule_images/timelabelformat_week.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WeekLabelSettings~TimeLabelColor.html) property of `WeekLabelSettings` in `WeekViewSettings`.

{% tabs %}

{% highlight C# %}

           schedule.ScheduleView = ScheduleView.WeekView;
			//Create new instance of WeekViewSettings
			WeekViewSettings weekViewSettings = new WeekViewSettings();
			//Create new instance of WeekLabelSettings
			WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
			weekLabelSettings.TimeLabelColor = Color.Blue;
			weekViewSettings.WeekLabelSettings = weekLabelSettings;
			schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}
![](daymodule_images/timelabelappearance_week.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style:
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectionStyle.html) property of `SfSchedule`.

{% tabs %}

{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WeekView;
			//Create new instance of SelectionStyle 
			SelectionStyle selectionStyle = new SelectionStyle();
			selectionStyle.BackgroundColor = Color.Blue;
			selectionStyle.BorderColor = Color.Black;
			selectionStyle.BorderThickness = 5;
			selectionStyle.BorderCornerRadius = 5;
			schedule.SelectionStyle = selectionStyle;
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
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
![](daymodule_images/selectionstyle_week.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectionView.html) property of `SfSchedule`.

{% tabs %}

{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WeekView;
			//Add the CustomView 
			Button customView = new Button();
			customView.Text = "+NewEvent";
			customView.BackgroundColor = Color.FromHex("#FF9800");
			customView.TextColor = Color.White;
			schedule.SelectionView = customView;
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
      <schedule:SfSchedule.SelectionView>
           <Button 
               BackgroundColor="#FF9800" 
               Text="+NewEvent" 
               TextColor="White"/>
      </schedule:SfSchedule.SelectionView>
    </schedule:SfSchedule>
{% endhighlight %}
{% endtabs %}
![](daymodule_images/selectioncustomview_week.png)

>**Note:**
Selection customization is applicable for time slots alone.




















