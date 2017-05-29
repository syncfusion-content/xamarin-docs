---

layout: post
title: Customize the Schedule WorkWeekView at SfSchedule control for Xamarin.Forms
description: Learn how to Customize the schedule WorkWeekView in SfSchedule control
platform: xamarin.Forms
control: SfSchedule
documentation: ug

---


# WorkWeekView:

WorkWeekView is to view only working days of a particular week. By default, Saturday and Sunday are the non-working days. You can be customize it with any days of a Week. Appointments arranged in timeslots based on its duration with respective day of the week.


## ViewHeader Appearance:
You can customize the default appearance of view header in [WorkWeekView](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ScheduleView.html) by using [ViewHeaderStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.ViewHeaderStyle.html) property of [SfSchedule](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule.html).

{% tabs %}
{% highlight c# %}

            //Create new instance of Schedule
			SfSchedule schedule = new SfSchedule();
			schedule.ScheduleView = ScheduleView.WorkWeekView;
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

    <schedule:SfSchedule x:Name="schedule" ScheduleView ="WorkWeekView">
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

![](daymodule_images/viewheaderappearance_workweek.png)

You can customize the height of the ViewHeader in `WeekView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~ViewHeaderHeight.html) property of `SfSchedule`.

{% tabs %} 
{% highlight C# %}

        schedule.ScheduleView = ScheduleView.WorkWeekView;
		schedule.ViewHeaderHeight = 50;
			
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView ="WorkWeekView" ViewHeaderHeight="50" />
           
{% endhighlight %}
{% endtabs %}

![](daymodule_images/viewheaderheight_workweek.png)

## Change Time Interval:
You can customize the interval of timeslots in `WorkWeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~TimeInterval.html)  property of `SfSchedule`.

{% tabs %}
{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WorkWeekView;
	schedule.TimeInterval = 120;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView" TimeInterval="120"/>  
{% endhighlight %}
{% endtabs %} 

![](daymodule_images/timeinterval_workweek.png)

## Change Working hours:

Working hours in `WorkWeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~WorkStartHour.html) and [WorkEndHour](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~WorkEndHour.html) properties of [WorkWeekViewSettings](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~WorkWeekViewSettings.html).

{% tabs %} 
{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WorkWeekView;
	//Create new instance of WorkWeekViewSettings
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.WorkStartHour = 10;
	workWeekViewSettings.WorkEndHour = 18;
	schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
       <schedule:SfSchedule.WorkWeekViewSettings>
            <!--setting working hours properties -->
             <schedule:WorkWeekViewSettings 
                WorkStartHour="10" 
                WorkEndHour="18">
             </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
    </schedule:SfSchedule>
{% endhighlight %}
{% endtabs %}

![](daymodule_images/changeworkinghours_workweek.png)

>**Note**:
`WorkStartHour` and `WorkEndHour` should be in integer value to represent hours.

## Timeslot Appearance:
You can customize the appearance of timeslots in `WeekView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-Work-hours)
 * [Timeslot customization in Non-Working hours](timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours:

You can customize the appearance of the working hour timeslots by its color using[TimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~TimeSlotColor.html), [TimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~TimeSlotBorderColor.html), [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~VerticalLineStrokeWidth.html),  [VerticalLineColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~VerticalLineColor.html) and  [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~TimeSlotBorderStrokeWidth.html) properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WorkWeekView;
			//Create new instance of WorkWeekViewSettings
			WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
			workWeekViewSettings.TimeSlotBorderColor = Color.Aqua;
			workWeekViewSettings.VerticalLineColor = Color.Blue;
			workWeekViewSettings.TimeSlotColor = Color.Yellow;
			workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
			workWeekViewSettings.VerticalLineStrokeWidth = 5;
			schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% highlight XAML %}

     <schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
     <schedule:SfSchedule.WorkWeekViewSettings>
      <!--setting work week view settings properties -->
        <schedule:WorkWeekViewSettings
          TimeSlotColor="Yellow"
          TimeSlotBorderColor="Aqua" 
          TimeSlotBorderStrokeWidth="5"
          VerticalLineStrokeWidth="5" 
          VerticalLineColor="Blue">
       </schedule:WorkWeekViewSettings>
     </schedule:SfSchedule.WorkWeekViewSettings>
    </schedule:SfSchedule>
{% endhighlight %}
{% endtabs %} 

![](daymodule_images/timeslotappearance_workweek.png)

### Timeslot customization in Non-Working hours:

You can customize the appearance of the non-working hour timeslots by its color using [NonWorkingHoursTimeSlotBorderColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~NonWorkingHoursTimeSlotBorderColor.html),[NonWorkingHoursTimeSlotColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~NonWorkingHoursTimeSlotColor.html),`VerticalLineStrokeWidth`, `VerticalLineColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WorkWeekView;
			//Create new instance of WorkWeekViewSettings
			WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
			workWeekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Aqua;
			workWeekViewSettings.VerticalLineColor = Color.Blue;
			workWeekViewSettings.NonWorkingHoursTimeSlotColor = Color.Yellow;
			workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
			workWeekViewSettings.VerticalLineStrokeWidth = 5;
			schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView">
     <schedule:SfSchedule.WorkWeekViewSettings>
      <!--setting work week view settings properties -->
        <schedule:WorkWeekViewSettings
           NonWorkingHoursTimeSlotColor="Yellow"
           NonWorkingHoursTimeSlotBorderColor="Aqua" 
           TimeSlotBorderStrokeWidth="5"
           VerticalLineStrokeWidth="5" 
           VerticalLineColor="Blue">
        </schedule:WorkWeekViewSettings>
     </schedule:SfSchedule.WorkWeekViewSettings>
    </schedule:SfSchedule> 
{% endhighlight %}
{% endtabs %} 

![](daymodule_images/nonworkinghours_workweek.png)

>**Note**:
` TimeSlotBorderStrokeWidth`and ` VerticalLineStrokeWidth` properties are common to both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots:

You can restrict or allocate certain timeslot as Non-accessible blocks by using [NonAccessibleBlocks](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~NonAccessibleBlocks.html) of `WorkWeekViewSettings` so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}
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
{% endtabs %} 

![](daymodule_images/nonaccessibleblock_workweek.png)

>**Note**:
Selection and related events will not be working in this blocks.

## Change first day of week:
By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using[FirstDayOfWeek](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~FirstDayOfWeek.html) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}

    schedule.ScheduleView = ScheduleView.WorkWeekView;
	schedule.FirstDayOfWeek = 3;
{% endhighlight %}

{% highlight XAML %}

    <schedule:SfSchedule x:Name="schedule" ScheduleView="WorkWeekView" FirstDayOfWeek="3"/>
{% endhighlight %}
{% endtabs %} 

![](daymodule_images/firstdayofweek_workweek.png)

## Time Label Formatting:

You can customize the format for the labels which are mentioning the time, by setting [TimeFormat](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekLabelSettings~TimeFormat.html) property of [WorkWeekLabelSettings](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekViewSettings~WorkWeekLabelSettings.html) in `WorkWeekViewSettings`.


{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WorkWeekView;
			WorkWeekViewSettings workweekViewSettings = new WorkWeekViewSettings();
			WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
			workWeekLabelSettings.TimeFormat = "hh mm";
			workweekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
			schedule.WorkWeekViewSettings = workweekViewSettings;
{% endhighlight %}

![](daymodule_images/timelabelformat_workweek.png)

## Time Label Appearance:

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.WorkWeekLabelSettings~TimeLabelColor.html) property of `WorkWeekLabelSettings` in `WorkWeekViewSettings`.


{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WorkWeekView;
			//Create new instance of WorkWeekViewSettings
			WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
			//Create new instance of WorkWeekLabelSettings
			WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
			workWeekLabelSettings.TimeLabelColor = Color.Blue;
			workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
			schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}

![](daymodule_images/timelabelappearance_workweek.png)

## Selection:
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style:
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectionStyle.html) property of `SfSchedule`.

{% tabs %}
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
{% endtabs %} 

![](daymodule_images/selectionstyle_workweek.png)

### Selection customization using custom View:
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~SelectionView.html) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}

            schedule.ScheduleView = ScheduleView.WorkWeekView;
			//Add the CustomView 
			Button customView = new Button();
			customView.Text = "+NewEvent";
			customView.BackgroundColor = Color.FromHex("#FF9800");
			customView.TextColor = Color.White;
			schedule.SelectionView = customView;
{% endhighlight %}

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
{% endtabs %} 

![](daymodule_images/selectioncustomview_workweek.png)

>**Note:**
Selection customization is applicable for time slots alone.




















