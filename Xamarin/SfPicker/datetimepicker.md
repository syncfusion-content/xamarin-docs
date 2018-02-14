---
layout: post
title: Demonstrate DateTimePicker using SfPicker of Syncfusion Picker control for Xamarin.Forms
description: Overview and key features of Picker control
platform: Xamarin
control: Picker
documentation: ug
---


# Date Time Picker

In our Xamarin.Forms, SfPicker control has multi column support. Using this we can populate day, month, year, hour and minute values of collection in SfPicker control. 

We have demonstrated how to create custom DateTimePicker using Picker control in the following steps.

**Step** **1** **:** We have created custom class named as “DateTimePicker”. This class should inherit from SfPicker control.
{% highlight c# %}
public class DateTimePicker : SfPicker

{

}

{% endhighlight %}

**Step** **2** **:** After that create six ObservableCollection with object type in DateTimePicker class. 

**Collection** **details** **:** 

Day Collection, Month Collection, Year Collection, Hour Collection and Minute Collection.

Day Collection -> We have added current month days using DateTime.DaysInMonth.

Month Collection -> We have added Jan to Dec months

Year Collection -> We have added 1990 to 2050 years.

Hour Collection -> We have added 0 to 24 hours.

Minute Collection -> We have added 00 to 59 minutes.

Date Collection -> We have added all the five collections.

Date Collection is main collection we have assigned this collection to ItemsSource of Picker Control.

The below code demonstrates Date collection creation.

{% highlight c# %}

public class DateTimePicker : SfPicker

{

#region Public Properties

// Months API is used to modify the Day collection as per change in Month

internal Dictionary<string, string> Months { get; set; }

/// <summary>

/// Date is the actual DataSource for SfPicker control which will holds the collection of Day ,Month and Year

/// </summary>

/// <value>The date.</value>

public ObservableCollection<object> Date { get; set; }

//Day is the collection of day numbers

internal ObservableCollection<object> Day { get; set; }

//Month is the collection of Month Names

internal ObservableCollection<object> Month{ get; set; }

//Year is the collection of Years from 1990 to 2042

internal ObservableCollection<object> Year{ get; set; }



//Hour is the collection of Hours in Railway time format

internal ObservableCollection<object> Hour{ get; set; }

//Minute is the collection of Minutes from 00 to 59

internal ObservableCollection<object> Minute{ get; set; }

#endregion

public DateTimePicker()

{

Months = new Dictionary<string, string>();

Date = new ObservableCollection<object>();

Day = new ObservableCollection<object>();

Month = new ObservableCollection<object>();

Year = new ObservableCollection<object>();

Hour = new ObservableCollection<object>();

Minute = new ObservableCollection<object>();   

PopulateDateCollection();

this.ItemsSource = Date;

}

private void PopulateDateCollection()

{

//populate months

for (int i = 1; i < 13; i++)

{

if (!Months.ContainsKey(CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i).Substring(0, 3)))

Months.Add(CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i).Substring(0, 3), CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i));

Month.Add(CultureInfo.CurrentCulture.DateTimeFormat.GetMonthName(i).Substring(0, 3));

}

//populate year

for (int i = 1990; i < 2050; i++)

{

Year.Add(i.ToString());

}

//populate Days

for (int i = 1; i <= DateTime.DaysInMonth(DateTime.Now.Year, DateTime.Now.Month); i++)

{

if (i < 10)

{

Day.Add("0" + i);

}

else

Day.Add(i.ToString());

}

//populate Hours

for (int i = 1; i <= 24; i++)

{

if (i < 10)

{

Hour.Add("0" + i.ToString());

}

else

Hour.Add(i.ToString());

}

//populate Minutes

for (int j = 0; j < 60; j++)

{

if (j < 10)

{

Minute.Add("0" + j);

}

else

Minute.Add(j.ToString());

}

Date.Add(Month);

Date.Add(Day);

Date.Add(Year);

Date.Add(Hour);

Date.Add(Minute);

}

}



{% endhighlight %}

**Step** **3** **:** We have updated the day value based on month and year value using Selection changed event of SfPicker control. Since the days of each month differs we have to handle this collection.

{% highlight c# %}

public DateTimePicker()

{



//hook selection changed event

this.SelectionChanged += CustomDatePicker_SelectionChanged;

}

private void CustomDatePicker_SelectionChanged(object sender, SelectionChangedEventArgs e)

{

UpdateDays(Date, e);

}

//Update days method is used to alter the Date collection as per selection change in Month column(if Feb is Selected day collection has value from 1 to 28)

public void UpdateDays(ObservableCollection<object> Date, SelectionChangedEventArgs e)

{

Device.BeginInvokeOnMainThread(() =>

{

try

{

bool update = false;

if (e.OldValue != null && e.NewValue != null && (e.OldValue as IList).Count>0 && (e.NewValue as IList).Count>0)

{

if ((e.OldValue as IList)[0] != (e.NewValue as IList)[0])

{

update = true;

}

if ((e.OldValue as IList)[2] != (e.NewValue as IList)[2])

{

update = true;

}

}

if (update)

{

ObservableCollection<object> days = new ObservableCollection<object>();

int month = DateTime.ParseExact(Months[(e.NewValue as IList)[0].ToString()], "MMMM", CultureInfo.InvariantCulture).Month;

int year = int.Parse((e.NewValue as IList)[2].ToString());

for (int j = 1; j <= DateTime.DaysInMonth(year, month); j++)

{

if (j < 10)

{

days.Add("0" + j);

}

else

days.Add(j.ToString());

}

if (days.Count > 0)

{

Date.RemoveAt(1);

Date.Insert(1, days);

}

}

}

catch

{

}

});

}

{% endhighlight %}

**Step** **4** **:** We have defined each column headers “Day”, “Month” , “Year” , “Hour” , “Minute”  using ColumnHeaderText property of SfPicker control. The below code demonstrates how to define header for each column of SfPicker control.

{% highlight c# %}
public class DateTimePicker : SfPicker

{

/// <summary>

/// Headers API is holds the column name for every column in date picker

/// </summary>

/// <value>The Headers.</value>

public ObservableCollection<string> Headers { get; set; }

public DateTimePicker()

{

Headers = new ObservableCollection<string>();

Headers.Add("Month");

Headers.Add("Day");

Headers.Add("Year");

Headers.Add("Hour");

Headers.Add("Minute");

//SfPicker header text

HeaderText = "Date Picker";



// Column header text collection

this.ColumnHeaderText = Headers;

}

}

{% endhighlight %}

**Step** **5** **:** Finally we have enabled SfPicker header, Column header and footer using ShowHeader,ShowFooter and ShowColumnHeader properties.

{% highlight c# %}
public DateTimePicker()

{



//Enable Footer

ShowFooter = true;

//Enable SfPicker Header

ShowHeader = true;

//Enable Column Header of SfPicker

ShowColumnHeader = true;

}

{% endhighlight %}

**Step** **6** **:** We have added the DateTimePicker control in main XAML page. Please refer the below code snippets.

{% tabs %}
{% highlight xaml %}
<ContentPage

x:Class="SfPDatetimeSample.MainPage"

xmlns="http://xamarin.com/schemas/2014/forms"

xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

xmlns:local="clr-namespace:SfPDatetimeSample"

xmlns:picker="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms">

<ContentPage.BindingContext>

<local:DateTimeViewModel />

</ContentPage.BindingContext>

<Grid>

<Button

Clicked="Button_Clicked"

HeightRequest="50"

HorizontalOptions="Center"

Text="Show Picker"

VerticalOptions="Center"

WidthRequest="200" />

<local:DateTimePicker

x:Name="date"

ColumnHeaderHeight="40"

HorizontalOptions="Start"

PickerHeight="400"

PickerMode="Dialog"

PickerWidth="300"

SelectedItem="{Binding StartDate}"

VerticalOptions="Center" />

</Grid>

</ContentPage> 

{% endhighlight %}

{% highlight c# %}
public partial class MainPage : ContentPage

{

public MainPage()

{

InitializeComponent();

}

private void Button_Clicked(object sender, EventArgs e)

{

date.IsOpen = !date.IsOpen;

}

}

{% endhighlight %}
{% endtabs %}

Screen shot for the above codes.

![](images/datetimepicker_img1.jpeg)


We have attached DateTimePicker sample for reference. Please download the sample from the following link.

Sample link: [DateTimePicker](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DateTimePicker-1772392178.zip)

