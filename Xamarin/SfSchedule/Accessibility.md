---
layout: post
title: AutomationId | SfSchedule | Xamarin.Forms | Syncfusion
description: Set Automation Id to SfSchedule for automation framework to find and interact with control inner elements.
platform: Xamarin
control: SfSchedule
documentation: UG
---

## AutomationId

The `SfSchedule` control has built-in `AutomationId` for inner elements. Please find the following table of Automation IDs for inner elements. To keep unique `AutomationId`, these inner elements’ AutomationIds are updated based on the control’s `AutomationId`.  For example, if you set `SfSchedule` `AutomationId` as `SfSchedule.AutomationId = EventScheduler`, then the Automation framework will interact with the month header as `EventSchedulerAugust 2019`. The following screenshots denote the AutomationIds for inner elements.

### Month view

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>MonthCell</td>
<td>dddd dd/MMMM/yyyy</td>
<td>Tuesday 01/July/2019</td>
</tr>

<tr>
<td>Month Header</td>
<td>MMMM yyyy</td>
<td>August 2019</td>
</tr>

<tr>
<td>Inline View</td>
<td>Subject hh tt-hh tt dd/MMMM/yyyy</td>
<td>Consulting 10 AM-12 PM 01/July/2019</td>
</tr>

<tr>
<td>Agenda View</td>
<td>Subject hh tt-hh tt dd/MMMM/yyyy</td>
<td>Planning 10 AM-11 AM 01/July/2019</td>
</tr>

<tr>
<td>All day</td>
<td>Subject All day</td>
<td>Consulting All day</td>
</tr>

<tr>
<td>Spanning Appointment</td>
<td>Subject hh tt dd/MMMM/yyyy-hh tt dd/MMMM/yyyy</td>
<td>Planning 10 AM 12/August/2019-02 PM 18/August/2019</td>
</tr>

<tr>
<td>Resources</td>
<td>Name ResourceID</td>
<td>John 1501</td>
</tr>

<tr>
<td>No Events</td>
<td>No Events text</td>
<td>No Events</td>
</tr>

</table>

![Month view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-month-view.png)
![Month view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-month-view-allday.png)
![Month view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-month-view-spanning.png)
![Month view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-month-view-resources.png)
![Month view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-month-view-no-events.png)

### Day, week and workweek views

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>TimeslotView(Only for DayView)</td>
<td>hh a dd/MMMM/yyyy</td>
<td>09 AM 22/August/2019</td>
</tr>

<tr>
<td>Appointment</td>
<td>Subject hh tt-hh tt dd/MMMM/yyyy</td>
<td>Planning 10 AM-12 PM 01/July/2019</td>
</tr>

<tr>
<td>Header</td>
<td>MMMM yyyy</td>
<td>August 2019</td>
</tr>

<tr>
<td>ViewHeader</td>
<td>dddd dd/MMMM/yyyy</td>
<td>Sunday 22/August/2019</td>
</tr>

<tr>
<td>AllDay</td>
<td>Subject All day</td>
<td>Consulting All day</td>
</tr>

<tr>
<td>Spanning Appointment</td>
<td>Subject hh tt dd/MMMM/yyyy-hh tt dd/MMMM/yyyy</td>
<td>Planning 10 AM 12/August/2019-02 PM 18/August/2019</td>
</tr>

<tr>
<td>Resources</td>
<td>Name ResourceID</td>
<td>Brooklyn 6343</td>
</tr>

</table>

![Day view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-day-view.png)

![Day view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-day-view-resources.png)

![Day view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-day-view-spanning.png)

![Week view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-week-view.png)

![Week view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-week-view-spanning.png)

![Work week view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-work-week-view.png)

![Work week view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-workweek-view-spanning.png)

### Timeline view

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>TimeslotView(Only applicable if days count is 1)</td>
<td>hh a dd/MMMM/yyyy</td>
<td>09 AM 22/August/2019</td>
</tr>

<tr>
<td>Appointment</td>
<td>Subject hh tt-hh tt dd/MMMM/yyyy</td>
<td>Planning 10 AM-12PM 01/July/2019</td>
</tr>

<tr>
<td>Resources</td>
<td>Name ResourceID</td>
<td>Sophia 7456</td>
</tr>

<tr>
<td>Header</td>
<td>MMMM yyyy</td>
<td>August 2019</td>
</tr>

<tr>
<td>Header - DaysCount</td>
<td>dd MMMM - dd MMMM yyyy</td>
<td>04 December - 08 December 2018</td>
</tr>

<tr>
<td>ViewHeader</td>
<td>dddd dd/MMMM/yyyy</td>
<td>Sunday 22/August/2019</td>
</tr>

</table>

![Timeline view AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-timeline-view.png)
![Timeline View AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-timeline-view-header.png)
![Timeline View AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-timeline-view-resources.png)