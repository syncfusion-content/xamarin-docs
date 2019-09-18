---
layout: post
title: AutomationId | SfSchedule | Xamarin.Forms | Syncfusion
description: Learn how to use automationid support
platform: Xamarin
control: SfSchedule
documentation: ug
---

# AutomationId

The `SfSchedule` control has built-in `AutomationId` for inner elements. Please find the following table of Automation IDs for inner elements.

## Month View

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>MonthCell</td>
<td>dd/MMMM/yyyy</td>
<td>01/July/2019</td>
</tr>

<tr>
<td>Month Header</td>
<td>MMMM yyyy</td>
<td>August 2019</td>
</tr>

<tr>
<td>Inline View</td>
<td>hh a Subject dd/MMMM/yyyy</td>
<td>10 AM Consulting 22/August/2019</td>
</tr>

<tr>
<td>Agenda View</td>
<td>hh a Subject dd/MMMM/yyyy</td>
<td>11 AM Planning 22/August/2019</td>
</tr>

<tr>
<td>No Events</td>
<td>No Events text</td>
<td>No Events</td>
</tr>

</table>

## Day View / Week View / Work Week View

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
<td>hh a Subject dd/MMMM/yyyy</td>
<td>10 AM Consulting 22/August/2019</td>
</tr>

<tr>
<td>Header</td>
<td>MMMM yyyy</td>
<td>August 2019</td>
</tr>

<tr>
<td>ViewHeader</td>
<td>ddd dd/MMMM/yyyy</td>
<td>Sunday 22/August/2019</td>
</tr>

<tr>
<td>AllDay</td>
<td>hh a Subject dd/MMMM/yyyy</td>
<td>10 AM Consulting 22/August/2019</td>
</tr>

</table>

## Timeline View

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>TimeslotView(Only applicable dayscount is 1)</td>
<td>hh a dd/MMMM/yyyy</td>
<td>09 AM 22/August/2019</td>
</tr>

<tr>
<td>Appointment</td>
<td>hh a Subject dd/MMMM/yyyy</td>
<td>10 AM Consulting 22/August/2019</td>
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
<td>ddd dd/MMMM/yyyy</td>
<td>Sunday 22/August/2019</td>
</tr>

</table>

To keep unique `AutomationID`, these inner elements’ AutomationIds are updated based on the control’s `AutomationId`.  For example, if you set `SfSchedule` `AutomationId` as “SfSchedule.AutomationId = “EventScheduler””, then the Automation framework will interact with the month header as `EventSchedulerAugust 2019`. The following screenshots denote the AutomationIds for inner elements.

## MonthView 
![MonthView AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-month-view.png)
![MonthView AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-month-view-no-events.png)

## DayView
![DayView AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-day-view.png)

## WeekView
![WeekView AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-week-view.png)

## WorkWeekView
![WorkWeekView AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-work-week-view.png)

## TimelineView
![TimelineView AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-timeline-view.png)
![TimelineView AutomationId support in Xamarin.Forms Schedule](automationid_images/xamarin-forms-schedule-timeline-view-header.png)