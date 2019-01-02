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

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfchart) link to know about the assemblies required for adding Calendar to your project.

## Launching the SfCalendar on each platform

To use SfCalendar inside an application, each platform application must initialize the SfCalendar renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and  UWP

The Android and UWP launches the SfCalendar without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

### iOS

To launch SfCalendar in iOS, need to create an instance of SfCalendarRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
	global::Xamarin.Forms.Forms.Init();

	new SfCalendarRenderer();

	LoadApplication(new App());

	return base.FinishedLaunching(app, options);
}

{% endhighlight %}

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfCalendar assemblies in `App.xaml.cs` in UWP project as like in below code snippet.

{% highlight C# %}

// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
…

	rootFrame.NavigationFailed += OnNavigationFailed;
		
	// you'll need to add `using System.Reflection;`
	List<Assembly> assembliesToInclude = new List<Assembly>();

	//Now, add all the assemblies your app uses
	assembliesToInclude.Add(typeof(SfCalendarRenderer).GetTypeInfo().Assembly);

	// replaces Xamarin.Forms.Forms.Init(e);        
	Xamarin.Forms.Forms.Init(e, assembliesToInclude);
		
…     
}
{% endhighlight %}
### Create a Simple SfCalendar

The SfCalendar control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfCalendar and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

xmlns:CalendarSample="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms"
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfCalendar.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfCalendar control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms"
	x:Class="GettingStarted.CalendarPage">
<ContentPage.Content>
 <syncfusion:SfCalendar x:Name="calendar" />	
</ContentPage.Content>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfCalendar.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
public partial class CalendarPage : ContentPage
{
	public CalendarPage()
	{
		InitializeComponent();

		SfCalendar calendar = new SfCalendar();

		this.Content = calendar;
	}
}
}
{% endhighlight %}

{% endtabs %}

## Set Blackout Dates

SfCalendar control provides option to black out the desired date which is in disabled state among the visible dates. Here, holidays are blacked out in the form which cannot be selected by the user. To black out the holiday, add them into `BlackoutDates` list. 

{% highlight c# %}

SfCalendar  calendar = new SfCalendar();

List<DateTime> black_dates = new List<DateTime>();

for (int i = 0; i < 5; i++)
{
	DateTime date = new DateTime(2018,4,1+i);
	black_dates.Add(date);
}

calendar.BlackoutDates = black_dates;

{% endhighlight %}

## Enable Multiple Selection

SfCalendar control allows user to select one or more dates at a time among the non black out dates.

To enable it set `MultiSelection` option in SelectionMode enumeration property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar" SelectionMode="MultiSelection" />

{% endhighlight %}

{% highlight c# %}

SfCalendar calendar = new SfCalendar();

calendar.SelectionMode=SelectionMode.MultiSelection;

{% endhighlight %}

{% endtabs %}

## Restrict Dates

SfCalendar allows to select dates that falls between certain range of dates. Here, restrict user to select dates only in current year.

N> To specify the range, set start date and end date to `MinDate` and `MaxDate` properties respectively.

{% highlight c# %}

SfCalendar  calendar = new SfCalendar();

calendar.MinDate = new DateTime(2014,4,1);
calendar.MaxDate = new DateTime(2018,4,1);

this.Content = calendar;
	
{% endhighlight %}


![](images/GS.png)

You can download the entire source code of this demo for Xamarin.Forms from
here [CalendarGettingStarted](https://github.com/SyncfusionExamples/xamarin-calendar-getting-started)