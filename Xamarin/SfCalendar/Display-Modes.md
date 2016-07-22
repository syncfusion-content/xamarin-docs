---
layout: post
title: Accessing View modes in Syncfusion Calendar control for Xamarin.Forms
description: Learn how to set month view and year view in Calendar
platform: Xamarin
control: Calendar
documentation: ug
---

# Display Modes

Calendar control provides two types of views to display dates such as month view and year view. It can be assigned to the SfCalendar control by using `ViewMode` property.

By default SfCalendar control is assigned with month view. Based on the user’s preference SfCalendar can be viewed in any of the available two type.

## Month View

This displays entire dates of a particular month, by default current month will be displayed on loading. The current date is provided with separate color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by three ways such as single, multiple and range which can be modified using `SelectionMode`

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" ViewMode="MonthView"/>

{% endhighlight %}

{% highlight c# %}

	sfCalendar.ViewMode=ViewMode.MonthView;
 
{% endhighlight %}

{% endtabs %}
 
![](images/Month View.png)
 
### Month view Settings

* Current day text color can be modified using `TodayTextColor`.

* The month view label settings class has the APIs to change date text size, day text size and format options.

* The background color of the inline view can be modified using `InlineBackgroundColor` property.

* The BlackOutDate color can be modified with `BlackOutColor` property.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="monthViewSettings" TodayTextColor="Red" InlineBackgroundColor="Blue" WeekDayBackGroundColor="Yellow" MonthViewSettings="monthviewSettings"/>

{% endhighlight %}

{% highlight c# %}
	
	MonthLabelSettings labelSettings = new MonthLabelSettings();
	labelSettings.DateFormat = “dd”;
	labelSettings.DayLabelSize = 20;
	labelSettings.DayFormat = "EEE";
	labelSettings.DateLabelSize =  12;
	MonthViewSettings monthViewSettings = new MonthViewSettings();
	monthViewSettings.TodayTextColor=Color.ParseColor("#1B79D6");
	monthViewSettings.InlineBackgroundColor=Color.ParseColor("#E4E8ED");
	monthViewSettings.WeekDayBackGroundColor(Color.ParseColor("#F7F7F7"));
	monthviewSettings.MonthLabelSettings = labelSettings;
	sfCalendar.MonthViewSettings=monthViewSettings;
	
{% endhighlight %}

{% endtabs %}

N> Similar way there are many settings available to modify Text and Background colors of month view in `MonthViewSettings` class.

## YearView

This displays entire dates/month of a particular year, by default current year will be displayed on loading. The Years can be changed by swiping back and forth or `forward` and `backward` methods. The Months can be navigated quickly by selecting on the particular month in year view.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" ViewMode="YearView"/>

{% endhighlight %}

{% highlight c# %}

	calendar.ViewMode=ViewMode.YearView;
	
{% endhighlight %}

{% endtabs %}

![](images/Year View.png)  

### Year View Settings

* The Month header color can be modified using `MonthHeaderTextColor` property in similar way, year header and date text color can be changed using `YearTextColor` and `DateTextColor` properties respectively. 
* The gravity of the month name can be modified using `LabelAlignment` property, to position it to Left, Right or Center. 
* The complete layout’s background color can be modified using `YearLayoutBackground` property.   

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" YearHeaderTextColor="Red" MonthHeaderBackground="Green" DateTextColor="Blue" HeaderLabelAlignment="Center" YearViewSettings="yearViewSettings" />

{% endhighlight %}

{% highlight c# %}

	SfCalendar calendar = new SfCalendar();
	YearViewSettings yearViewSettings = new YearViewSettings();
	yearViewSettings.YearHeaderTextColor=Color.parseColor("#1B79D6");
	yearViewSettings.MonthHeaderBackground=Color.parseColor("#E4E8ED");
	yearViewSettings.DateTextColor=Color.RED;
	yearViewSettings.HeaderLabelAlignment=LabelAlignment.Center;
	calendar.YearViewSettings=yearViewSettings;

{% endhighlight %}   

{% endtabs %}                               

