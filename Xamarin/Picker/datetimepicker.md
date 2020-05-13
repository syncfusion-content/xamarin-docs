---
layout: post
title: Demonstrate DateTimePicker using Syncfusion Picker for Xamarin.Forms
description: Overview and key features of Date Time Picker and how to get started with the SfPicker Control in Xamarin.Forms
platform: Xamarin
control: Picker
documentation: ug
---


# Date Time Picker of Picker Control

In our Xamarin.Forms, picker control has multi column support. By using this, you we can populate day, month, year, hour, and minute values of collection in picker control. 

This section explains create custom DateTimePicker by using picker control.

**Step** **1** **:** Create a custom class, and name it as “DateTimePicker”. This class should be inherited from picker control.
{% highlight c# %}
public class DateTimePicker : SfPicker

{

}

{% endhighlight %}

**Step** **2** **:** Create six ObservableCollection with object type in DateTimePicker class. 

**Collection** **details** **:** 

Day collection, Month collection, Year collection, Hour collection, and Minute collection.

Day collection Add current month's days by using DateTime.DaysInMonth.

Month collection -Add months from January to December.

Year collection -Add years from 1990 to 2050.

Hour collection -Add hours from 0 to 24.

Minute collection -Add minutes from  00 to 59.

Date collection -Add all the five collections.

Date collection is the main collection, and this collection has been assigned to ItemsSource of picker control.

The following code demonstrates date collection creation.

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

Date.Add(Year);

Date.Add(Month);

Date.Add(Day);

Date.Add(Hour);

Date.Add(Minute);

}

}



{% endhighlight %}

**Step** **3** **:** Update the day value based on month and year values by using Selection changed event of picker control. Since the days of each month differs, you should handle this collection.

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
                if (Date.Count == 5)
                {
                    bool flag = false;
                    if (e.OldValue != null && e.NewValue != null && (e.OldValue is ObservableCollection<object>) && (e.OldValue as ObservableCollection<object>).Count >0)
                    {
                        if (!object.Equals((e.OldValue as IList)[1], (e.NewValue as IList)[1]))
                        {
                            flag = true;
                        }

                        if (!object.Equals((e.OldValue as IList)[0], (e.NewValue as IList)[0]))
                        {
                            flag = true;
                        }
                    }

                    if (flag)
                    {
                        ObservableCollection<object> days = new ObservableCollection<object>();
                        int month = DateTime.ParseExact(Months[(e.NewValue as IList)[1].ToString()], "MMMM", CultureInfo.InvariantCulture).Month;
                        int year = int.Parse((e.NewValue as IList)[0].ToString());
                        for (int j = 1; j <= DateTime.DaysInMonth(year, month); j++)
                        {
                            if (j < 10)
                            {
                                days.Add("0" + j);
                            }
                            else
                                days.Add(j.ToString());
                        }

                        ObservableCollection<object> PreviousValue = new ObservableCollection<object>();

                        foreach (var item in e.NewValue as IList)
                        {
                            PreviousValue.Add(item);
                        }

                        if (days.Count > 0)
                        {
                            Date.RemoveAt(2);
                            Date.Insert(2, days);
                        }

                        if ((Date[2] as IList).Contains(PreviousValue[2]))
                        {
                            this.SelectedItem = PreviousValue;
                        }
                        else
                        {
                            PreviousValue[2] = (Date[2] as IList)[(Date[2] as IList).Count - 1];
                            this.SelectedItem = PreviousValue;
                        }
                    }
                }
        });
    }

{% endhighlight %}

**Step** **4** **:** Define each column headers “Day”, “Month” , “Year” , “Hour” , and “Minute”  by using the ColumnHeaderText property. The following code demonstrates how to define header for each column of picker control.

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

Headers.Add("Year");

Headers.Add("Month");

Headers.Add("Day");

Headers.Add("Hour");

Headers.Add("Minute");

//SfPicker header text

HeaderText = "Date Picker";



// Column header text collection

this.ColumnHeaderText = Headers;

}

}

{% endhighlight %}

**Step** **5** **:** Finally enable the picker header, Column header and footer by using the ShowHeader,ShowFooter and ShowColumnHeader properties.

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

**Step** **6** **:** Add the DateTimePicker control in main XAML page. Please refer the following code snippets.

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

N> The default value is the initial value of the ItemsSource collection. The default minimum year is 1990 and the maximum year is 2050 provided in the collection.

The following screenshot illustrates the output of the above codes.

![DateTimePicker image](images/datetimepicker_img1.jpeg)

You can download the DateTimePicker sample for reference from the following link.

Sample link: [DateTimePicker](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedPicker1526116181)