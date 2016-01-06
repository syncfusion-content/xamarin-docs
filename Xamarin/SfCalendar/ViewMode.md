---
layout: post
title: Accessing View modes in Syncfusion Calendar control for Xamarin.Forms
description: Learn how to set month view and year view in Calendar
platform: Xamarin.Forms
control: Calendar
documentation: ug
---
# Built-in Views

Calendar control provides two types of views to display dates such as month view and year view. It can be assigned to the calendar control by using view mode property.

By default calendar control is assigned with month view. Based on the user’s preference calendar viewed in any of the available two type.

## Month View

This displays entire dates of a particular month, by default current month will be displayed on loading. The current date is provided with seperate color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by three ways such as single, multiple and range which can be modified using `SelectionMode`

{% highlight C# %}

sfCalendar.ViewMode=ViewMode.MonthView;
 
{% endhighlight %}
 
![](images/Month View.png)
 
## Month view Settings

*Current day text color can be modified using `TodayTextColor`.

*The month view label settings class has the APIs to change date text size, day text size and format options are available.

*The background color of the inline view can be modified using `InlineBackgroundColor` property.

*The blackoutdate color can be modified with `BlackOutColor` property.

    {% highlight C# %}
	
	MonthLabelSettings labelsettings = new MonthLabelSettings();
	labelSettings.DateFormat = “dd”;
	labelSettings.DayLabelSize = 20;
	labelSettings.DayFormat = "EEE";
	labelSettings.DateLabelSize =  12;
	MonthViewSettings monthViewSettings = new MonthViewSettings();
	monthViewSettings.TodayTextColor=Color.ParseColor("#1B79D6");
	monthViewSettings.InlineBackgroundColor=Color.ParseColor("#E4E8ED");
	monthViewSettings.SetWeekDayBackGroundColor(Color.ParseColor("#F7F7F7"));
	monthviewSettings.MonthLabelSettings = labelSettings;
	sfCalendar.MonthViewSettings=monthViewSettings;
	
	{% endhighlight %}


Similar way there are many settings available to modify Text and Background colors of month view in `MonthViewSettings` class.


