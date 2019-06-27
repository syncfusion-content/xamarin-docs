---
layout: post
title: Xamarin Syncfusion calendar month, year, decade and century view. 
description: Calendar Xamarin.Forms displays month, year, decade and century views which allows users to easily select and navigate between all built-in views.
platform: Xamarin
control: Calendar
documentation: ug
---

# Calendar views

Xamarin.Forms calendar control provides 4 different types of views such month, year, decade and century. It allows users to easily select and navigate between all built-in views. This can be achieved by using [ViewMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~ViewMode.html) property of SfCalendar.

N> By default calendar control is assigned with month view. 

## Month view

This displays entire dates of a particular month, by default current month will be displayed on loading. The current date is provided with separate color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by four ways such as single, multiple, range and multi range selections which can be achieved using [SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~SelectionMode.html)

## Trailing and leading days

The `SfCalendar` allows you hide the days of the next month and previous month in calendar to enhance the appearance. This can be achieved by enabling the [ShowLeadingAndTrailingDays](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~ShowLeadingAndTrailingDays.html) property. The following code demonstrates how to hide the leading and trailing dates in calendar.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="MonthView" 
						ShowLeadingAndTrailingDays="True"/>

{% endhighlight %}

{% highlight c# %}

calendar.ViewMode = ViewMode.MonthView;
calendar.ShowLeadingAndTrailingDays = true; 
 
{% endhighlight %}

{% endtabs %}

![Month View in Xamarin.Forms Calendar ](images/Xamarin.Forms-Calendar-HideLeadingTrailing.png)

N>
* The OnMonthCellLoaded event is triggered for the current month dates.
* The VisibleDates in the MonthChanged event will return the current month dates.


## Month view customization

You can customize the calendar month view by using [MonthViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings.html) of `SfCalendar`.

* Current day text color can be modified using [TodayTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~TodayTextColor.html).
* The day header format, day font size, day header font size can be modified using [DayHeaderFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~DayHeaderFormat.html), [DayFontSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~DayFontSize.html), [DayHeaderFontSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~DayHeaderFontSize.html)
* The background color of the inline view can be modified using [InlineBackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~InlineBackgroundColor.html) property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar">
	<syncfusion:SfCalendar.MonthViewSettings>
		  <syncfusion:MonthViewSettings 
				CurrentMonthBackgroundColor="#800080"
				CurrentMonthTextColor="#ffffff"
				PreviousMonthBackgroundColor="#9895F0"
				PreviousMonthTextColor="#000000"
				DateSelectionColor="#ffffff"
				SelectedDayTextColor="#000000"
				DayHeaderFormat="EEEEE"
				DayFontSize="12"
				DayHeaderFontSize="14"
				TodaySelectionBackgroundColor="Green"/>
   </syncfusion:SfCalendar.MonthViewSettings>
</syncfusion:SfCalendar>  

{% endhighlight %}

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();    

MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.CurrentMonthBackgroundColor = Color.FromHex("#800080");
monthViewSettings.CurrentMonthTextColor = Color.FromHex("#ffffff");
monthViewSettings.PreviousMonthBackgroundColor = Color.FromHex("#9895F0");
monthViewSettings.PreviousMonthTextColor = Color.FromHex("#000000");
monthViewSettings.DateSelectionColor = Color.FromHex("#ffffff");
monthViewSettings.SelectedDayTextColor = Color.FromHex("#000000");
monthViewSettings.DayHeaderFormat = "EEEEE";
monthViewSettings.DayFontSize = 12;
monthViewSettings.DayHeaderFontSize = 20;
monthViewSettings.SelectionRadius = 15;
monthViewSettings.TodaySelectionTextColor= Color.Black;
monthViewSettings.TodaySelectionBackgroundColor= Color.Green;

calendar.MonthViewSettings = monthViewSettings;
this.Content = calendar;

{% endhighlight %}

{% endtabs %}

![Month View in Xamarin.Forms Calendar ](images/xamarin.forms-calendar-monthview-customization.jpg)

N> To disable the current day selection, use `TodaySelectionBackgroundColor` color as Transparent.

### Month view border color customization

You can customize the border color of calendar month view using [MonthViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings.html). The border color of month view can be customized using the [BorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~BorderColor.html) property and the lines of month cells can be enabled using the [CellGridOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~CellGridOptions.html) property.

{% tabs %}	
	
{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar">
	<syncfusion:SfCalendar.MonthViewSettings>
		  <syncfusion:MonthViewSettings BorderColor ="#ff0000" CellGridOptions="Both"/>                      
   </syncfusion:SfCalendar.MonthViewSettings>
</syncfusion:SfCalendar>  

{% endhighlight %}

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();    
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.BorderColor = Color.FromHex("#ff0000");
monthViewSettings.CellGridOptions = CellGridOptions.Both;
calendar.MonthViewSettings = monthViewSettings;
this.Content = calendar;

{% endhighlight %}

{% endtabs %}

![Month view border color in Xamarin.Forms Calendar ](images/xamarin.forms-BorderColor.png)

### Today border color customization

You can customize the today border color of calendar month cell using [MonthViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings.html). The border color of current day can be customized using the [TodayBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthViewSettings~TodayBorderColor.html) property and it is applicable for both `Fill` and `Circle` `SelectionShape`.

{% tabs %}	
	
{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar">
	<syncfusion:SfCalendar.MonthViewSettings>
		  <syncfusion:MonthViewSettings TodayBorderColor="#ff0000"/>
   </syncfusion:SfCalendar.MonthViewSettings>
</syncfusion:SfCalendar>  

{% endhighlight %}

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();    
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.TodayBorderColor = Color.FromHex("#ff0000");
calendar.MonthViewSettings = monthViewSettings;
this.Content = calendar;

{% endhighlight %}

{% endtabs %}

![Month view today border color in Xamarin.Forms Calendar ](images/xamarin.forms-TodayBorderColor.png)

## Week view

The number of weeks in the month view can be changed by setting the [NumberOfWeeksInView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~NumberOfWeeksInView.html) property in SfCalendar. By default, `NumberOfWeeksInView` starts from current week, and this can be modified using the [MoveToDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MoveToDate.html) property of calendar. It also supports all existing features such as [FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~FirstDayOfWeek.html), [MinDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MinDate.html), [MaxDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MaxDate.html), and [SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~SelectionMode.html).

N>
* Week number ranges from 1 to 6. If lesser or greater than these range is considered, `NumberOfWeeksInView` will be displayed as 6.
* Inline view considers  `NumberOfWeeksInView` as only 6. For other count, only agenda view will be displayed in calendar.
* Dynamically changing `NumberOfWeeksInView` shows the first row of month view dates. It can be handled using the `MoveToDate` property of calendar
* [ShowLeadingAndTrailingDays](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~ShowLeadingAndTrailingDays.html) is not applicable if the `NumberOfWeeksInView` is lesser than 6.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar" NumberOfWeeksInView=3/>

{% endhighlight %}

{% highlight c# %}

SfCalendar calendar = new SfCalendar();
calendar.NumberOfWeeksInView = 3;

{% endhighlight %}

{% endtabs %}

![Week view in Xamarin.Forms Calendar ](images/xamarin.forms-NumberOfWeeksInView.png)

## Year view

This displays entire dates/month of a particular year, by default current year will be displayed on loading. The Years can be changed by swiping back and forth or [Forward](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~Forward.html) and [Backward](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~Backward.html) methods. The Months can be navigated quickly by selecting on the particular month in year view.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="YearView"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar calendar = new SfCalendar();
calendar.ViewMode=ViewMode.YearView;
this.Content = calendar;
 
{% endhighlight %}

{% endtabs %}
 
![YearView in Xamarin.Forms Calendar](images/xamarin.forms-calendar-yearview-customization.jpg)

## Year view mode

You can set the year view as either date or month using [YearViewMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~YearViewMode.html). By default, current year and months will be displayed. 

* If the `YearViewMode` is date, it will be displays all the months with dates in a particular year view.
* If the `YearViewMode` is month, it will be displays all the months in a particular year view.


{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="YearView" YearViewMode="Date"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar calendar = new SfCalendar();
calendar.ViewMode=ViewMode.YearView;
calendar.YearViewMode = YearViewMode.Date;
this.Content = calendar;
 
{% endhighlight %}

{% endtabs %}

![Year view mode in Xamarin.Forms Calendar ](images/xamarin.forms-YearViewMode.png)
 
N>
* The `YearViewMode` property is only applicable for calendar in Android and iOS platforms.

## Year view customization

We can customize the calendar view in yearView mode by using [YearViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings.html) property of SfCalendar. Date text color can be modified using [DateTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~DateTextColor.html). You can also customize the header, month layout in year view's text color and background color by using the [HeaderBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~HeaderBackground.html), [LayoutBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~LayoutBackground.html), [YearHeaderTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~YearHeaderTextColor.html) properties.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar">
	<syncfusion:SfCalendar.YearViewSettings>
		<syncfusion:YearViewSettings 
			LayoutBackground="#ffe4b5"
			DateTextColor="#E6E6FA"
			HeaderBackground="#8B4513"
			YearHeaderTextColor="#FFFFFF"/>
	</syncfusion:SfCalendar.YearViewSettings>
</syncfusion:SfCalendar>    

{% endhighlight %}

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();        
YearViewSettings yearViewSettings = new YearViewSettings();
yearViewSettings.LayoutBackground = Color.FromHex("#ffe4b5");
yearViewSettings.DateTextColor = Color.FromHex("#008000");
yearViewSettings.YearHeaderTextColor = Color.FromHex("#ff0000");
calendar.YearViewSettings = yearViewSettings;
this.Content = calendar;

{% endhighlight %}

{% endtabs %}

![Year View in Xamarin.Forms Calendar ](images/xamarin.Forms-Calendar-year-view-settings.jpg)


## Decade view

This view displays the period of 10 years. By default, current year range of 10 years will be displayed on loading. You can easily navigate between month/year view to decade view by tapping the calendar header. The year can be navigated quickly by selecting a particular year from decade view.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="Decade"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar calendar = new SfCalendar();
calendar.ViewMode=ViewMode.Decade;
this.Content = calendar;
 
{% endhighlight %}	

{% endtabs %}

![Decade view in Xamarin.Forms Calendar ](images/xamarin.forms-DecadeView.png)
 
## Decade view customization

You can customize the decade view of calendar by using [YearViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings.html). 

* Year text color can be modified using [MonthHeaderTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~MonthHeaderTextColor.html).
* You can customize the decade view header text and background color by using the [YearHeaderTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~YearHeaderTextColor.html) and [HeaderBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~HeaderBackground.html) property.
* You can customize the background of decade view by using [LayoutBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~LayoutBackground.html) and [MonthLayoutBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~MonthLayoutBackground.html).


{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar">
<syncfusion:SfCalendar.YearViewSettings>
	<syncfusion:YearViewSettings 
		LayoutBackground ="#D3D3D3"
		HeaderBackground = "#F2F2F2"
		MonthHeaderTextColor ="#0000FF"
		YearHeaderTextColor="#ff0000"
		MonthLayoutBackground  ="#F2F2F2"/>
</syncfusion:SfCalendar.YearViewSettings>
</syncfusion:SfCalendar>    

{% endhighlight %}

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();        
YearViewSettings yearViewSettings = new YearViewSettings();
yearViewSettings.LayoutBackground = Color.FromHex("#D3D3D3");
yearViewSettings.MonthHeaderTextColor = Color.FromHex("#0000FF");
yearViewSettings.MonthLayoutBackground = Color.FromHex("#F2F2F2"); 
yearViewSettings.YearHeaderTextColor = Color.FromHex("#ff0000");
yearViewSettings.HeaderBackground = Color.FromHex("#F2F2F2");
calendar.YearViewSettings = yearViewSettings;
this.Content = calendar;

{% endhighlight %}

{% endtabs %}

![Decade view in Xamarin.Forms Calendar ](images/xamarin.forms-DecadeView-Custom.png)

## Century view

This view displays the period of 100 years. By default, current year range of 100 years will be displayed on loading. You can easily navigate between month/year/decade view to century view by tapping the calendar header. You can easily navigate to decade view by selecting decade years in century view.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar  x:Name="calendar" ViewMode="Century"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar calendar = new SfCalendar();
calendar.ViewMode=ViewMode.Century;
this.Content = calendar;
 
{% endhighlight %}

{% endtabs %}

![Decade view in Xamarin.Forms Calendar ](images/xamarin.form-CenturyView.png)
 
## Century view customization

You can customize the century view of calendar using [YearViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings.html). 

* Year text color can be modified using [MonthHeaderTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~MonthHeaderTextColor.html).
* You can customize the century view header text and background color by using the [YearHeaderTextColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~YearHeaderTextColor.html) and [HeaderBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~HeaderBackground.html) property.
* You can customize the background of century view by using [LayoutBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~LayoutBackground.html) and [MonthLayoutBackground](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.YearViewSettings~MonthLayoutBackground.html).


{% tabs %}

{% highlight xaml %}

<syncfusion:SfCalendar x:Name="calendar">
	<syncfusion:SfCalendar.YearViewSettings>
		<syncfusion:YearViewSettings 
			LayoutBackground ="#D3D3D3"
			HeaderBackground = "#F2F2F2"
			MonthHeaderTextColor ="#0000FF"
			YearHeaderTextColor="#ff0000"
			MonthLayoutBackground  ="#F2F2F2"/>
	</syncfusion:SfCalendar.YearViewSettings>
</syncfusion:SfCalendar>   

{% endhighlight %}

{% highlight c# %}
	
SfCalendar calendar = new SfCalendar();        
YearViewSettings yearViewSettings = new YearViewSettings();
yearViewSettings.LayoutBackground = Color.FromHex("#D3D3D3");
yearViewSettings.MonthHeaderTextColor = Color.FromHex("#0000FF");
yearViewSettings.MonthLayoutBackground = Color.FromHex("#F2F2F2"); 
yearViewSettings.YearHeaderTextColor = Color.FromHex("#ff0000");
yearViewSettings.HeaderBackground = Color.FromHex("#F2F2F2");
calendar.YearViewSettings = yearViewSettings;
this.Content = calendar;

{% endhighlight %}

{% endtabs %}

![Decade view in Xamarin.Forms Calendar ](images/xamarin.forms-CenturyView-Custom.png)



