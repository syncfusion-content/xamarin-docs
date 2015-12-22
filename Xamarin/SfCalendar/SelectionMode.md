---
layout: post
title: Selection
description: Learn how to do the selection in Calendar
platform: Xamarin.Forms
control: Calendar
documentation: ug
---
#Selection

Dates can be selected by making a touch on month view cells. The default Selection mode is Single which allows user to select one date at a time. Calendar provides support to select dates in three modes such as single, multiple and range selection.

* `SingleSelection` – A single date can be selected in a month view which can be equipped when user needs to select one date at a time / to view events.

* `MultiSelection` – More than one date can be selected in a random manner. Clicking again on selected dates can do deselection.

* `RangeSelection` – Range of dates can be selected by dragging on the date cells.

The selected dates can be retrieved through `CalendarTappedListner` which is raised on selecting.

    {% highlight C# %}
	
	sfCalendar.SelectionMode=SelectionMode.SingleSelection;
	
	{% endhighlight %}

N>In range selection, navigation through swipe will be restricted and moving between months can be done by clicking on navigation button available at top corners of calendar control.

![](images/Selection.png)