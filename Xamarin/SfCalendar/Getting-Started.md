---
layout: post
title: Getting Started with Syncfusion Calendar control for Xamarin.Forms
description: Learn how to add libraries and to get started with Calendar control
platform: Xamarin.Forms
control: Calendar
documentation: ug
---

# Getting Started

## Create your first Calendar control in Xamarin.Forms

This section provides overview for working with Essential Calendar for Xamarin.Forms. You can walk through the entire process of creating an Calendar.

### Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.
Components/syncfusionessentialstudio-version/lib/pcl/
Alternatively, if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.
After installing Essential Studio for Xamarin, all the required assemblies found in the installation folders, typically
{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib
Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib
Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder
{download location}\syncfusionessentialstudio-version\lib
You can then add the assembly references to the respective projects as shown below

** PCL Project**

pcl\Syncfusion.SfCalendar.XForm.dll

** Android Project**

android\Syncfusion.SfCalendar.Andriod.dll

android\Syncfusion.SfCalendar.xForms.Andriod.dll

** IOS (Classic) Project**

ios\Syncfusion.SfCalendar.iOS.dll

ios\Syncfusion.SfCalendar.xForms.iOS.dll

ios\Syncfusion.SfCalendar.XForm.dll

**IOS (Unified) Project**

ios-unified\Syncfusion.SfCalendar.iOS.dll

ios-unified\Syncfusion.SfCalendar.xForms.iOS.dll

ios-unified\Syncfusion.SfCalendar.XForm.dll

** Windows Phone Project**

wp8\Syncfusion.SfCalendar.WP8.dll

wp8\Syncfusion.SfCalendar.xForms.WinPhone.dll

### Add and Configure the Calendar

The Calendar control configured entirely in C# code or by using XAML markup.The following steps explain on how to create an Calendar and configure its elements,

* Create an instance of SfCalendar.

	SfCalendar sfCalendar=new SfCalendar();

* Configure the properties of Calendar.

    {% highlight C# %}
	
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




##Creating your first Calendar in Xamarin.iOS.

This section provides a quick overview to work with the Calendar in Objective C. This example explains how to create an Calendar with different CalendarModes and SuggestionModes.

### Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:
{Syncfusion Installed location}\Essential Studio {version number}\lib
You have to add the following assembly reference to the iOS classic project
ios\Syncfusion.SfCalendar.iOS.dll
And below assembly reference to the iOS unified project.
ios-unifed\Syncfusion.SfCalendar.iOS.dll

![](images/Calendar-iOS.png) 

### And and Configure the Calendar

The following steps explain on how to create an Calendar and configure its elements,

*Create an instance of SfCalendar
   
    {% highlight C# %}
	
	@interface ViewController ()
	{     SfCalendar *_calendar;
	} 
	- (void)viewDidLoad 
	{     
	[super viewDidLoad];   
	_calendar=[[ SfCalendar alloc]init];  
	[self.view addSubview:SfCalendar]; 
	}
	
	{% endhigh%}

*Configure the properties for Calendar. 

    {% highlight C# %}
	
	_calendar.ViewMode = SFCalendarViewMode.SFCalendarViewModeMonth;
	_calendar.Locale =  new NSLocale("fr-FR")
	_calendar.SelectionMode = SFCalenderSelectionMode.SFCalenderSelectionModeSingle;
	_calendar.TransitionMode = SFCalendarTransitionModee. SFCalendarTransitionModeFloat; 
	NSDate today = new NSDate ();
	NSCalendar calendar = NSCalendar.CurrentCalendar;
	// Get the year, month, day from the date
	NSDateComponents components = calendar.Components (NSCalendarUnit.Year | NSCalendarUnit.Month | NSCalendarUnit.Day, today);
	// Set the hour, minute, second
	schedule.BlackoutDates = new NSMutableArray ();
	components.Day -= 10;
	for (int i = 0; i < 5; i++) {
	NSDate startDate = calendar.DateFromComponents (components);
	components.Day += 5;
	schedule.BlackoutDates.Add (startDate);
	}
	
	{% endhighlight %}





    
                                    
