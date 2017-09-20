---
layout: post
title: Demonstrate CascadingPicker using SfPicker of Syncfusion Picker control for Xamarin.Forms
description: Overview and key features of Picker control
platform: Xamarin
control: Picker
documentation: ug
---


# Cascading

We have demonstrated how to create custom Cascading sample using Picker control in the following steps.

We have created the cascading sample for updating state collection based on selected item of SfPicker.

Please refer the below steps to create the cascading sample 

**Step** **1** **:** We have created three ObservableCollection with object type in PickerCascading class. 

**Collection** **details** **:** 

Area Collection, Country Collection and State Collection.

Country Collection -> We have added country names.

State Collection -> We have added state names.

Area Collection -> We have added above  2 collections.

Area Collection is main collection we have assigned this collection to ItemsSource of Picker Control.

The below code demonstrates Area collection creation.

{% highlight c# %}


public class PickerCascading:INotifyPropertyChanged

{

#region Public Properties

/// <summary>

/// Area is the actual DataSource for SfPicker control which will holds the collection of Country and State

/// </summary>

/// <value>The area.</value>

public ObservableCollection<object> Area { get; set; }

//Country is the collection of country names

private ObservableCollection<object> Country { get; set; }

//State is the collection of state names

private ObservableCollection<object> State { get; set; }

/// <summary>

/// Headers API is holds the column name for every column in cascading picker

/// </summary>

/// <value>The Headers.</value>

public ObservableCollection<string> Header { get; set; }

private object _selected;

public event PropertyChangedEventHandler PropertyChanged;

#endregion

//Identify the selected area using property changed method

public object Selected

{

get { return _selected; }

set { _selected = value; RaisePropertyChanged("Selected"); }

}

public PickerCascading()

{

Area = new ObservableCollection<object>();

Header = new ObservableCollection<string>();

Country = new ObservableCollection<object>();

State = new ObservableCollection<object>();

//populate Countries

Country.Add("UK");

Country.Add("USA");

Country.Add("India");

Country.Add("UAE");

Country.Add("Germany");

//populate states

State.Add("London");

State.Add("Manchester");

State.Add("Cambridge");

State.Add("Edinburgh");

State.Add("Glasgow");

State.Add("Birmingham");

Area.Add(Country);

Area.Add(State);

Selected = new ObservableCollection<object>() { "UK", "London" };

}

//Hooked when changes occurred 

public void RaisePropertyChanged(string name)

{

if (PropertyChanged != null)

PropertyChanged(this, new PropertyChangedEventArgs(name));

}

}

{% endhighlight %}

**Step** **2** **:** We have updated the state collection  based on selected item of country name using Selection changed event of SfPicker control.

{% highlight c# %}

private void picker_SelectionChanged(object sender, Syncfusion.SfPicker.XForms.SelectionChangedEventArgs e)

{

if(picker.ItemsSource!=null && CurrentItem != (e.NewValue as IList)[0].ToString())

{

//Updated the second column collection based on first column selected value.

(picker.ItemsSource as ObservableCollection<object>).RemoveAt(1);

(picker.ItemsSource as ObservableCollection<object>).Add(GetCountry((e.NewValue as IList)[0].ToString()));

}

}

{% endhighlight %}

**Step** **3** **:** We have defined column headers as  “Country” and  “State” using ColumnHeaderText property of SfPicker control. The below code demonstrates how to define header for each column of SfPicker control.

{% highlight c# %}

public class PickerCascading:INotifyPropertyChanged

{           

/// <summary>

/// Headers API is holds the column name for every column in cascading picker

/// </summary>

/// <value>The Headers.</value>

public ObservableCollection<string> Header { get; set; }

public PickerCascading()

{

Header = new ObservableCollection<string>();

Header.Add("Country");

Header.Add("State");

}

}

{% endhighlight %}

**Step** **4** **:** We have added the cascading picker control in main XAML page. Please refer the below code snippets.

{% tabs %}
{% highlight xaml %}
<ContentPage

x:Class="CascadingPicker.MainPage"

xmlns="http://xamarin.com/schemas/2014/forms"

xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

xmlns:local="clr-namespace:CascadingPicker"

xmlns:syncfusion="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms">

<ContentPage.BindingContext>

<local:PickerCascading />

</ContentPage.BindingContext>

<ContentPage.Content>

<Grid HorizontalOptions="Center" VerticalOptions="Center">

<StackLayout>

<Button

Clicked="Button_Clicked"

HeightRequest="40"

Text="Open Picker"

WidthRequest="200" />

</StackLayout>

<syncfusion:SfPicker

x:Name="picker"

ColumnHeaderText="{Binding Header}"

HeaderText="Select your Area"

HeightRequest="350"

ItemsSource="{Binding Area}"

PickerHeight="250"

PickerMode="Dialog"

PickerWidth="280"

SelectedItem="{Binding Selected}"

SelectionChanged="picker_SelectionChanged"

ShowColumnHeader="True"

WidthRequest="300" />

</Grid>

</ContentPage.Content>

</ContentPage>



{% endhighlight %}


{% highlight c# %}
public partial class MainPage : ContentPage

{

string CurrentItem;

public MainPage()

{

InitializeComponent();

}

private void Button_Clicked(object sender, EventArgs e)

{

picker.IsOpen = true;

}

}

{% endhighlight %}
{% endtabs %}

Screen shot for the above codes.

![](images/cascading_img1.jpeg)


We have attached Cascading sample for reference. Please download the sample from the following link.

Sample link: [CascadingSample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/CascadingPicker-212266727)

