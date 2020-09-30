---
layout: post
title: Appointment Drag and Drop in Xamarin Scheduler | Syncfusion
description: Describes how to drag and drop the appointments and its customization of Schedule (SfSchedule) control.
platform: xamarin
control: SfSchedule
documentation: ug
---

# Appointment Drag and Drop
Appointments can be rescheduled using the drag and drop operation. To perform drag-and-drop operations within the schedule, enable the [AllowAppointmentDrag](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_AllowAppointmentDrag) property of `SfSchedule`.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name=“schedule” ScheduleView="WeekView" AllowAppointmentDrag="true">
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.AllowAppointmentDrag = true;
{% endhighlight %}
{% endtabs %}

![Drag and Drop appointments in schedule Xamarin Forms](PopulatingAppointments_images/draganddrop.gif)

## Handle dragging based on the appointment
Using [AppointmentDragStarting](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html) event, you can get the appointment details and handle whether the appointment can be draggable or not. This event will be triggered when the appointment is started dragging. The [AppointmentDragStartingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDragStartingEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDragStartingEventArgs.html#Syncfusion_SfSchedule_XForms_AppointmentDragStartingEventArgs_Appointment) - Gets the dragged appointment details.
[Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true)- Appointment dragging can be handled (enable/disable) using this boolean property.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragStarting += Schedule_AppointmentDragStarting;

...

private void Schedule_AppointmentDragStarting(object sender, AppointmentDragStartingEventArgs e)
{
        var appointment = e.Appointment;
        e.Cancel = false;
}
{% endhighlight %}
{% endtabs %}

### Disabling dragging when the appointment is AllDay appointment
Using `Cancel` property in the `AppointmentDragStartingEventArgs` argument of Schedule `AppointmentDragStarting` event, you can enable/disable the appointment dragging based on the requirement. In the below code, appointment dragging is disabled when the appointment is AllDay appointment.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragStarting += Schedule_AppointmentDragStarting;

...

private void Schedule_AppointmentDragStarting(object sender, AppointmentDragStartingEventArgs e)
{
        var appointment = e.Appointment as ScheduleAppointment;

      if (appointment.IsAllDay)
      {
            e.Cancel = true;
      }
}
{% endhighlight %}
{% endtabs %}

## Get the dragging appointment position
Using [AppointmentDragOver](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html) event, you can get the dragging appointment details, position and time of the particular location. The event will be continuously triggered when the appointment is being dragged. The [AppointmentDragEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs.html#Syncfusion_SfSchedule_XForms_AppointmentDragEventArgs_Appointment) - Gets the details of the appointment to be dropped.
[DraggingPoint](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs.html#Syncfusion_SfSchedule_XForms_AppointmentDragEventArgs_DraggingPoint)- Gets the dragging point (X, Y) of the appointment in Schedule.
[DraggingTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDragEventArgs.html#Syncfusion_SfSchedule_XForms_AppointmentDragEventArgs_DraggingTime)- Gets the dragging time of the appointment in Schedule

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragOver += Schedule_AppointmentDragOver;

...

private void Schedule_AppointmentDragOver(object sender, AppointmentDragEventArgs e)
{
        var appointment = e.Appointment;
        var draggingPoint = e.DraggingPoint;
        var draggingTime = e.DraggingTime;
}
{% endhighlight %}
{% endtabs %}

### Displaying alert while dragging appointment over the blocked time slots
Using `draggingPoint` and `draggingTime` properties in the `AppointmentDragEventArgs` of Schedule `AppointmentDragOver` event you can get the current position and time of dragging appointment. In the below code, Indicating the message while dragging over the Schedule `NonAccessibleBlock`.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDragOver += Schedule_AppointmentDragOver;

...

private void Schedule_AppointmentDragOver(object sender, AppointmentDragEventArgs e)
{
        //// checking whether dragging appointment time within NonAccessibleBlock
        if (schedule.WorkWeekViewSettings.NonAccessibleBlocks[0].StartTime == e.DraggingTime.Hour ||
        (schedule.WorkWeekViewSettings.NonAccessibleBlocks[0].StartTime - 1 == e.DraggingTime.Hour && e.DraggingTime.Minute > 0))
        {
                label.Text = "Cannot be moved to blocked time slots";
        }
}
{% endhighlight %}
{% endtabs %}

## Handle appointment dropping
Using [AppointmentDrop](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html) event you can get the dropping appointment details, position, time and you can handle whether the appointment can be dropped to the specific position or not. This event will trigger after dropping the appointment. The [AppointmentDropEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs.html) argument contains the following properties.

[Appointment](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs.html#Syncfusion_SfSchedule_XForms_AppointmentDropEventArgs_Appointment) - Gets the details of the appointment to be dropped.
[Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true)- Appointment dropping can be handled (enable / disable) using this Boolean property.
[DropTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs.html#Syncfusion_SfSchedule_XForms_AppointmentDropEventArgs_DropTime)- Gets the dropped time of the appointment in Schedule

{% tabs %}
{% highlight c# %}
schedule.AppointmentDrop += Schedule_AppointmentDrop;

...

private void Schedule_AppointmentDrop(object sender, AppointmentDropEventArgs e)
{
        var appointment = e.Appointment;
        e.Cancel = false;
        var dropTime = e.DropTime;
}
{% endhighlight %}
{% endtabs %}

### Disabling dropping when dropping appointment within the Non-Accessible region
Using `Cancel` property in the `AppointmentDropEventArgs` argument of Schedule `AppointmentDrop` event, you can enable/disable the appointment dropping based on the requirement. In the below code, appointment dropping is disabled while dropping in the Non-Accessible block region.

{% tabs %}
{% highlight c# %}
schedule.AppointmentDrop += Schedule_AppointmentDrop;

...

private void Schedule_AppointmentDrop(object sender, AppointmentDropEventArgs e)
{
//// checking whether dropping appointment time within NonAccessibleBlock
if (schedule.WorkWeekViewSettings.NonAccessibleBlocks[0].StartTime == e.DropTime.Hour ||
(schedule.WorkWeekViewSettings.NonAccessibleBlocks[0].StartTime - 1 == e.DropTime.Hour && e.DropTime.Minute > 0))
{
        e.Cancel = true;
}
}
{% endhighlight %}
{% endtabs %}

## Customizing the Drag and Drop environment
Using [DragDropSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_DragDropSettings) property of schedule, you can handle the behavior of drag and drop in Schedule.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
    <schedule:SfSchedule.DragDropSettings>
        <schedule:DragDropSettings AllowNavigate="true" AllowScroll="true" ShowTimeIndicator="true">
    </schedule:DragDropSettings>
</schedule:SfSchedule.DragDropSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
DragDropSettings dragDropSettings = new DragDropSettings();
dragDropSettings.AllowNavigate = true;
dragDropSettings.AllowScroll = true;
var timeSpan = new TimeSpan(0, 0, 0, 1, 0);
dragDropSettings.AutoNavigationDelay = timeSpan;
dragDropSettings.ShowTimeIndicator = true;
dragDropSettings.TimeIndicatorStyle = timeIndicatorStyle;
schedule.DragDropSettings = dragDropSettings;
{% endhighlight %}
{% endtabs %}

### Disabling navigation when dragging appointment
Using [AllowNavigate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DragDropSettings.html#Syncfusion_SfSchedule_XForms_DragDropSettings_AllowNavigate) boolean property can handle the Appointment dragging, whether navigate to next/previous view or not while dragging the appointment to the endpoint of the current view in Schedule. Default value of the `AllowNavigate` property is true and  Schedule will navigate to next/previous view when dragging the appointment the endpoint of the current view.

{% tabs %}
{% highlight c# %}
dragDropSettings.AllowNavigate = false;
{% endhighlight %}
{% endtabs %}

### Handling navigation delay while holding dragged appointment
Using [AutoNavigationDelay](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DragDropSettings.html#Syncfusion_SfSchedule_XForms_DragDropSettings_AutoNavigationDelay)  `TimeSpan` property can handle the navigation time when navigating to next/previous view while holding the dragged appointment.

{% tabs %}
{% highlight c# %}
var timeSpan = new TimeSpan(0, 0, 0, 1, 0);
dragDropSettings.AutoNavigationDelay = timeSpan;
{% endhighlight %}
{% endtabs %}

### Disabling scroll when dragging appointment
Using [AllowScroll](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DragDropSettings.html#Syncfusion_SfSchedule_XForms_DragDropSettings_AllowScroll) boolean property can handle the Appointment dragging, whether scroll (below/above) the Schedule or not while dragging the appointment to the endpoint of the current view in Schedule. Default value of the `AllowScroll` property is true.

{% tabs %}
{% highlight c# %}
dragDropSettings.AllowScroll = false;
{% endhighlight %}
{% endtabs %}

### Disabling dragging time indicator
[ShowTimeIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DragDropSettings.html#Syncfusion_SfSchedule_XForms_DragDropSettings_ShowTimeIndicator) - Using this boolean property can handle the time indicator whether it should visible or not, which shows the dragged appointment current position time in time text slots. Default value of the `ShowTimeIndicator` property is true.

{% tabs %}
{% highlight c# %}
dragDropSettings.ShowTimeIndicator = false;
{% endhighlight %}
{% endtabs %}

## Customize appearance of dragging Time Indicator
Using [TimeIndicatorStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DragDropSettings.html#Syncfusion_SfSchedule_XForms_DragDropSettings_TimeIndicatorStyle) property can handle the time indicator style which contains [TextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeIndicatorStyle.html#Syncfusion_SfSchedule_XForms_TimeIndicatorStyle_TextColor), [TextSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeIndicatorStyle.html#Syncfusion_SfSchedule_XForms_TimeIndicatorStyle_TextSize) and [TextFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.TimeIndicatorStyle.html#Syncfusion_SfSchedule_XForms_TimeIndicatorStyle_TextFormat).

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule x:Name="schedule" ScheduleView="WeekView">
    <schedule:SfSchedule.DragDropSettings>
        <schedule:DragDropSettings>
            <schedule:DragDropSettings.TimeIndicatorStyle>
                <schedule:TimeIndicatorStyle TextColor="Red" TextSize="13" TextFormat="hh:mm">
                </schedule:TimeIndicatorStyle>
            </schedule:DragDropSettings.TimeIndicatorStyle>
        </schedule:DragDropSettings>
    </schedule:SfSchedule.DragDropSettings>
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
TimeIndicatorStyle timeIndicatorStyle = new TimeIndicatorStyle();
timeIndicatorStyle.TextColor = Color.Red;
timeIndicatorStyle.TextSize = 15;
timeIndicatorStyle.TextFormat = "hh : mm";
dragDropSettings.TimeIndicatorStyle = timeIndicatorStyle;
{% endhighlight %}
{% endtabs %}

![Time Indicator in schedule Xamarin Forms](PopulatingAppointments_images/timeindicator.png)

>**Notes**
* While dropping appointment to `AllDay` panel from time slots, appointment start and end time will change to 12.00 AM.
* While dropping appointment to time slots from `AllDay` panel, appointment duration will change as one (1) hour from the dropped time.
* Doesn't support control to control drag and drop.

## Get resource item at appointment drop
Using the [DropResourceItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs.html#Syncfusion_SfSchedule_XForms_AppointmentDropEventArgs_DropResourceItem) property that is in the [AppointmentDrop](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html) event, you can get the dropping ResourceItem details. It will return schedule resource item value for timeline view with resource view mode as Absolute using the property of [AppointmentDropEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.AppointmentDropEventArgs.html).

{% tabs %}
{% highlight c# %}
schedule.AppointmentDrop += Schedule_AppointmentDrop;

...

private void Schedule_AppointmentDrop(object sender, AppointmentDropEventArgs e)
{
        var changedResource = e.DropResourceItem;
        App.Current.MainPage.DisplayAlert("", "Resorce change into " + (changedResource as Employee).Name, "ok");
}
{% endhighlight %}
{% endtabs %}


## See also

[How to get dropped resource in Xamarin.Forms Schedule (SfSchedule)](https://www.syncfusion.com/kb/11179/how-to-get-dropped-resource-in-xamarin-forms-schedule-sfschedule)

[How to drag appointment to the exact hour in Schedule (SfSchedule) Xamarin.Forms](https://www.syncfusion.com/kb/11081/how-to-drag-appointment-to-the-exact-hour-in-schedule-sfschedule-xamarin-forms)
