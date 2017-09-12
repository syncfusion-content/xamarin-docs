---
layout: post
title: Demonstrate Date Picker using SfPicker of Syncfusion Picker control for Xamarin.Forms
description: Overview and key features of Picker control
platform: Xamarin
control: Picker
documentation: ug
---


# Date Picker

We have demonstrated in the following steps to create custom Date Picker using Picker control.

**Step** **1** **:** We have created custom class named as “CustomDatePicker”. This class should inherit from SfPicker control.

{% highlight c# %}

public class CustomDatePicker : SfPicker

{

}

{% endhighlight %}

**Step** **2** **:** After that create four ObservableCollection with object type in CustomDatePicker class. 

**Collection** **details** **:** 

Date Collection, Day Collection, Month Collection and Year Collection.

Day Collection -> We have added current month days using DateTime.DaysInMonth.

Month Collection -> We have added Jan to Dec months

Year Collection -> We have added 1990 to 2050 years.

Date Collection -> We have added all the three collections.

Date Collection is main collection we have assigned this collection to ItemsSource of Picker Control.

The below code demonstrates Date collection creation.

{% highlight c# %}
public class CustomDatePicker : SfPicker

{

#region Public Properties

// Months api is used to modify the Day collection as per change in Month

internal Dictionary<string, string> Months { get; set; }

/// <summary>

/// Date is the acutal DataSource for SfPicker control which will holds the collection of Day ,Month and Year

/// </summary>

/// <value>The date.</value>

public ObservableCollection<object> Date { get; set; }

//Day is the collection of day numbers

internal ObservableCollection<object> Day { get; set; }

//Month is the collection of Month Names

internal ObservableCollection<object> Month{ get; set; }

//Year is the collection of Years from 1990 to 2042

internal ObservableCollection<object> Year{ get; set; }

#endregion

public CustomDatePicker()

{

Months = new Dictionary<string, string>();

Date = new ObservableCollection<object>();

Day = new ObservableCollection<object>();

Month = new ObservableCollection<object>();

Year = new ObservableCollection<object>();

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

Date.Add(Month);

Date.Add(Day);

Date.Add(Year);

}

}

{% endhighlight %}

**Step** **3** **:** We have updated the day value based on month and year value using Selection changed event of SfPicker control. Since the days of each month differs we have to handle this collection.

{% highlight c# %}
public CustomDatePicker()

{



//hook selection changed event

this.SelectionChanged += CustomDatePicker_SelectionChanged;

}

private void CustomDatePicker_SelectionChanged(object sender, SelectionChangedEventArgs e)

{

UpdateDays(Date, e);

}

//Updatedays method is used to alter the Date collection as per selection change in Month column(if feb is Selected day collection has value from 1 to 28)

public void UpdateDays(ObservableCollection<object> Date, SelectionChangedEventArgs e)

{

Device.BeginInvokeOnMainThread(() =>

{

try

{

bool isupdate = false;

if (e.OldValue != null && e.NewValue != null && (e.OldValue as IList).Count>0 && (e.NewValue as IList).Count>0)

{

if ((e.OldValue as IList)[0] != (e.NewValue as IList)[0])

{

isupdate = true;

}

if ((e.OldValue as IList)[2] != (e.NewValue as IList)[2])

{

isupdate = true;

}

}

if (isupdate)

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

**Step** **4** **:** We have defined each column headers “Day”, “Month” and “Year” using ColumnHeaderText property of SfPicker control. The below code demonstrates how to define header for each column of SfPicker control.

{% highlight c# %}
public class CustomDatePicker : SfPicker

{

/// <summary>

/// Headers api is holds the column name for every column in date picker

/// </summary>

/// <value>The Headers.</value>

public ObservableCollection<string> Headers { get; set; }

public CustomDatePicker()

{

Headers = new ObservableCollection<string>();

Headers.Add("Month");

Headers.Add("Day");

Headers.Add("Year");

//SfPicker header text

HeaderText = "Date Picker";



// Column header text collection

this.ColumnHeaderText = Headers;

}

}

{% endhighlight %}

**Step** **5** **:** Finally we have enabled SfPicker header, Column header and footer using ShowHeader,ShowFooter and ShowColumnHeader properties.

{% highlight c# %}
public CustomDatePicker()

{



//Enable Footer

ShowFooter = true;

//Enable SfPicker Header

ShowHeader = true;

//Enable Column Header of SfPicker

ShowColumnHeader = true;

}

{% endhighlight %}

**Step** **6** **:** We have added the CustomDatePicker control in main XAML page. Please refer the below code snippets.

{% tabs %}
{% highlight xaml %}
<ContentPage

x:Class="DatePicker.DatePickerPage"

xmlns="http://xamarin.com/schemas/2014/forms"

xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

xmlns:local="clr-namespace:DatePicker"

xmlns:picker="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms">

<ContentPage.BindingContext>

<local:DatePickerViewModel />

</ContentPage.BindingContext>

<Grid>

<Button

Clicked="Button_Clicked"

HeightRequest="30"

HorizontalOptions="Center"

Text="Show Picker"

VerticalOptions="Center"

WidthRequest="200" />

<local:CustomDatePicker

x:Name="date"

ColumnHeaderHeight="40"

HorizontalOptions="Center"

PickerHeight="400"

PickerMode="Dialog"

PickerWidth="300"

SelectedItem="{Binding StartDate}"

VerticalOptions="Center" />

</Grid>

</ContentPage>

{% endhighlight %}


{% highlight c# %}
public partial class DatePickerPage : ContentPage

{

public DatePickerPage()

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

Please find the below screen shot using the above codes.

![](images/datepicker_img1.jpeg)


We have attached DatePicker sample for reference. Please download the sample from the following link.

Sample link: [DatePicker](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DatePicker1441640702# "")

