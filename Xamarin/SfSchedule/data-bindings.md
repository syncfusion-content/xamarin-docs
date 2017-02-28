---

layout: post
title: Populating Appointments in Syncfusion SfSchedule control for Xamarin.Forms
description: Learn how to Populate Appointments in SfSchedule control
platform: xamarin
control: SfSchedule
documentation: ug

---


# Data Bindings

Schedule control has a built-in capability to handle the appointment arrangement internally based on the ScheduleAppointment collections. `ScheduleAppointment` is a class, which holds the details about the appointment to be rendered in schedule. `ScheduleAppointmentsCollection` can be provided to schedule using the following method.

## Schedule Appointment

### Adding appointments using Collection

`ScheduleAppointment` has some basic properties such as StartTime, EndTime, Subject and some additional information about the appointment can be added using Color, Notes, Location, All Day, Recursive properties.

Create the collection of the ScheduleAppointments by setting required details using above mentioned properties for each appointment. And then assign the created collection to the `DataSource` property of `IEnumerable` type in `SfSchedule` as like in below code example.

{% highlight c# %}
    
    ScheduleAppointmentCollection appointmentCollection;

	//creating new instance for schedule
	SfSchedule sfschedule=new SfSchedule();
	sfschedule.ScheduleView = ScheduleView.WeekView;
	ScheduleAppointmentCollection appointmentCollection = new ScheduleAppointmentCollection();

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

### Adding AllDayAppointments 

AllDayAppointment is for setting appointment for full day by using `ShowAllDay` property in the `ScheduleAppointment`. Create the collection of the `ScheduleAppointment` by setting required details using above mentioned properties for each appointment. And then assign the created collection to the `DataSource` property of `SfSchedule` as like in below code example.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule sfschedule=new SfSchedule();
	sfschedule.ScheduleView = ScheduleView.WeekView;
	WeekViewSettings weekViewSeetings = new WeekViewSettings();
	weekViewSeetings.ShowAllDay = true;
	sfschedule.WeekViewSettings = weekViewSeetings;
	ScheduleAppointmentCollection appointmentCollection = new ScheduleAppointmentCollection();

	//Creating new event
	ScheduleAppointment clientMeeting = new ScheduleAppointment();

	DateTime currentDate = DateTime.Now;
	DateTime startTime = new DateTime (currentDate.Year,currentDate.Month,currentDate.Day, 10, 0, 0); 
	DateTime endTime = new DateTime (currentDate.Year, currentDate.Month,currentDate.Day, 12, 0, 0);

	clientMeeting.StartTime = startTime;
	clientMeeting.EndTime = endTime;
	clientMeeting.Color = Color.Blue;
	clientMeeting.Subject = "ClientMeeting";
	clientMeeting.IsAllDay = true;
	appointmentCollection.Add(clientMeeting);
	sfschedule.DataSource = appointmentCollection;
	this.Content= sfschedule;

{% endhighlight %}

### Adding Recurrence Appointments  

Recursive appointments can be created by enabling `IsRecursive` property in Schedule appointments, to know more about adding appointments in the control, refer `ScheduleAppointment`.

And then need to set the RecurrenceRule to populate the required recursive appointment collection in a specific pattern.RRULE can be easily created through `RecurrenceBuilder` engine by simple APIs available in Schedule control.

Recursive appointment can be created in any recurrence patterns, for instance, some events can be repeated every week such as “Server maintenance”, where as some on them may repeat every year like wedding anniversary. 

To know more about customization of all day appointment panel refer [Recurrence Appointments](/xamarin/sfschedule/recurrence "Recurrence Pattern")

### Appointment Editor

Appointments can be edit using this Appointment editor by tapping the Appointment using `ScheduleCellTapped`event and set the required properties of `ScheduleAppointment` for editing.

## Custom Data

You can add events to the schedule by creating collection of `ScheduleAppointments` using `ObservableCollection`. You can schedule meetings for a particular day by setting `From` and `To` of `Meeting` class.

{% highlight c# %}

	ObservableCollection<Meeting> ListOfMeeting = new ObservableCollection<Meeting>();

	private void BookingAppointments()
	{
	Random randomTime = new Random();
	List<Point> randomTimeCollection = GettingTimeRanges();

	int appointmentIndex = 0;
	DateTime date;
	DateTime DateFrom = DateTime.Now.AddDays(-10);
	DateTime DateTo = DateTime.Now.AddDays(10);
	DateTime dataRangeStart = DateTime.Now.AddDays(-3);
	DateTime dataRangeEnd = DateTime.Now.AddDays(3);

	for (date = DateFrom; date < DateTo; date = date.AddDays(1))
	{
	if ((DateTime.Compare(date, dataRangeStart) > 0) && (DateTime.Compare(date, dataRangeEnd) < 0))
	{
	for (int AdditionalAppointmentIndex = 0; AdditionalAppointmentIndex < 3; AdditionalAppointmentIndex++)
	{
	Meeting meeting = new Meeting();
	int hour = (randomTime.Next((int)randomTimeCollection[AdditionalAppointmentIndex].X, (int)randomTimeCollection[AdditionalAppointmentIndex].Y));
	meeting.From = new DateTime(date.Year, date.Month, date.Day, hour, 0, 0);
	meeting.To = (meeting.From.AddHours(1));
	meeting.EventName = meeting_collection[randomTime.Next(9)];
	meeting.color = color_collection[randomTime.Next(9)];
	ListOfMeeting.Add(meeting);
	}
	}
	else {
	Meeting meeting = new Meeting();
	meeting.From = new DateTime(date.Year, date.Month, date.Day, randomTime.Next(9, 11), 0, 0);
	meeting.To = (meeting.From.AddHours(1));
	meeting.EventName = meeting_collection[randomTime.Next(9)];
	meeting.color = color_collection[randomTime.Next(9)];
	ListOfMeeting.Add(meeting);
	}
	}
	}

{% endhighlight %}

You can add `Subject` and `Color` to the appointments created by creating a collection for the same.

{% highlight c# %}

	List<string> meeting_collection;
	List<Color> color_collection;

	private void InitializeDataForBookings()
	{
	meeting_collection = new List<string>();
	meeting_collection.Add("General Meeting");
	meeting_collection.Add("Plan Execution");
	meeting_collection.Add("Project Plan");
	meeting_collection.Add("Consulting");
	meeting_collection.Add("Performance Check");
	meeting_collection.Add("Yoga Therapy");
	meeting_collection.Add("Plan Execution");
	meeting_collection.Add("Project Plan");
	meeting_collection.Add("Consulting");
	meeting_collection.Add("Performance Check");

	color_collection = new List<Color>();
	color_collection.Add(Color.FromHex("#117EB4"));
	color_collection.Add(Color.FromHex("#B4112E"));
	color_collection.Add(Color.FromHex("#C44343"));
	color_collection.Add(Color.FromHex("#11B45E"));
	color_collection.Add(Color.FromHex("#43BEC4"));
	color_collection.Add(Color.FromHex("#B4112E"));
	color_collection.Add(Color.FromHex("#C44343"));
	color_collection.Add(Color.FromHex("#117EB4"));
	color_collection.Add(Color.FromHex("#C4435A"));
	color_collection.Add(Color.FromHex("#DF5348"));
	color_collection.Add(Color.FromHex("#43c484"));
	}

{% endhighlight %}

You can set random time for the appointments in schedule.

{% highlight c# %}

    private List<Point> GettingTimeRanges()
    {
    List<Point> randomTimeCollection = new List<Point>();
    randomTimeCollection.Add(new Point(9, 11));
    randomTimeCollection.Add(new Point(12, 14));
    randomTimeCollection.Add(new Point(15, 17));

    return randomTimeCollection;
    }

{% endhighlight %}

![](PopulatingAppointments_images/GettingStarted.png)

## Appointment Customization

Appointments can be customized using `AppointmentStyle` property in schedule. To know more about customization of Schedule Appointment refer [View Customization](/xamarin/sfschedule/view-customization "View Customization")