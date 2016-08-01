---
layout: post
title: Getting Started with Syncfusion Calendar control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion calendar control for Xamarin.Forms platform
platform: Xamarin
control: Calendar
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfCalendar control in a real-time scenario and also provides a walk-through on some of the customization features available in Calendar control.


## Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below.

### PCL 

pcl\Syncfusion.SfCalendar.XForms.dll


### Android 

android\Syncfusion.SfCalendar.Android.dll
android\Syncfusion.SfCalendar.XForms.Android.dll
android\Syncfusion.SfCalendar.XForms.dll

### iOS 

iOS-unified\Syncfusion.SfCalendar.iOS.dll
iOS-unified\Syncfusion.SfCalendar.XForms.iOS.dll
iOS-unified\Syncfusion.SfCalendar.XForms.dll

### Windows Phone

wp8\Syncfusion.SfInput.WP8.dll
wp8\Syncfusion.SfShared.WP8.dll
wp8\Syncfusion.SfCalendar.XForms.dll
wp8\Syncfusion.SfCalendar.XForms.WinPhone.dll

### Windows Phone 8.1

wp81\Syncfusion.SfInput.WP.dll
wp81\Syncfusion.SfShared.WP.dll
wp81\Syncfusion.SfCalendar.XForms.dll
wp81\Syncfusion.SfCalendar.XForms.WinPhone.dll

### WinRT

winrt\Syncfusion.SfInput.WinRT.dll
winrt\Syncfusion.SfShared.WinRT.dll
winrt\Syncfusion.SfCalendar.XForms.dll
winrt\Syncfusion.SfCalendar.XForms.WinRT.dll

### UWP 

uwp\Syncfusion.SfInput.UWP.dll
uwp\Syncfusion.SfShared.UWP.dll
uwp\Syncfusion.SfCalendar.XForms.dll
uwp\Syncfusion.SfCalendar.XForms.UWP.dll


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

## Add SfCalendar

The following steps helps to add a SfCalendar control through code.

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

## Enabling Multiple Selection 

To enable multiple selection, change the selection type using `SelectionMode` property. Check the [Selection Mode](http://help.syncfusion.com/xamarin/sfcalendar/restrict-dates-from-selection#range-of-min--max-dates)  section for more details.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar x:Name="calendar" SelectionMode="MultiSelection" />

{% endhighlight %}

{% highlight c# %}

	SfCalendar calendar = new SfCalendar ();
	calendar.SelectionMode=SelectionMode.MultiSelection;

{% endhighlight %}

{% endtabs %}

## Setting Blackout Dates

Add the dates into `BlackOutDates` property, which needs to be disabled among visible dates. Check the [BlackOutDates](http://help.syncfusion.com/android/sfcalendar/blackoutdates) section for more details.

For instance add all the holiday dates to blackout dates property.


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



## Restricting Dates

Set `MinDate` and `MaxDate` property to limit visible dates range. Check the [Min Max dates](http://help.syncfusion.com/xamarin/sfcalendar/datenavigation-and-gesture#min-max-dates) section for more details.

{% tabs %}

{% highlight xaml %}

	<CalendarSample:SfCalendar  x:Name="calendar" SelectionMode="MultiSelection" MinDate="2014,4,1" MaxDate="2018,4,1"/>

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
	calendar.MaxDate = new DateTime(2018,4,1);
	
{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)