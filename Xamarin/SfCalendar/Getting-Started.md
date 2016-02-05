---
layout: post
title: Getting Started with Syncfusion Calendar control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion calendar control for Xamarin.Forms platform
platform: Xamarin.Forms
control: Calendar
documentation: ug
---

# Getting Started

This section explains you the steps to configure a Calendar control in a real-time scenario and also provides a walk-through on some of the customization features available in Calendar control.

![](images/gettingstarted.png)

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.
Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively, if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies found in the installation folders, typically
{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib
Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder
{download location}\syncfusionessentialstudio-version\lib
You can then add the assembly references to the respective projects as shown below

**PCL Project**

pcl\Syncfusion.SfCalendar.XForm.dll

**Android Project**

android\Syncfusion.SfCalendar.Android.dll

android\Syncfusion.SfCalendar.xForms.Android.dll

**IOS (Classic) Project**

ios\Syncfusion.SfCalendar.iOS.dll

ios\Syncfusion.SfCalendar.xForms.iOS.dll

ios\Syncfusion.SfCalendar.XForm.dll

**IOS (Unified) Project**

ios-unified\Syncfusion.SfCalendar.iOS.dll

ios-unified\Syncfusion.SfCalendar.xForms.iOS.dll

ios-unified\Syncfusion.SfCalendar.XForm.dll

**Windows Phone Project**

wp8\Syncfusion.SfCalendar.WP8.dll

wp8\Syncfusion.SfCalendar.xForms.WinPhone.dll

## Add and Configure the Calendar

* Adding reference to calendar.

{% highlight c# %}

	using Syncfusion.SfCalendar.XForms;

{% endhighlight %}

* Create an instance of SfCalendar.

{% highlight c# %}

	SfCalendar sfCalendar=new SfCalendar();
	SetContentView(sfCalendar);
	
{% endhighlight %}

## Calendar Customization

{% highlight c# %}
	
	SfCalendar sfCalendar = new SfCalendar ();
	sfCalendar.ViewMode=ViewMode.MonthView;
	DateTime d1=new DateTime(2015,1,1);
	sfCalendar.MinDate=mindate;
	DateTime d2=new DateTime(2040,12,12);
	sfCalendar.MaxDate=d2;
	sfCalendar.SelectionMode=SelectionMode.SingleSelection;
	List<DateTime> black_dates = new List<DateTime>();
	black_dates.Add (new DateTime(2015,11,3));
	black_dates.Add (new DateTime(2015,11,7));
	black_dates.Add (new DateTime(2015,11,15));
	black_dates.Add (new DateTime(2015,11,16));
	black_dates.Add (new DateTime(2015,11,26));
	black_dates.Add (new DateTime(2015,11,30));
	sfCalendar.BlackoutDates= black_dates ;
	sfCalendar.ShowInlineEvents=True;
	sfCalendar.Locale= new System.Globalization.CultureInfo("zh-CN");
	sfCalendar.TransitionMode=TransitionMode.Float;
	//MonthView Setting
	MonthViewSettings monthViewSettings = new MonthViewSettings();
	monthViewSettings.TodayTextColor=Color.ParseColor("#1B79D6");
	monthViewSettings.InlineBackgroundColor=Color.ParseColor("#E4E8ED");
	monthViewSettings.SetWeekDayBackGroundColor(Color.ParseColor("#F7F7F7"));
	sfCalendar.MonthViewSettings=monthViewSettings;
	
{% endhighlight %}




