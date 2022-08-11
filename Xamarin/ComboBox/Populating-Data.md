---
layout: post
title: Populating Data  in Xamarin ComboBox control | Syncfusion
description: Learn here all about Populating Data  support in Syncfusion Xamarin ComboBox (SfComboBox) control and more.
platform: xamarin
control: SfComboBox
documentation: ug
---

# Populating Data  in Xamarin ComboBox (SfComboBox)

[`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) control can be populated with a list of string or business objects, which assists the users when typing. Users can choose one item from the filtered suggestion list.

The [`DataSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DataSource) property is used to populate data in the combo box control. This section explains how to populate the combo box control with list of string and list of employee details separately.

## Populating string data

Create an instance of string list and populate items as shown in the following codes. 

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             xmlns:local="clr-namespace:NamespaceName"     
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"       
             x:Class="NamespaceName.ClassName">
<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30"> 
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox"> 
        <combobox:SfComboBox.ComboBoxSource>
            <ListCollection:List x:TypeArguments="x:String">
                <x:String> Great Britain </x:String>
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> Canada </x:String>
                <x:String> France </x:String>
                <x:String> Italy </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> China </x:String>
                <x:String> Japan </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.ComboBoxSource>
    </combobox:SfComboBox>
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

List<String> countryNames = new List<String>(); 
countryNames.Add("Great Britain"); 
countryNames.Add("Uganda"); 
countryNames.Add("Ukraine"); 
countryNames.Add("Canada"); 
countryNames.Add("France"); 
countryNames.Add("Italy"); 
countryNames.Add("United Kingdom"); 
countryNames.Add("China"); 
countryNames.Add("Japan"); 

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.ComboBoxSource = countryNames;
layout.Children.Add(comboBox); 
Content = layout;


{% endhighlight %}

{% endtabs %}

![DataStringImage](images/Populating-Data/populating-data-string.png)

## Populating business objects

Apart from string data, [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html)can deal business object data also. Now create Model and ViewModel classes to populate the combo box control with employee details. 

### Create and Initialize business models 

Define a simple model class employee with fields ID and name, and then populate employee data in ViewModel. 

{% highlight c# %}

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
	employeeCollection.Add(new Employee() { ID = 1, Name = "Frank" }); 
	employeeCollection.Add(new Employee() { ID = 2, Name = "James" }); 
	employeeCollection.Add(new Employee() { ID = 3, Name = "Steve" }); 
	employeeCollection.Add(new Employee() { ID = 4, Name = "Lucas" }); 
	employeeCollection.Add(new Employee() { ID = 5, Name = "Mark" }); 
	employeeCollection.Add(new Employee() { ID = 6, Name = "Michael" }); 
	employeeCollection.Add(new Employee() { ID = 7, Name = "Aldrin" }); 
	employeeCollection.Add(new Employee() { ID = 8, Name = "Jack" }); 
	employeeCollection.Add(new Employee() { ID = 9, Name = "Howard" }); 
}
}

{% endhighlight %}

### Populate data in ComboBox

Now populate this EmployeeViewModel data in [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) control by binding with [`DataSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DataSource) property. 

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
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DataSource="{Binding EmployeeCollection}" DisplayMemberPath="Name" />
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

EmployeeViewModel employee = new EmployeeViewModel();
SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.BindingContext = employee;
comboBox.DataSource = employee.EmployeeCollection;
comboBox.DisplayMemberPath = "Name";
layout.Children.Add(comboBox);
Content = layout;

{% endhighlight %}

{% endtabs %}

N> Set the EmployeeViewModel instance as the BindingContext of your control; this is done to bind properties of EmployeeViewModel to SfComboBox.

### Setting DisplayMemberPath

The combo box control is populated with a list of employees. But the employee model contains two properties ID and Name, So it is necessary to intimate by which property it should filter suggestions. The [`DisplayMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DisplayMemberPath) property specifies the property path with type of filtering is done on business objects.

{% highlight c# %}
	
comboBox.DisplayMemberPath = "Name";
	
{% endhighlight %}

![BusinessObjectImage](images/Populating-Data/populating-data-business-object.png)

### Setting ItemTemplate

The [`ItemTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_ItemTemplate) property helps to decorate suggestion items with custom templates. The following code explains the steps to add an image to the suggestion list item.

{% tabs %}
{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DisplayMemberPath="Name" DataSource="{Binding EmployeeCollection}">
	<combobox:SfComboBox.ItemTemplate>
            <DataTemplate>
                <StackLayout Orientation="Horizontal">
                    <Image Source="User.png" WidthRequest="12"/>
                    <Label Text="{Binding Name}" />
                </StackLayout>
            </DataTemplate>
        </combobox:SfComboBox.ItemTemplate>
    </combobox:SfComboBox>
</StackLayout>

{% endhighlight %}

The ItemTemplate in the previous XAML code is translated to C# which is shown in the following code.

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

StackLayout layout = new StackLayout() 
{ 
    VerticalOptions = LayoutOptions.Start, 
    HorizontalOptions = LayoutOptions.Start, 
    Padding = new Thickness(30) 
}; 

EmployeeViewModel employee = new EmployeeViewModel();
SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.BindingContext = employee;
comboBox.DataSource = employee.EmployeeCollection;
comboBox.ItemTemplate = itemTemplate;

layout.Children.Add(comboBox);
Content = layout;

{% endhighlight %}
{% endtabs %}

Refer to [this](https://help.syncfusion.com/xamarin/sfcombobox/customizing-combobox) link to learn more about the customizing options available in the combo box control.

N> Add the required image in drawable folder(Android), Resources folder(iOS) and at project location for UWP.

![ItemTemplateImage](images/Populating-Data/item-template.png)

## Populate particular column of the items in DataTable through ItemsSource.

[`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_ItemsSource) property helps to populate the DataTable items by using the [`DisplayMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DisplayMemberPath) property. The following code explains the steps to add the data table items.


### Create , initialize and add items in DataTable 

Define a data table with Order details data in ViewModel.

{% tabs %}

{% highlight C# %}
public class ViewModel
{
    public ViewModel()
    {
        DataTableCollection = GetDataTable();
    }
    public DataTable DataTableCollection { get; set; }
 
    private DataTable GetDataTable()
    {
        DataTable dataTable = new DataTable();
        dataTable.Columns.Add("Order ID", typeof(double));
        dataTable.Columns.Add("Customer Name", typeof(string));
        dataTable.Columns.Add("Customer ID", typeof(string));
        dataTable.Columns.Add("Country", typeof(string));
        dataTable.Rows.Add(1001, "Maria Anders", "ALFKI", "Germany");
        dataTable.Rows.Add(1002, "Ana Trujilo", "ANATR", "Mexico");
        dataTable.Rows.Add(1003, "Antonio Moreno","ENDGY", "Mexico");
        dataTable.Rows.Add(1004, "Thomas Hardy", "ANTON", "UK");
        dataTable.Rows.Add(1005, "Christina Berglund", "BERGS", "Sweden");
        dataTable.Rows.Add(1006, "Hanna Moos", "BLAUS", "Germany");
        dataTable.Rows.Add(1007, "Frederique Citeaux", "BLONP", "France");
        dataTable.Rows.Add(1008, "Martin Sommer", "BOLID", "Spain");
        dataTable.Rows.Add(1009, "Laurence Lebihan", "BONAP", "France");
        dataTable.Rows.Add(1010, "Kathryn", "BOTTM", "Canada");
        dataTable.Rows.Add(1011, "Tamer", "XDKLF", "UK");
        dataTable.Rows.Add(1012, "Martin", "QEUDJ", "US");
        dataTable.Rows.Add(1013, "Nancy", "ALOPS", "France");
        dataTable.Rows.Add(1014, "Janet", "KSDIO", "Canada");
        dataTable.Rows.Add(1015, "Dodsworth", "AWSDE", "Canada");
        dataTable.Rows.Add(1016, "Buchanan", "CDFKL", "Germany");
        dataTable.Rows.Add(1017, "Therasa", "WSCJD", "Canada");
        dataTable.Rows.Add(1018, "Margaret", "PLSKD", "UK");
        dataTable.Rows.Add(1019, "Anto", "CCDSE", "Sweden");
        dataTable.Rows.Add(1020, "Edward", "EWUJG", "Germany");
        dataTable.Rows.Add(1021, "Anne", "AWSDK", "US");
        dataTable.Rows.Add(1022, "Callahan", "ODKLF", "UK");
        dataTable.Rows.Add(1023, "Vinet", "OEDKL", "France"); 
        return dataTable;
    }
}
{% endhighlight %}

{% endtabs %}

Add the column name in the [`DisplayMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DisplayMemberPath) property to display all the data's of the corresponding column which is given as following code.   

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:ComboBoxSample"
             x:Class="ComboBoxSample.MainPage">
    <ContentPage.BindingContext>
        <local:EmployeeViewModel/>
    </ContentPage.BindingContext>
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
        <combobox:SfComboBox x:Name="combobox"  
                             SelectedIndex="2" 
                             DisplayMemberPath="CustomerID" 
                             ItemsSource="{Binding DataTableCollection}">
            <combobox:SfComboBox.ItemTemplate>
                <DataTemplate>
                     <DataTemplate>
                        <Grid>
                            <StackLayout Orientation="Horizontal">
                                <Label Text="{Binding}" HeightRequest="200" WidthRequest="200"/>
                            </StackLayout>
                        </Grid>
                    </DataTemplate>
                </DataTemplate>
            </combobox:SfComboBox.ItemTemplate>
        </combobox:SfComboBox>
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace ComboBoxample
{
    public partial class MainPage : ContentPage
    {
        SfComboBox comboBox;
        public MainPage()
        {
            InitializeComponent();
            comboBox = new SfComboBox();
            comboBox.HeightRequest = 40;
            comboBox.SelectedIndex = 2;
            comboBox.DisplayMemberPath="CustomerID"; 
            ViewModel viewModel = new ViewModel();

            StackLayout layout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            DataTemplate itemTemplate = new DataTemplate(() =>
            {
                Grid grid;
                Label label;
                grid = new Grid();
                label = new Label();
                label.SetBinding(Label.TextProperty, ".");
                label.WidthRequest = 200;
                label.HeightRequest = 200;
                grid.Children.Add(label);
                return new ViewCell { View = grid };
            });

            comboBox.ItemTemplate = itemTemplate;
            comboBox.ItemsSource = viewModel.DataTableCollection;
            layout.Children.Add(comboBox);
            this.BindingContext = viewModel;
            this.Content = layout;
        }

    }
}

{% endhighlight %}

{% endtabs %}
