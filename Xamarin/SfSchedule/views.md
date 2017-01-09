---
layout: post
title: Accessing View modes in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to set views in SfSchedule control
platform: xamarin
control: SfSchedule
documentation: ug
---


# Views

Schedule control provides four different types of views to display dates. `DayView`, `WeekView`, `WorkWeekView` and `MonthView`. It can be assigned to the schedule control by using `ScheduleView` property. Based on the user’s preference appointments can be viewed in any of the four type of view available. By default schedule control is assigned with day view.

## Day View

DayView is used to display a single day, current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule
      x:Name="sfschedule" 
	  ScheduleView="DayView">
	</schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    //creating new instance for schedule
    SfSchedule sfschedule= new SfSchedule ();
    
    //setting schedule view
    sfschedule.ScheduleView = ScheduleView.DayView;
    
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

![](views_images/DayView/DayView.png)

### Settings

#### Date Time Formatting

You can format the time string in the schedule control using `DayLabelSettings` of `DayViewSettings`. Also you can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `DayViewSettings`.To know more about customization of timeslot panel refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule>
        <schedule:SfSchedule.DayViewSettings>
		<!--setting label formats-->
		<schedule:DayViewSettings.DayLabelSettings >
		<schedule:DayLabelSettings TimeFormat="hh a"/>
		</schedule:DayViewSettings.DayLabelSettings>
        </schedule:DayViewSettings>
        </schedule:SfSchedule.DayViewSettings>
    </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}
    
    DayViewSettings dayviewsettings = new DayViewSettings();
	//setting label size and formats
    DayLabelSettings dayLabelSettings =new DayLabelSettings();
    dayLabelSettings.TimeFormat =("hh a");
    dayViewSettings.DayLabelSettings= dayLabelSettings;
    sfschedule.DayViewSettings = dayViewSettings;
    this.content = sfschedule;
    
 {% endhighlight %} 
 
 {% endtabs %}

#### Non-Accessible Blocks

You can restrict/allocate certain timeslot as Non-accessible block using `NonAccessibleBlocks` of `DayViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}

{% highlight xaml %}

    <!--setting non-accessing blocks-->
	<schedule:DayViewSettings.NonAccessibleBlocks>
        <schedule:NonAccessibleBlock 
			StartTime="13" 
			EndTime ="14"
			Text="LUNCH"
			Color="Black"/>			
    </schedule:DayViewSettings.NonAccessibleBlocks>
    
{% endhighlight %}

{% highlight C# %}

    //setting non-accessing blocks.
    NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock ();
    NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new    NonAccessibleBlocksCollection ();
    nonAccessibleBlock.StartTime = 13;
    nonAccessibleBlock.EndTime = 14;
    nonAccessibleBlock.Text = “LUNCH”;
    nonAccessibleBlock.Color = Color.Black;
    nonAccessibleBlocksCollection.Add (nonAccessibleBlock);
    dayViewSettings.NonAccessibleBlocks =nonAccessibleBlocksCollection;
    sfschedule.DayViewSettings = dayViewSettings;
    
{% endhighlight %}

{% endtabs %}

#### Working Hours

You can modify the working hours using `WorkStartHour` and `WorkEndHour` properties of `DayViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.To know more about customization of working hours refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule>
        <schedule:SfSchedule.DayViewSettings>
            <!--setting working hours properties -->
            <schedule:DayViewSettings
            WorkStartHour="10"
            WorkEndHour="18">
            </schedule:DayViewSettings>
        </schedule:SfSchedule.DayViewSettings>
    </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight C# %}

    //setting working hours properties 
    DayViewSettings dayViewSettings = new DayViewSettings ();
    dayViewSettings.WorkStartHour = 10;
    dayViewSettings.WorkEndHour = 18;
    sfschedule.DayViewSettings = dayviewsettings;
    
{% endhighlight %}

{% endtabs %}

#### All Day Appointments Panel

You can view All Day appointments in separate panel and the panel’s visibility can be enabled by setting `ShowAllDay` property of `DayViewSettings` as true.

Also you can change the all day appointment panel color using the property `AllDayAppointmentLayoutColor`.To know more about customization of all day appointment panel [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule.DayViewSettings>
		<schedule:DayViewSettings
			ShowAllDay="true">
		</schedule:DayViewSettings>
	</schedule:SfSchedule.DayViewSettings>
	
{% endhighlight %}

{% highlight c# %}

    dayviewsettings.ShowAllDay = true;

 {% endhighlight %} 
 
 {% endtabs %}

![](views_images/NonAccessinleBlock/NonAcessibleBlock.png)

>**Note**:These properties and customizations are applicable only for Day View. Customizations for other views are discussed under the respective views.

## Week View

To view all the seven days of a particular week, by default if will be current week. Appointments arranged in timeslots based on its duration with respective day of the week.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule x:Name="sfschedule" 
	  ScheduleView="WeekView">
	</schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}
    
    //creating new instance for schedule
    SfSchedule sfschedule= new SfSchedule ();
    
    //setting schedule view
    sfschedule.ScheduleView = ScheduleView.WeekView;
    
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

![](views_images/WeekView/WeekView.png)

### Settings

#### Date Time Formatting

You can format the time string in the schedule control using `WeekLabelSettings` of `WeekViewSettings`. Also you can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WeekViewSettings`.To know more about customization of time slot panel refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule ScheduleView="WeekView">
        <schedule:SfSchedule.WeekViewSettings>
			<!--setting label formats-->
			<schedule:WeekViewSettings.WeekLabelSettings >
			<schedule:WeekLabelSettings TimeFormat="hh a"/>
			</schedule:WeekViewSettings.WeekLabelSettings>
          </schedule:WeekViewSettings>
        </schedule:SfSchedule.WeekViewSettings>
    </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}
    
    WeekViewSettings weekViewSettings = new WeekViewSettings ();
    //setting label size and formats
    WeekLabelSettings weekLabelSettings = new WeekLabelSettings (); 
    weekLabelSettings.TimeFormat =("hh a");
    weekViewSettings.WeekLabelSettings = weekLabelSettings;
    sfschedule.WeekViewSettings = weekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### Non-Accessible Blocks

You can restrict/allocate certain timeslot as Non-accessible block using `NonAccessibleBlocks` of `WeekViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule ScheduleView="WeekView">
        <schedule:SfSchedule.WeekViewSettings>
			<!--setting non-accessing blocks-->
			<schedule:WeekViewSettings.NonAccessibleBlocks>
              <schedule:NonAccessibleBlock 
						StartTime="13" 
						EndTime ="14"
						Text="LUNCH"
						Color="Black"/>			
           </schedule:WeekViewSettings.NonAccessibleBlocks>
          </schedule:WeekViewSettings>
        </schedule:SfSchedule.WeekViewSettings>
     </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}

    //setting non-accessing blocks
    NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock ();
    NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection ();
    nonAccessibleBlock.StartTime = 13;
    nonAccessibleBlock.EndTime = 14;
    nonAccessibleBlock.Text = "LUNCH”; 
    nonAccessibleBlock.Color = Color.Black;
    nonAccessibleBlocksCollection.Add (nonAccessibleBlock);
    weekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;
    sfschedule.WeekViewSettings = weekViewSettings;

{% endhighlight %}

{% endtabs %}

>**NOTE**:
Non-Accessible Block is not applicable in Windows Phone.

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and `WorkEndHour` properties of `WeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.To know more about customization of working hours refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule ScheduleView="WeekView">
        <schedule:SfSchedule.WeekViewSettings>
			<!--setting week view settings properties -->
		    <schedule:WeekViewSettings
			WorkStartHour="10" 
			WorkEndHour="18">
            </schedule:WeekViewSettings>
        </schedule:SfSchedule.WeekViewSettings>
     </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}

    //setting week view settings properties
    WeekViewSettings weekViewSettings = new WeekViewSettings ();
    weekViewSettings.WorkStartHour = 10;
    weekViewSettings.WorkEndHour = 18;
    sfschedule.WeekViewSettings = weekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### All Day Appointments Panel

You can view All Day appointments in separate panel and the panel’s visibility can be enabled by setting `ShowAllDay` property of `WeekViewSettings` as true. Also you can change the all day appointment panel color using the property `AllDayAppointmentLayoutColor`.To know more about customization of all day appointment panel refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}

    <schedule:SfSchedule ScheduleView="WeekView">
        <schedule:SfSchedule.WeekViewSettings>
			<!--setting week view settings properties -->
			<schedule:WeekViewSettings
			ShowAllDay="true" />
        </schedule:SfSchedule.WeekViewSettings>
     </schedule:SfSchedule>
     
{% endhighlight %}

{% highlight c# %}

    //setting week view settings properties
    WeekViewSettings weekViewSettings = new WeekViewSettings ();
    weekViewSettings.ShowAllDay = true;
    sfschedule.WeekViewSettings = weekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

![](views_images/NonAccessibleBlock_WeekView_images/NonAccessibleBlock_WeekView.png)

## Work Week View

To view working days of a particular week, by default current work week will be displayed. Saturday and Sunday are the non-working days by default; it can be customized with any days in a WeekView. Appointments arranged in timeslots based on its duration with respective day of the week.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule x:Name="sfschedule" 
	  ScheduleView="WorkWeekView">
	</schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}
    
    //creating new instance for schedule
    SfSchedule sfschedule= new SfSchedule ();
    
    //setting schedule view
    sfschedule.ScheduleView = ScheduleView.WorkWeekView;
    
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

![](views_images/WorkWeekView/WorkWeekView.png)

### Settings

#### Date Time Formatting

You can format the time string in the schedule control using `WorkWeekLabelSettings` of `WorkWeekViewSettings`. 

Also you can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WorkWeekViewSettings`.To know more about customization of time slot panel refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule ScheduleView="WorkWeekView">
        <schedule:SfSchedule.WorkWeekViewSettings>
			<!--setting label formats-->
			<schedule:WorkWeekViewSettings.WorkWeekLabelSettings >
			<schedule:WorkWeekLabelSettings TimeFormat="hh a"/>
			</schedule:WorkWeekViewSettings.WorkWeekLabelSettings>
          </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
     </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
    //setting label formats
    WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
    workWeekLabelSettings.TimeFormat = ("hh a");
    workWeekViewSettings.WorkWeekLabelSettings =(workWeekLabelSettings);
    sfschedule.WorkWeekViewSettings = (workWeekViewSettings);
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### Non-Accessible Blocks

You can restrict/allocate certain timeslot as Non-accessible block using `NonAccessibleBlocks` of `WorkWeekViewSettings`, so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule ScheduleView="WorkWeekView">
        <schedule:SfSchedule.WorkWeekViewSettings>
			<!--setting non-accessing blocks-->
			<schedule:WorkWeekViewSettings.NonAccessibleBlocks>
              <schedule:NonAccessibleBlock 
						StartTime="13" 
						EndTime ="14"
						Text="LUNCH"
						Color="Black"/>			
           </schedule:WorkWeekViewSettings.NonAccessibleBlocks>
          </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
     </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    //setting non-accessing blocks.
    NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock ();
    NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection ();
    nonAccessibleBlock.StartTime = 13;
    nonAccessibleBlock.EndTime = 14;
    nonAccessibleBlock.Text = "LUNCH”;
    nonAccessibleBlock.Color = Color.Black;
    nonAccessibleBlocksCollection.Add (nonAccessibleBlock);
    workWeekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;
    sfschedule.WorkWeekViewSettings = workWeekViewSettings;
    sfschedule.WorkWeekViewSettings = (workWeekViewSettings);
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

>**NOTE**:
Non-Accessible Block is not applicable in Windows Phone.

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and `WorkEndHour`  properties of `WorkWeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.To know more about customization of working hours refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule ScheduleView="WorkWeekView">
        <schedule:SfSchedule.WorkWeekViewSettings>
			<!--setting workweek view settings properties -->
			<schedule:WorkWeekViewSettings 
			WorkStartHour="10" 
			WorkEndHour="18">
          </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
     </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    //setting workweekviewsettings properties
    WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
    workWeekViewSettings.WorkStartHour = 10;
    workWeekViewSettings.WorkEndHour = 18;
    sfschedule.WorkWeekViewSettings = workWeekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

#### All Day Appointments Panel

You can view All Day appointments in separate panel and the panel’s visibility can be enabled by setting `ShowAllDay`  property of `WorkWeekViewSettings` as true.

Also you can change the all day appointment panel color using the property `AllDayAppointmentLayoutColor`. To know more about customization of all day appointment panel refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization")

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule ScheduleView="WorkWeekView">
        <schedule:SfSchedule.WorkWeekViewSettings>
			<!--setting workweek view settings properties -->
			<schedule:WorkWeekViewSettings
			ShowAllDay="true">
          </schedule:WorkWeekViewSettings>
        </schedule:SfSchedule.WorkWeekViewSettings>
     </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    //setting workweekviewsettings properties
    WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
    workWeekViewSettings.ShowAllDay = true;
    sfschedule.WorkWeekViewSettings = workWeekViewSettings;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

![](views_images/NonAccessibleBlock_WorkWeekView_images/NonAccessibleBlock-WorkWeekView.png)

## Month View

To view entire dates of a particular month, by default current month will be displayed initially. Appointments arranged within the cell based on its duration. Current date is differentiated by some color and rest of the dates in a month will be in different color., Also the color differentiation for dates will be applicable for previous and next month dates.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule x:Name="sfschedule" 
	  ScheduleView="MonthView">
	</schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}

    //creating new instance for schedule
    SfSchedule sfschedule= new SfSchedule ();
    
    //setting schedule view
    sfschedule.ScheduleView = ScheduleView.MonthView;
    
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

![](views_images/MonthView/MonthView.png)

### Settings

#### Date Time formatting

You can format the date and day string in the schedule control using 
`MonthLabelSettings` of `MonthViewSettings`.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule.MonthViewSettings >
			<!--setting label formats-->
		    <schedule:MonthViewSettings.MonthLabelSettings> 
				<schedule:MonthLabelSettings 
				DayFormat="E"
				DateFormat="dd">
				</schedule:MonthLabelSettings>	
			</schedule:MonthViewSettings.MonthLabelSettings>
		</schedule:MonthViewSettings>
      </schedule:SfSchedule.MonthViewSettings>
      
{% endhighlight %}

{% highlight c# %}

    //setting month view settings properties
    MonthViewSettings monthViewSettings =  new MonthViewSettings();
    //setting label size and formats
    MonthLabelSettings monthLabelSettings  = new MonthLabelSettings();
    monthLabelSettings.DayFormat=("E");
    monthLabelSettings. DateFormat=("dd");
    monthViewSettings.MonthLabelSettings = (monthLabelSettings);
    schedule.MonthViewSettings = (monthViewSettings);
    this.Content = (sfschedule);

{% endhighlight %}

{% endtabs %}

#### Blackout dates

You can restrict/allocate certain month cell as blackout days using `BlackoutDates` of `MonthViewSettings`, so that we can allocate those cells for predefined events/activities like Scheduled maintenance, planned leave etc.

{% highlight c# %}

    //setting month view settings properties
    MonthViewSettings monthViewSettings =  new MonthViewSettings();
    ObservableCollection<DateTime> black_out_days_collection = new ObservableCollection<DateTime>();
    DateTime date = DateTime.Now.Date;
    DateTime date1 = DateTime.Now.Date.AddDays(1);
    DateTime date2 = DateTime.Now.Date.AddDays(2);
    DateTime date3 = DateTime.Now.Date.AddDays(3);
    DateTime date4 = DateTime.Now.Date.AddDays(4);
    DateTime date5 = DateTime.Now.Date.AddDays(5);
    
    black_out_days_collection.Add(date);
    black_out_days_collection.Add(date1);
    black_out_days_collection.Add(date2);
    black_out_days_collection.Add(date3);
    black_out_days_collection.Add(date4);
    black_out_days_collection.Add(date5);
    monthViewSettings.BlackoutDates = black_out_days_collection;
 
    monthViewSettings.MonthLabelSettings = monthLabelSettings;
    schedule.MonthViewSettings = monthViewSettings;
    this.Content = sfschedule;

{% endhighlight %}

{% endtabs %}

#### Week number

You display the week number of the year in month view by setting `ShowWeekNumber` in property of `MonthViewSettings` are true. By default it is false.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule.MonthViewSettings >
        <schedule:MonthViewSettings ShowWeekNumber="False">
		</schedule:MonthViewSettings>
      </schedule:SfSchedule.MonthViewSettings>
      
{% endhighlight %}

{% highlight c# %}

    //setting month view settings properties
    MonthViewSettings monthViewSettings =  new MonthViewSettings();
    monthViewSettings.ShowWeekNumber = true;
    schedule.MonthViewSettings = monthViewSettings;
    this.Content = sfschedule;

{% endhighlight %}

{% endtabs %}

#### Month Navigation Direction

`MonthView` of Schedule can be navigated horizontally and vertically.You can change the direction of navigation through `MonthNavigationDirection` property of `MonthViewSettings`.By default MonthNavigation is `Horizontal`

{% tabs %}

{% highlight xaml %}

    <schedule:MonthViewSettings
        MonthNavigationDirection="Vertical">
	</schedule:MonthViewSettings>
	
{% endhighlight %}
{% highlight C# %}

    MonthViewSettings monthViewSettings = new MonthViewSettings();
    //To navigate vertically
    monthViewSettings.MonthNavigationDirection =  MonthNavigationDirections.Vertical;
    sfschedule.MonthViewSettings = monthViewSettings;
    
{% endhighlight %}
{% endtabs %}

### MonthViewCellStyle

You can customize the month cells of MonthView using vaious properties of `MonthViewCellStyle`. To know more about customization of MonthView refer [MonthCell Customization](/xamarin/sfschedule/appearance-and-styling "MonthCell Customization")

### MonthAppointmentInlineTapped Event

You can able to know the details of appointments in inline using `MonthInlineAppointmentTapped` event in `Schedule`.To know more about customization of working hours refer [Panel Customization](/xamarin/sfschedule/appearance-and-styling "Panel Customization").

![](views_images/BlackOutDates/BlackOutDays.png)