---
layout: post
title: MVVM | Calendar for Xamarin.Forms | Syncfusion
description: Describes how to use Syncfusion calendar (SfCalendar) in different cases of MVVM and describes about the commands.
platform: xamarin
control: SfCalendar
documentation: ug
---

# Binding Properties in MVVM Pattern
## Binding SelectedDate

Calendar supports selecting a date programmatically by binding the [SelectedDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_SelectedDate) property from your view model.

{% tabs %}
{% highlight c# %} 
calendar.SetBinding(SfCalendar.SelectedDateProperty, new Binding("SelectedDate", BindingMode.TwoWay));
{% endhighlight %}
{% highlight xaml %} 
XAML:
<calendar:SfCalendar x:Name="calendar"
                     ShowInlineEvents="True"
                     SelectionMode="SingleSelection"
                     SelectedDate="{Binding SelectedDate, Mode=TwoWay}">
</calendar:SfCalendar>
{% endhighlight %}
{% endtabs %}

The following code sample demonstrates the ViewModel class.

{% tabs %}
{% highlight c# %} 
public class MainViewModel 
{
    public DateTime SelectedDate { get; set; }

    public MainViewModel()
    {
        SelectedDate = new DateTime(2019, 02, 05);
    }
}
{% endhighlight %}
{% endtabs %}

>**NOTE**
* You can bind the `SelectedDate` property only when the [SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_SelectionMode) is set to SingleSelection in calendar.

## Binding SelectedDates

Calendar supports selecting dates programmatically by binding the [SelectedDates](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_SelectedDates) property from your view model with the `List<DateTime>` type.

{% tabs %}
{% highlight c# %} 
calendar.SetBinding(SfCalendar.SelectedDatesProperty, new Binding("SelectedDates", BindingMode.TwoWay));
{% endhighlight %}
{% highlight xaml %} 
<calendar:SfCalendar x:Name="calendar"
                     ShowInlineEvents="True"
                     SelectionMode="MultiSelection"
                     SelectedDates="{Binding SelectedDates, Mode=TwoWay}">
</calendar:SfCalendar>
{% endhighlight %}
{% endtabs %}

The following code sample demonstrates the ViewModel class.

{% tabs %}
{% highlight c# %}
public class MainViewModel
{
    public List<DateTime> SelectedDates { get; set; }

    public MainViewModel()
    {
        SelectedDates = new List<DateTime>();
        SelectedDates.Add(new DateTime(2019, 02, 05));
        SelectedDates.Add(new DateTime(2019, 02, 08));
        SelectedDates.Add(new DateTime(2019, 02, 10));
        SelectedDates.Add(new DateTime(2019, 02, 14));
        SelectedDates.Add(new DateTime(2019, 02, 20));
    }

}
{% endhighlight %}
{% endtabs %}

>**NOTE**
* You can bind the `SelectedDates` property only when `SelectionMode` is set to `MultiSelection` in calendar.

## Binding SelectedRange
The calendar supports selecting a range of dates programmatically by binding the [SelectedRange](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_SelectedRange) property with the [SelectionRange](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html) type from your view model.

{% tabs %}
{% highlight c# %}
calendar.SetBinding(SfCalendar.SelectedRangeProperty, new Binding("SelectedRange", BindingMode.TwoWay));
{% endhighlight %}
{% highlight xaml %}
<calendar:SfCalendar x:Name="calendar"
                     ShowInlineEvents="True"
                     SelectionMode="RangeSelection"
                     SelectedRange ="{Binding SelectedRange, Mode=TwoWay}">
</calendar:SfCalendar>
{% endhighlight %}
{% endtabs %}

The following code sample demonstrates the ViewModel class.

{% tabs %}
{% highlight c# %}
public class MainViewModel
{
    public SelectionRange SelectedRange { get; set; }

    public MainViewModel()
    {
        SelectedRange = new SelectionRange();
        SelectedRange.StartDate = new DateTime(2019, 02, 10);
        SelectedRange.EndDate = new DateTime(2019, 02, 20);
    }
}
{% endhighlight %}
{% endtabs %}

Calendar supports selecting multiple ranges of dates programmatically by binding the `SelectedRange` property with `ObservableCollection<SelectionRange>` type from your view model.

{% tabs %}
{% highlight c# %}
calendar.SetBinding(SfCalendar.SelectedRangeProperty, new Binding("SelectedRanges", BindingMode.TwoWay));
{% endhighlight %}
{% highlight xaml %}
<calendar:SfCalendar x:Name="calendar"
                     ShowInlineEvents="True"
                     SelectionMode="MultiRangeSelection"
                     SelectedRange ="{Binding SelectedRanges, Mode=TwoWay}">
</calendar:SfCalendar>
{% endhighlight %}
{% endtabs %}

The following code sample demonstrates the ViewModel class.

{% tabs %}
{% highlight c# %}
public class MainViewModel
{
    public ObservableCollection<SelectionRange> SelectedRanges { get; set; }

    public MainViewModel()
    {
        SelectedRanges = new ObservableCollection<SelectionRange>();
        SelectedRanges.Add(new SelectionRange()
        {
            StartDate = new DateTime(2019, 02, 10),
            EndDate = new DateTime(2019, 02, 20)
        });

        SelectedRanges.Add(new SelectionRange()
        {
            StartDate = new DateTime(2019, 01, 31),
            EndDate = new DateTime(2019, 02, 05)
        });
    }
}
{% endhighlight %}
{% endtabs %}

>**NOTE**
* You can bind the `SelectedRange` property only when `SelectionBinding` is set to `RangeSelection` and `MultiRangeSelection` in calendar.



## Commands
 
### Tap command
 
The [TapCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_TapCommand) will be triggered whenever tapping the calendar cell and passing the [CalendarTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.CalendarTappedEventArgs.html) as parameter.

{% tabs %}
{% highlight xaml %} 
    <calendar:SfCalendar x:Name="calendar"  TapCommand="{Binding CalendarCellTapped}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
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

### Hold command

The [HoldCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_HoldCommand) will be triggered whenever the calendar cell is long pressed and passing the [DayCellHoldingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.DayCellHoldingEventArgs.html) as parameter.

{% tabs %}
{% highlight xaml %} 
    <calendar:SfCalendar x:Name="calendar"  HoldCommand="{Binding OnDateCellHolding}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
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
	CommandText = obj.ToString("dd/MM/yyyy") ;
  }
 
}
{% endhighlight %}
{% endtabs %} 

### Month changed command

The [MonthChangedCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_MonthChangedCommand) will be triggered whenever the navigating between month and Forward()/backward() is called in calendar and passing the [MonthChangedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.MonthChangedEventArgs.html) as parameter.

{% tabs %}
{% highlight xaml %} 
    <calendar:SfCalendar x:Name="calendar"  MonthChangedCommand="{Binding OnMonthChanged}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
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

### Selection changed command

The [SelectionChangedCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_SelectionChangedCommand) will be triggered whenever the selection is changed in calendar for the following selections and passing the [SelectionChangedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SelectionChangedEventArgs.html) as parameter.

* SingleSelection - A single date can be selected in a month view which can be equipped when user needs to select one date at a time.
* MultiSelection - More than one date can be selected.
* RangeSelection - It allows us to select a single date range in calendar month view.
* MultiRangeSelection - More than one date range can be selected in a month view.

{% tabs %}
{% highlight xaml %} 
    <calendar:SfCalendar x:Name="calendar" SelectionChangedCommand="{Binding OnSelectionChanged}">
              <calendar:SfCalendar.BindingContext>
              <local:CalendarViewModel/>
              </calendar:SfCalendar.BindingContext>
    </calendar:SfCalendar>
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
	SelectionChangedCommandText = " DateAdded- " +obj.DateAdded?.Count.ToString() +"  "+ " DateRemoved- " + obj.DateRemoved?.Count.ToString() + "  " + " NewRangeAdded -"
	  + obj.NewRangeAdded?.Count.ToString();
  }
}
    
{% endhighlight %}
{% endtabs %} 

## See also

[How to bind SelectedDates of Calendar in MVVM?](https://www.syncfusion.com/kb/10087/how-to-bind-selecteddates-of-calendar-in-mvvm)
