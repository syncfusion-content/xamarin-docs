---
layout : post
title : Data Binding  in Syncfusion AutoComplete control for Xamarin.Forms
description : This section decribes how to populate the strings or objects in the autocomplete for the filtering suggestion list. 
platform : xamarin
control : SfAutoComplete
documentation : ug
---

# Populating Data

## Populating Data in Xamarin AutoComplete

SfAutoComplete control can be populated with a list of string or business objects, which assists the user while typing. Users can choose one item from the filtered suggestion list.

[`DataSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_DataSource) property is used to populate data in SfAutoComplete control. This section explains populating AutoComplete with list of string and list of Employee details separately.

## Populating String Data

Create an instance of string list and populate items as shown below: 

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start"
                 Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>France</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>China</x:String>
                    <x:String>United States</x:String>
                    <x:String>Japan</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                DataSource = new List<string>()
                {
                   "India",
                    "Uganda",
                    "Ukraine", 
                    "Canada",
                    "United Arab Emirates",
                    "France", 
                    "United Kingdom",
                    "China", 
                    "United States",
                    "Japan",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Populating data string](images/Populating-Data/populating-data-string.png)

## Populating Business Objects

Apart from string data, SfAutoComplete can deal with business object data also. Now let us create Model and ViewModel classes to populate AutoComplete with Employee details.

### Create and Initialize Business Models 

Define a simple model class Employee with fields ID, Name and populate employee data in ViewModel.

{% tabs %}

{% highlight C# %}

namespace AutocompleteSample
{
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
}

{% endhighlight %}

{% endtabs %}

### Populate data in AutoComplete and Setting DisplayMemberPath

Now populate this EmployeeViewModel data in SfAutoComplete control by binding with [`DataSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_DataSource) property. At this point, the control is populated with the list of employees. But the Employee model contains two properties ID and Name so it is necessary to intimate by which property it should filter suggestions. [`DisplayMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_DisplayMemberPath) property specifies the property path with which filtering is done on business objects.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <ContentPage.BindingContext>
        <local:EmployeeViewModel/>
    </ContentPage.BindingContext>
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40"
                                     DisplayMemberPath="Name" 
                                     DataSource="{Binding EmployeeCollection}" />
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            EmployeeViewModel employee = new EmployeeViewModel();
            StackLayout layout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                BindingContext = employee,
                DataSource = employee.EmployeeCollection,
                DisplayMemberPath = "Name"
            };

            layout.Children.Add(autoComplete);
            this.Content = layout;
        }
    }
}


{% endhighlight %}

{% endtabs %}

N> Set the EmployeeViewModel instance as the BindingContext of your control; this is done to bind properties of EmployeeViewModel to SfAutoComplete.

![Populating data business object](images/Populating-Data/populating-data-business-object.png)

### Setting ItemTemplate

[`ItemTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_ItemTemplate) property helps to decorate suggestion items with custom templates. The following code explains the steps to add an image to the suggestion list item.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <ContentPage.BindingContext>
        <local:EmployeeViewModel/>
    </ContentPage.BindingContext>
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete" 
                                     HeightRequest="40"
                                     DisplayMemberPath="Name" 
                                     DataSource="{Binding EmployeeCollection}">
            <autocomplete:SfAutoComplete.ItemTemplate>
                <DataTemplate>
                    <StackLayout Orientation="Horizontal" 
                                 Padding="2,0,0,0">
                        <Image Source="User.png" 
                               WidthRequest="12"/>
                        <Label Text="{Binding Name}" 
                               VerticalOptions="Center" 
                               WidthRequest="500"/>
                    </StackLayout>
                </DataTemplate>
            </autocomplete:SfAutoComplete.ItemTemplate>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% endtabs %}

The ItemTemplate in above XAML code is translated to C# and given below:

{% tabs %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            EmployeeViewModel employee = new EmployeeViewModel();
            StackLayout layout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                BindingContext = employee,
                DataSource = employee.EmployeeCollection,
                DisplayMemberPath = "Name"
            };

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
                label.WidthRequest = 500;
                stack.Children.Add(image);
                stack.Children.Add(label);
                return new ViewCell { View = stack };
            });
            autoComplete.ItemTemplate = itemTemplate;

            layout.Children.Add(autoComplete);
            this.Content = layout;
        }

    }
}

{% endhighlight %}

{% endtabs %}

Refer [this](https://help.syncfusion.com/xamarin/sfautocomplete/customizing-autocomplete) link to learn more about the customizing options available in SfAutoComplete control.

N> Add the required image in drawable folder(Android), Resources folder(iOS) and at project location for UWP.

![Item template](images/Populating-Data/item-template.png)