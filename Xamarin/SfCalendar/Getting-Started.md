---
layout: post
title: Getting Started with Syncfusion Calendar control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion calendar control for Xamarin.Forms platform
platform: Xamarin
control: Calendar
documentation: ug
---

# Getting Started

This section explains how to implement simple holiday indicator application which allows user to select working days using SfCalendar control.

## Add SfCalendar

You can then add the assembly references to the respective projects as shown below.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfCalendar.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfCalendar.Android.dll<br/>android\Syncfusion.SfCalendar.XForms.Android.dll<br/>android\Syncfusion.SfCalendar.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfCalendar.iOS.dll<br/>iOS-unified\Syncfusion.SfCalendar.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfCalendar.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfCalendar.XForms.dll<br/>wp8\Syncfusion.SfCalendar.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfCalendar.XForms.dll<br/>wp81\Syncfusion.SfCalendar.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfCalendar.XForms.dll<br/>winrt\Syncfusion.SfCalendar.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfCalendar.XForms.dll<br/>uwp\Syncfusion.SfCalendar.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the calendar custom renderer as shown below. 

Create an instance of SfCalendarRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfCalendarRenderer();
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfCalendarRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfCalendarRenderer ();
}	

{% endhighlight %}

{% endtabs %}


* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:CalendarSample="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms"/>
	
{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfCalendar.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfCalendar control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar x:Name="calendar"/>
	
{% endhighlight %}

{% highlight c# %}

	SfCalendar calendar=new SfCalendar();
	this.Content=calendar;
	
{% endhighlight %}

{% endtabs %}

## Setting Blackout Dates

SfCalendar control provides option to black out the desired date which is in disabled state among the visible dates. Here, holidays are blacked out in the form which cannot be selected by the user. To black out the holiday, add them into `BlackoutDates` list. 

N> Check the [BlackOutDates](http://help.syncfusion.com/android/sfcalendar/blackoutdates) section for more details.

{% tabs %}

{% highlight c# %}

	SfCalendar  calendar = new SfCalendar ();
	calendar.SelectionMode=SelectionMode.MultiSelection;
	List<DateTime> black_dates = new List<DateTime>();
	for (int i = 0; i < 5; i++)
	{
		DateTime date = DateTime.Now.Date.AddDays(i+7);
		black_dates.Add(date);
    }
	calendar.BlackoutDates = black_dates;

{% endhighlight %}

{% endtabs %}

## Enabling Multiple Selection 

SfCalendar control allows user to select one or more dates at a time among the non black out dates.

To enable it set `MultiSelection` option in SelectionMode enumeration property.

N> Check the [Selection Mode](http://help.syncfusion.com/xamarin/sfcalendar/select-multiple-dates)  section for more details.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar x:Name="calendar" SelectionMode="MultiSelection" />

{% endhighlight %}

{% highlight c# %}

	SfCalendar calendar = new SfCalendar ();
	calendar.SelectionMode=SelectionMode.MultiSelection;

{% endhighlight %}

{% endtabs %}



## Restricting Dates

SfCalendar control provides option to set visible dates range from minimum date to maximum date. All the other dates in the SfCalendar are in disabled state. This can be done by using the properties named `MinDate` and `MaxDate`. Check the [Min Max dates](http://help.syncfusion.com/xamarin/sfcalendar/restrict-dates-from-selection#range-of-min--max-dates) section for more details.

Following example shows how to set particular period of time the employee is working in a company.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" SelectionMode="MultiSelection" MinDate="2014,4,1" MaxDate="2016,4,1"/>

{% endhighlight %}

{% highlight c# %}

	SfCalendar  calendar = new SfCalendar ();
	calendar.SelectionMode=SelectionMode.MultiSelection;
	List<DateTime> black_dates = new List<DateTime>();
	for (int i = 0; i < 5; i++)
	{
		DateTime date = DateTime.Now.Date.AddDays(i+7);
		black_dates.Add(date);
    }
	calendar.BlackoutDates = black_dates;
	calendar.MinDate = new DateTime(2014,4,1);
	calendar.MaxDate = new DateTime(2016,4,1);
	
{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)