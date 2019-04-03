---
layout : post
title : Data Binding  in Syncfusion AutoComplete control for Xamarin.Forms
description : This section decribes how to populate the strings or objects in the autocomplete for the filtering suggestion list. 
platform : xamarin
control : SfAutoComplete
documentation : ug
---

# Populating Data

SfAutoComplete control can be populated with a list of string or business objects, which assists the user while typing. Users can choose one item from the filtered suggestion list.

[`DataSource`] property is used to populate data in SfAutoComplete control. This section explains populating AutoComplete with list of string and list of Employee details separately.

## Populating String Data

Create an instance of string list and populate items as shown below: 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" />
</StackLayout>
	
{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Great Britain");
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("Canada");
countryNames.Add("United Arab Emirates");
countryNames.Add("France");
countryNames.Add("Italy");
countryNames.Add("United Kingdom");
countryNames.Add("China");
countryNames.Add("United States");
countryNames.Add("Japan");
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

![Populating data string](images/Populating-Data/populating-data-string.png)

## Populating Business Objects

Apart from string data, SfAutoComplete can deal with business object data also. Now let us create Model and ViewModel classes to populate AutoComplete with Employee details.

### Create and Initialize Business Models 

Define a simple model class Employee with fields ID, Name and populate employee data in ViewModel.

{% tabs %}

{% highlight C# %}

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
	employeeCollection.Add(new Employee() { ID = 6, Name = "Aldan" });
	employeeCollection.Add(new Employee() { ID = 7, Name = "Aldrin" });
	employeeCollection.Add(new Employee() { ID = 8, Name = "Alan" });
	employeeCollection.Add(new Employee() { ID = 9, Name = "Aaron" });
}
}

{% endhighlight %}

{% endtabs %}

### Populate data in AutoComplete

Now populate this EmployeeViewModel data in SfAutoComplete control by binding with [`DataSource`] property. 

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:AutoComplete"
			 xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             x:Class="AutoComplete.MainPage">
	<ContentPage.BindingContext>
		<local:EmployeeViewModel/>
	</ContentPage.BindingContext>
	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" DisplayMemberPath="Name" DataSource="{Binding EmployeeCollection}" />
	</StackLayout>
	
</ContentPage>

{% endhighlight %}

{% highlight C# %}

StackLayout layout = new StackLayout()
{
	VerticalOptions = LayoutOptions.Start,
	HorizontalOptions = LayoutOptions.Start,
    Padding = new Thickness(30)
};

EmployeeViewModel employee = new EmployeeViewModel();
SfAutoComplete autoComplete = new SfAutoComplete();
autoComplete.HeightRequest = 40;
autoComplete.BindingContext = employee;
autoComplete.DataSource = employee.EmployeeCollection;
autoComplete.DisplayMemberPath = "Name";

layout.Children.Add(autoComplete);
Content = layout;

{% endhighlight %}

{% endtabs %}

N> Set the EmployeeViewModel instance as the BindingContext of your control; this is done to bind properties of EmployeeViewModel to SfAutoComplete.

### Setting DisplayMemberPath

At this point, the control is populated with the list of employees. But the Employee model contains two properties ID and Name so it is necessary to intimate by which property it should filter suggestions. [`DisplayMemberPath`] property specifies the property path with which filtering is done on business objects.

{% highlight c# %}
	
autoComplete.DisplayMemberPath = "Name";
	
{% endhighlight %}

![Populating data business object](images/Populating-Data/populating-data-business-object.png)

### Setting ItemTemplate

[`ItemTemplate`] property helps to decorate suggestion items with custom templates. The following code explains the steps to add an image to the suggestion list item.

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" DisplayMemberPath="Name" DataSource="{Binding EmployeeCollection}">
	<autocomplete:SfAutoComplete.ItemTemplate>
		<DataTemplate>
			<StackLayout Orientation="Horizontal" Padding="2,0,0,0">
				<Image Source="User.png" WidthRequest="12"/>
				<Label Text="{Binding Name}" VerticalOptions="Center"/>
			</StackLayout>
		</DataTemplate>
	</autocomplete:SfAutoComplete.ItemTemplate>
	</autocomplete:SfAutoComplete>
</StackLayout>

{% endhighlight %}

The ItemTemplate in above XAML code is translated to C# and given below:

{% highlight c# %}

DataTemplate itemTemplate = new DataTemplate(() =>
{
StackLayout stack;
Image image;
Label label;
stack = new StackLayout();
stack.Orientation = StackOrientation.Horizontal;
image = new Image();
image.Source = (FileImageSource)ImageSource.FromFile("User.png");
label = new Label();
label.SetBinding(Label.TextProperty, "Name");
stack.Children.Add(image);
stack.Children.Add(label);
return new ViewCell { View = stack };
});
autoComplete.ItemTemplate = itemTemplate;

{% endhighlight %}

Refer [this](https://help.syncfusion.com/xamarin/sfautocomplete/customizing-autocomplete) link to learn more about the customizing options available in SfAutoComplete control.

N> Add the required image in drawable folder(Android), Resources folder(iOS) and at project location for UWP.

![Item template](images/Populating-Data/item-template.png)