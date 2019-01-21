---
layout: post
title: MVVM | Calendar for Xamarin.Forms | Syncfusion
description: Describes how to use calendar in different cases of MVVM.
platform: xamarin
control: SfCalendar
documentation: ug
---

# MVVM

# Commands
 
## Tap command
 
The [TapCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.TapCommand.html) will be triggered whenever tapping the calendar cell and passing the [CalendarTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.CalendarTappedEventArgs.html) as parameter.

{% tabs %}
{% highlight xaml %} 
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
			 xmlns:local="clr-namespace:CalendarTestBedSample" x:Class="CalendarSample.MainPage" 
			 xmlns:syncfusion="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms">
    <calendar:SfCalendar x:Name="calendar"  TapCommand="{Binding CalendarCellTapped}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public class CalendarViewModel
{
  private string commandText;
  
  public string CommandText
  {
	get { return commandText; }
	set { commandText = value; }
  }
  
  public ICommand CalendarCellTapped { get; set; }
   
  public CalendarViewModel()
  {
	CalendarCellTapped = new Command<CalendarTappedEventArgs>(CellTapped);
  }
   
  private void CellTapped(CalendarTappedEventArgs obj)
  {
	CommandText = obj.DateTime.ToString("dd/MM/yyyy") + " " + obj.SelectedAppointment.ToString();
  }
 
}
{% endhighlight %}
{% endtabs %} 

## Hold command

The [HoldCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.HoldCommand.html) will be triggered whenever the calendar cell is long pressed and passing the [DayCellHoldingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.DayCellHoldingEventArgs.html) as parameter.

{% tabs %}
{% highlight xaml %} 
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
			 xmlns:local="clr-namespace:CalendarTestBedSample" x:Class="CalendarSample.MainPage" 
			 xmlns:syncfusion="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms">
    <calendar:SfCalendar x:Name="calendar"  HoldCommand="{Binding OnDateCellHolding}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public class CalendarViewModel
{
  private string commandText;
  
  public string CommandText
  {
	get { return commandText; }
	set { commandText = value; }
  }
  
  public ICommand OnDateCellHolding { get; set; }
   
  public CalendarViewModel()
  {
	OnDateCellHolding = new Command<DateTime>(DateCellHolding);
  }
   
  private void DateCellHolding(DateTime obj)
  {
	CommandText = obj.Date.ToString("dd/MM/yyyy");
  }
 
}
{% endhighlight %}
{% endtabs %} 

## Month changed command

The [MonthChangedCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthChangedCommand.html) will be triggered whenever the navigating between month and Forward()/bacward() is called in calendar and passing the [MonthChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.MonthChangedEventArgs.html) as parameter.

{% tabs %}
{% highlight xaml %} 
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:CalendarTestBedSample" x:Class="CalendarSample.MainPage" 
			 xmlns:syncfusion="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms">
    <calendar:SfCalendar x:Name="calendar"  MonthChangedCommand="{Binding OnMonthChanged}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public class CalendarViewModel
{
  private string commandText;
  public string CommandText
  {
	get { return commandText; }
	set { commandText = value; }
  }
  
  public ICommand OnMonthChanged { get; set; }
   
  public CalendarViewModel()
  {
	OnMonthChanged = new Command<MonthChangedEventArgs>(MonthChanged);
  }
   
  private void MonthChanged(MonthChangedEventArgs obj)
  {
	CommandText =" CurrentMonth -"+ " " +obj.CurrentValue.ToString("dd/MM/yyyy") +"  "+" PreviousMonth - "+"  " +  obj.PreviousValue.ToString("dd/MM/yyyy") +"  "+" VisibleDate  - "+ " "+ obj.VisibleDates[0].Date.ToString("dd/MM/yyyy");
  }
}
{% endhighlight %}
{% endtabs %} 

## Selection changed command

The [SelectionChangedCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SelectionChangedCommand.html) will be triggered whenever the selection is changed in calendar for the following selections and passing the [SelectionChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfcalendar/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SelectionChangedEventArgs.html) as parameter.
    
	* SingleSlection - A single date can be selected in a month view which can be equipped when user needs to select one date at a time
	* MultiSelection - More than one date can be selected.
	* RangeSelection - It allows us to select a single date range in calendar month view.
	* MultiRangeSelection - More than one date range can be selected in a month view.

{% tabs %}
{% highlight xaml %} 
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:CalendarTestBedSample" x:Class="CalendarSample.MainPage" 
			 xmlns:syncfusion="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms">
    <calendar:SfCalendar x:Name="calendar"  SelectionChangedCommand="{Binding OnSelectionChanged}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
public class CalendarViewModel
{
  private string selectionChangedCommandText;
  public string SelectionChangedCommandText
  {
	get { return selectionChangedCommandText; }
	set { selectionChangedCommandText = value; }
  }
  
  public ICommand OnSelectionChanged { get; set; }
   
  public CalendarViewModel()
  {
	OnSelectionChanged = new Command<SelectionChangedEventArgs>(SelectionChanged);
  }
   
  private void SelectionChanged(SelectionChangedEventArgs obj)
  {
	SelectionChangedCommandText = " DateAdded- " +obj.DateAdded?.Count.ToString() +"  "+ " DateRemoved- " + obj.DateRemoved?.Count.ToString() + "  " + " NewRageAdded -"
	  + obj.NewRangeAdded?.Count.ToString();
  }
}
    
{% endhighlight %}
{% endtabs %} 
