---
layout: post
title: Retrieving selected value in Syncfusion SfComboBox control for Xamarin.Forms
description: Learn how to retrieve selected value from SfComboBox control
platform: xamarin
control: SfComboBox
documentation: ug
---

# Retrieving Selected values

SfComboBox provides a way to get the selected values using SelectedValue and SelectedIndex properties.

## Retrieving the index of selected item

When an item is selected from suggestion list, its index can be retrieved using the [`SelectedIndex`] property. 
This property holds the index of selected item in suggestion list. 

The following code example shows the way to retrieve SelectedIndex and display it in an alert.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" SelectionChanged="Handle_SelectionChanged">
		<combobox:SfComboBox.DataSource>
			<ListCollection:List x:TypeArguments="x:String">
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> United Arab Emirates </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> United States </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.DataSource>
	 </combobox:SfComboBox>                                                 
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.SelectionChanged += (sender, e) =>
{
	DisplayAlert("Selection Changed", "Selected Index: " + comboBox.SelectedIndex, "OK"); 
};

layout.Children.Add(comboBox); 
Content = layout; 

{% endhighlight %}

{% endtabs %}

## Retrieving the value of selected item

When an item is selected from suggestion list, selected value can be retrieved using the [`SelectedValue`] property. If the DataSource is bound to string data, then selected string is set to the SelectedValue property.  

The following code example shows the way to retrieve SelectedValue and display it in an alert.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" SelectionChanged="Handle_SelectionChanged">
		<combobox:SfComboBox.DataSource>
			<ListCollection:List x:TypeArguments="x:String">
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> United Arab Emirates </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> United States </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.DataSource>
	 </combobox:SfComboBox>                                             
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.SelectionChanged += (sender, e) => 
{
	DisplayAlert("Selection Changed", "Selected Value: " + comboBox.SelectedValue.ToString(), "OK"); 
};

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

### Retrieving a member of model object

If the DataSource is bound to business object data, there is an additional step to get the SelectedValue. The model class may have one or more properties. So, it is necessary to intimate the combo box control that which property of model class should be stored in the SelectedValue property. This can be accomplished using the [`SelectedValuePath`] property.

Define a simple model class Employee with fields ID, Name and populate employee data in ViewModel.

{% tabs %}

{% highlight xaml %}

// Create a Employee Class which holds the Name and id.
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

// Create EmployeeViewModel class holds the collection of employee data. 
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

{% highlight c# %}

Now populate this EmployeeViewModel data in SfComboBox control by binding with [`DataSource`] property. 

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             xmlns:local="clr-namespace:NamespaceName"            
             x:Class="NamespaceName.ClassName">
	<ContentPage.BindingContext>
    	<local:EmployeeViewModel/>
 	</ContentPage.BindingContext>
	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" SelectionChanged="Handle_SelectionChanged" DataSource="{Binding EmployeeCollection}"/>
	</StackLayout> 
</ContentPage>

{% endhighlight %}

{% highlight c# %}

	StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    SfComboBox comboBox = new SfComboBox();
    comboBox.BindingContext = new EmployeeViewModel();
	comboBox.DisplayMemberPath = "Name";
	comboBox.SelectedValuePath = "ID";
	comboBox.SelectionChanged += (sender, e) => 
	{
		DisplayAlert("Selection Changed", "Selected Value: " +    comboBox.SelectedValue.ToString(), "OK"); 
	}; 

    Binding binding = new Binding("EmployeeCollection");
    binding.Source = this;
    binding.Mode = BindingMode.TwoWay;
    comboBox.SetBinding(Label.DataSourceProperty,binding);

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}
