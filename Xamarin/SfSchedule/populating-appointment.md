---
title: Populating Appointments in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Populate Appointments in SfSchedule control
platform: xamarin
control: SfSchedule
documentation: ug
---

# Populating Appointments

Schedule control has a built-in capability to handle the appointment arrangement internally based on the ScheduleAppointment collections. `ScheduleAppointment` is a class, which holds the details about the appointment to be rendered in schedule. `ScheduleAppointmentsCollection` can be provided to schedule using the following method.

### Adding appointments using Collection

`ScheduleAppointment` has some basic properties such as StartTime, EndTime, Subject and some additional information about the appointment can be added using Color, Notes, Location, All Day, Recursive properties.

Create the collection of the ScheduleAppointments by setting required details using above mentioned properties for each appointment. And then assign the created collection to the `DataSource` property, which is of type `IEnumerable`, of `SfSchedule` as like in below code example.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule
      x:Name="sfschedule" 
	  ScheduleView="WeekView" 
	  DataSource="{Binding appointmentCollection
	</schedule:SfSchedule>

{% endhighlight %}

{% highlight c# %}
    
    ScheduleAppointmentCollection appointmentCollection;
    
    //creating new instance for schedule
    SfSchedule sfschedule=new SfSchedule();
    sfschedule.ScheduleView = ScheduleView.WeekView;
    appointmentCollection = new ScheduleAppointmentCollection();
    
    //Creating new event
    ScheduleAppointment clientMeeting = new ScheduleAppointment();
    
    DateTime currentDate = DateTime.Now;
    DateTime startTime = new DateTime (currentDate.Year,currentDate.Month,currentDate.Day, 10, 0, 0); 
    DateTime endTime = new DateTime (currentDate.Year, currentDate.Month,currentDate.Day, 12, 0, 0);
    
    clientMeeting.StartTime = startTime;
    clientMeeting.EndTime = endTime;
    clientMeeting.Color = Color.Blue;
    clientMeeting.Subject = "ClientMeeting";
    appointmentCollection.Add(clientMeeting);
    sfschedule.DataSource = appointmentCollection;
    this.Content= sfschedule;
    
{% endhighlight %}

{% endtabs %}

![](PopulatingAppointments_images/Appointments.png)

### Adding appointments using CustomData

Custom Data mapping can be done in Schedule by assigning custom data properties instead of properties of ScheduleAppointment(StartTime, EndTime, Subject,Color) to Schedule by binding those properties using `ScheduleAppointmentMapping`.

Create the collection of the ScheduleAppointments by setting required details using above mentioned properties for each appointment. And then assign the created collection to the `DataSource` property, which is of type `IEnumerable`, of `SfSchedule` as like in below code example.

{% tabs %}

{% highlight xaml %}
    
    <schedule:SfSchedule
    x:Name="Schedule" ScheduleView="WeekView"
    DataSource="{Binding appointmentCollection}">
    
    <!--mapping custom data properties-->
    <schedule:SfSchedule.AppointmentMapping>
        <schedule:ScheduleAppointmentMapping 
        SubjectMapping="Name" 
        StartTimeMapping = "MeetingStartDate"
        EndTimeMapping = "MeetingEndDate"
        ColorMapping="color"/>
    </schedule:SfSchedule.AppointmentMapping>
    
    </schedule:SfSchedule>
    
{% endhighlight %}

{% highlight c# %}
    
    //creating new instance for schedule
    SfSchedule sfschedule=new SfSchedule();
    sfschedule.ScheduleView = ScheduleView.WeekView;
    
	//creating instance for CustomData
    CustomData customData = new CustomData();
	ObservableCollection <CustomData> appointmentCollection = new ObservableCollection<CustomData>();

	ScheduleAppointmentMapping scheduleAppointmentMapping = new ScheduleAppointmentMapping();

	DateTime currentDate = DateTime.Now;

	DateTime starttime = new DateTime(currentDate.Year, currentDate.Month, currentDate.Day, 10, 0, 0);
	DateTime endtime = new DateTime(currentDate.Year, currentDate.Month, currentDate.Day, 12, 0, 0);

	customData.Name = "ClientMeeting";
	customData.Place = "Chennai";
	customData.MeetingStartDate = starttime;
	customData.MeetingEndDate = endtime;
	customData.color = Color.Blue;

	appointmentCollection.Add(customData);

	scheduleAppointmentMapping = new ScheduleAppointmentMapping();
	scheduleAppointmentMapping.SubjectMapping = "Name";
	scheduleAppointmentMapping.LocationMapping = "Place";
	scheduleAppointmentMapping.StartTimeMapping = "MeetingStartDate";
	scheduleAppointmentMapping.EndTimeMapping = "MeetingEndDate";
	scheduleAppointmentMapping.ColorMapping = "color";

	sfschedule.AppointmentMapping = scheduleAppointmentMapping;
	sfschedule.DataSource = appointmentCollection;
    this.Content= sfschedule;
	
	//CustomData class
	public class CustomData
	{
		public string Name { get; set; }
		public string Place { get; set; }
		public DateTime MeetingStartDate { get; set; }
		public DateTime MeetingEndDate { get; set; }
		public Color color { get; set; }
	}
	
{% endhighlight %}

{% endtabs %}

![](PopulatingAppointments_images/Appointments.png)

### AppointmentStyle

You can customize the Schedule Appointments using various properties of `AppointmentStyle`.To know more about customization of ScheduleAppointment refer [Appointment Customization](/xamarin/sfschedule/appearance-and-styling "Appointment Customization").

![](PopulatingAppointments_images/Appointments.png)