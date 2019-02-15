---
layout: post
title: Retrieving selected value in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to retrieve selected value from SfAutoComplete control
platform: xamarin
control: SfAutoComplete
documentation: ug
---

# Retrieving Selected values

SfAutoComplete provides a way to get the selected values using SelectedValue and SelectedIndex properties.

## Retrieving the Index of Selected Item

When an item is selected from suggestion list, its index can be retrieved using [`SelectedIndex`] property. 
SelectedIndex property holds the index of selected item in suggestion list. 

The following code example demonstrates the way to retrieve SelectedIndex and display it in an alert.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" />                            
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SelectionChanged += (sender, e) =>
{
DisplayAlert("Selection Changed", "Selected Index: " + autoComplete.SelectedIndex, "OK"); 
};

{% endhighlight %}

{% endtabs %}

## Retrieving the Value of Selected Item

When an item is selected from suggestion list, selected value can be retrieved using [`SelectedValue`] property. If the DataSource is bound to string data, then selected string is set to the SelectedValue property.  

The following code example demonstrates the way to retrieve SelectedValue and display it in an alert.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" />                            
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SelectionChanged += (sender, e) => 
{
DisplayAlert("Selection Changed", "Selected Value: " + autoComplete.SelectedValue.ToString(), "OK"); 
};

{% endhighlight %}

{% endtabs %}

### Retrieving a Member of Model Object

If the DataSource is bound to business object data, there is an additional step to get the SelectedValue. The model class may have one or more properties. So, it is necessary to intimate AutoComplete that which property of model class should be stored in SelectedValue property. This can be accomplished by [`SelectedValuePath`] property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" DataSource="{Binding EmployeeCollection}"/>                            
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

public partial class SamplePage : ContentPage
{
public SamplePage()
{
	InitializeComponent();       
	autoComplete.BindingContext = new EmployeeViewModel();
	autoComplete.DisplayMemberPath = "Name";
	autoComplete.SelectedValuePath = "ID";
	autoComplete.SelectionChanged += (sender, e) => {
	DisplayAlert("Selection Changed", "Selected Value: " +    autoComplete.SelectedValue.ToString(), "OK"); };
}
}
public class Employee
{
private int id;
public int ID
{
	get { return id; }
	set { id = value; }
}
private string name;
public string Name
{
	get { return name; }
	set { name = value; }
}
}
public class EmployeeViewModel
{
private ObservableCollection<Employee> employeeCollection;
public ObservableCollection<Employee> EmployeeCollection
{
	get { return employeeCollection; }
	set { employeeCollection = value; }
}
public EmployeeViewModel()
{
	employeeCollection = new ObservableCollection<Employee>();
	employeeCollection.Add(new Employee() { ID = 1, Name = "Eric" });
	employeeCollection.Add(new Employee() { ID = 2, Name = "James" });
	employeeCollection.Add(new Employee() { ID = 3, Name = "Jacob" });
	employeeCollection.Add(new Employee() { ID = 4, Name = "Lucas" });
	employeeCollection.Add(new Employee() { ID = 5, Name = "Mark" });
}
}

{% endhighlight %}

{% endtabs %}

If the DataSource is bound to business object data, Selected item can be set initially by specifing the index of the datasource item. The property which is specfied in the `SelectedValuePath` will be displayed with respective to the index of the selected item.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" DisplayMemberPath="Name" SelectedValuePath="ID" x:Name="autoComplete" />                            
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

public partial class SamplePage : ContentPage
{
public SamplePage()
{
	InitializeComponent();       
	 var items = new ObservableCollection<Employee>
            {
                new Employee{ ID = 1, Name = "Eric" },
                new Employee{ ID = 2, Name = "James" },
                new Employee{ ID = 3, Name = "Jacob" },
                new Employee{ ID = 4, Name = "Lucas" },
                new Employee{ ID = 5, Name = "Mark" }
            };
            autoComplete.DataSource = items;
            autoComplete.SelectedItem = items[4];
}
public class Employee
{
private int id;
public int ID
{
	get { return id; }
	set { id = value; }
}
private string name;
public string Name
{
	get { return name; }
	set { name = value; }
}
}
public class EmployeeViewModel
{
private ObservableCollection<Employee> employeeCollection;
public ObservableCollection<Employee> EmployeeCollection
{
	get { return employeeCollection; }
	set { employeeCollection = value; }
}
public EmployeeViewModel()
{
	employeeCollection = new ObservableCollection<Employee>();
	employeeCollection.Add(new Employee() { ID = 1, Name = "Eric" });
	employeeCollection.Add(new Employee() { ID = 2, Name = "James" });
	employeeCollection.Add(new Employee() { ID = 3, Name = "Jacob" });
	employeeCollection.Add(new Employee() { ID = 4, Name = "Lucas" });
	employeeCollection.Add(new Employee() { ID = 5, Name = "Mark" });
}
}

{% endhighlight %}

{% endtabs %}
