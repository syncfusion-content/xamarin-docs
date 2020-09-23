---
layout: post
title: Getting started | SfDataGrid | Xamarin | Syncfusion
description: Getting started with Xamarin.Forms DataGrid and walk through to create a demo application from the scratch. 
platform: xamarin
control: SfDataGrid
documentation: ug
---

# Getting Started with Xamarin DataGrid (SfDataGrid)

This section provides a quick overview for working with the SfDataGrid for Xamarin.Forms. Walk through the entire process of creating a real world of this control.

To get start quickly with Xamarin.Forms DataGrid, you can check on this video:
<style>#XamarinDataGridVideoTutorial{width : 90% !important; height: 400px !important }</style>
<iframe id='XamarinDataGridVideoTutorial' src='https://www.youtube.com/embed/rdPStxCSy5w'></iframe>

## Assembly deployment

After installing Essential Studio for Xamarin, find all the required assemblies in the installation folders {Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib.

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib.

N> Assemblies can be found in an unzipped package location in Mac.

## NuGet configuration

To install the required NuGet for the SfDataGrid control in the application, configure the NuGet packages of the Syncfusion components.

Refer to the following KB to configure the NuGet packages of the Syncfusion components:

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

The following NuGet package should be installed to use the SfDataGrid control in the application.

<table>
<tr>
<th> Project </th>
<th> Required package </th>
</tr>
<tr>
<td> Xamarin.Forms </td>
<td> Syncfusion.Xamarin.SfDataGrid</td>
</tr>
</table>

## Adding SfDataGrid reference

You can add SfDataGrid reference using one of the following methods:

**Method 1: Adding SfDataGrid reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDataGrid to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfDataGrid](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDataGrid), and then install it.

![Adding SfDataGrid reference from NuGet](Getting-started_images/Adding SfDataGrid reference.png)

N> Install the same version of SfDataGrid NuGet in all the projects.

**Method 2: Adding SfDataGrid reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfDataGrid control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfDataGrid assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Data.Portable.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfDataGrid.XForms.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Licensing.dll<br/>Syncfusion.SfComboBox.XForms.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.Data.Portable.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfDataGrid.XForms.dll<br/>Syncfusion.SfDataGrid.XForms.Android.dll<br/>Syncfusion.SfNumericTextBox.Android.dll<br/>Syncfusion.SfNumericTextBox.XForms.Android.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/>Syncfusion.SfComboBox.XForms.dll<br/>Syncfusion.SfComboBox.XForms.Android.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.Data.Portable.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfDataGrid.XForms.dll<br/>Syncfusion.SfDataGrid.XForms.iOS.dll<br/>Syncfusion.SfNumericTextBox.iOS.dll<br/>Syncfusion.SfNumericTextBox.XForms.iOS.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/>Syncfusion.SfComboBox.XForms.dll<br/>Syncfusion.SfComboBox.XForms.iOS.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.Data.Portable.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfDataGrid.XForms.dll<br/>Syncfusion.SfDataGrid.XForms.UWP.dll<br/>Syncfusion.SfInput.UWP.dll<br/>Syncfusion.SfShared.UWP.dll<br/>Syncfusion.SfNumericTextBox.XForms.UWP.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/>Syncfusion.SfComboBox.XForms.dll<br/>Syncfusion.SfComboBox.XForms.UWP.dll<br/></td>
</tr>
<tr>
<td>WPF</td>
<td>Syncfusion.Data.Portable.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfDataGrid.XForms.dll<br/>Syncfusion.SfDataGrid.XForms.WPF.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.WPF.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>macOS</td>
<td>Syncfusion.Data.Portable.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfDataGrid.XForms.dll<br/>Syncfusion.SfDataGrid.XForms.macOS.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.macOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the SfDataGrid on each platform

To use the SfDataGrid inside an application, each platform application must initialize the SfDataGrid renderer. This initialization step varies from platform to platform and is discussed in the following sections:

### Android

The Android launches the SfDataGrid without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the SfDataGrid in iOS, call the `SfDataGridRenderer.Init()` in the `FinishedLaunching` override method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called as demonstrated in the following code example:

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    Syncfusion.SfDataGrid.XForms.iOS.SfDataGridRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 

### macOS

To launch the SfDataGrid in macOS, call the `SfDataGridRenderer.Init()` method in the `DidFinishLaunching` override method of the AppDelegate class after the Xamarin.Forms framework initialization and before the LoadApplication method is called as demonstrated in the following code sample:

{% highlight C# %} 

public override void DidFinishLaunching(NSNotification notification)
{ 
    … 
    Forms.Init();
    Syncfusion.SfDataGrid.XForms.MacOS.SfDataGridRenderer.Init();
    LoadApplication(new App());          
    …
}

{% endhighlight %}

### Universal Windows Platform (UWP)

To launch the SfDataGrid in UWP, call the `SfDataGridRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called as demonstrated in the following code example.

{% highlight c# %}
public MainPage()
{
    …
    Syncfusion.SfDataGrid.XForms.UWP.SfDataGridRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %}

### Windows Presentation Platform (WPF)

To launch the SfDataGrid in WPF, call the `SfDataGridRenderer.Init()` in the `MainWindow` constructor before the LoadApplication is called as demonstrated in the following code example.

{% highlight c# %}
public MainWindow()
{
    …
    Syncfusion.SfDataGrid.XForms.WPF.SfDataGridRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %}

### Release mode issue in UWP platform

The known Framework issue in UWP platform is the custom controls will not render when deployed the application in `Release Mode` or [.Net Native compilation](https://docs.microsoft.com/en-US/dotnet/framework/net-native/). It can be resolved by initializing the SfDataGrid assemblies in `App.xaml.cs` in UWP project as in the following code snippet.

{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    …

    rootFrame.NavigationFailed += OnNavigationFailed;
        
    // you should add `using System.Reflection;`
    List<Assembly> assembliesToInclude = new List<Assembly>();

    //Now, add all the assemblies your app uses
    assembliesToInclude.Add(typeof(Syncfusion.SfDataGrid.XForms.UWP.SfDataGridRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(Syncfusion.SfNumericTextBox.XForms.UWP.SfNumericTextBoxRenderer).GetTypeInfo().Assembly);
	assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.ComboBox.SfComboBoxRenderer).GetTypeInfo().Assembly);

    // replaces Xamarin.Forms.Forms.Init(e);        
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        
    …     
}
{% endhighlight %}

## Create a simple SfDataGrid 

This section explains how to create a SfDataGrid and configure it. The SfDataGrid control can be configured entirely in C# code or using XAML markup. This is how the final output will look like on iOS, Android, and Windows Phone devices.
 
![Xamarin DataGrid](SfDataGrid_images/SfDataGrid-Xamarin_img2.png)

N> You can download the complete project of this demo from [GitHub](https://github.com/SyncfusionExamples/DataGrid-GettingStarted-in-Xamarin-Forms).

In this walk through, a new application can be created that contains the SfDataGrid which includes the following topics:

 * [Creating the project](#creating-the-project) 
 * [Adding SfDataGrid in Xamarin.Forms](#adding-sfdatagrid-in-xamarinforms)     
 * [Create data model](#create-datamodel-for-the-sfdatagrid)  
 * [Binding data](#binding-data-to-sfdatagrid) 
 * [Defining columns](#defining-columns) 
 * [Sorting](#sorting) 
 * [Grouping](#grouping) 
 * [Selection](#selection)
 * [Editing](https://help.syncfusion.com/xamarin/datagrid/editing)

## Creating the project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for Xamarin.Forms.

## Adding SfDataGrid in Xamarin.Forms 

1. Add the required assembly references to the pcl and renderer projects as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import the SfDataGrid control namespace as `xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms` in XAML Page.

3. Set the SfDataGrid control as content to the ContentPage.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms" 
             x:Class="GettingStarted.Sample">

    <ContentPage.Content>
        <syncfusion:SfDataGrid x:Name="dataGrid" />
    </ContentPage.Content>
</ContentPage> 
{% endhighlight %}
{% highlight c# %}
using Syncfusion.SfDataGrid.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfDataGrid dataGrid;
        public App()
        {
            dataGrid = new SfDataGrid();
            MainPage = new ContentPage { Content = dataGrid };
        }
    }
} 
{% endhighlight %}
{% endtabs %}

## Create DataModel for the SfDataGrid

The SfDataGrid is a data-bound control. Hence, a data model should be created to bind it to the control. 

Create a simple data source as shown in the following code example in a new class file. Save it as OrderInfo.cs file:

{% highlight c# %}
public class OrderInfo
{
    private int orderID;
    private string customerID;
    private string customer;
    private string shipCity;
    private string shipCountry;

    public int OrderID {
        get { return orderID; }
        set { this.orderID = value; }
    }

    public string CustomerID {
        get { return customerID; }
        set { this.customerID = value; }
    }

    public string ShipCountry {
        get { return shipCountry; }
        set { this.shipCountry = value; }
    }

    public string Customer {
        get { return this.customer; }
        set { this.customer = value; }
    }

    public string ShipCity {
        get { return shipCity; }
        set { this.shipCity = value; }
    }

    public OrderInfo (int orderId, string customerId, string country, string customer, string shipCity)
    {
        this.OrderID = orderId;
        this.CustomerID = customerId;
        this.Customer = customer;
        this.ShipCountry = country;
        this.ShipCity = shipCity;
    }
} 
{% endhighlight %}

N> If you want your data model to respond to property changes, implement `INotifyPropertyChanged` interface in your model class.

Create a model repository class with OrderInfo collection property initialized with required number of data objects in a new class file as shown in the following code example and save it as OrderInfoRepository.cs file:

{% highlight c# %}
public class OrderInfoRepository
{
    private ObservableCollection<OrderInfo> orderInfo;
    public ObservableCollection<OrderInfo> OrderInfoCollection {
        get { return orderInfo; }
        set { this.orderInfo = value; }
    }

    public OrderInfoRepository ()
    {
        orderInfo = new ObservableCollection<OrderInfo> ();
        this.GenerateOrders ();
    }

    private void GenerateOrders ()
    {
        orderInfo.Add (new OrderInfo (1001, "Maria Anders", "Germany", "ALFKI", "Berlin"));
        orderInfo.Add (new OrderInfo (1002, "Ana Trujillo", "Mexico", "ANATR", "Mexico D.F."));
        orderInfo.Add (new OrderInfo (1003, "Ant Fuller", "Mexico", "ANTON", "Mexico D.F."));
        orderInfo.Add (new OrderInfo (1004, "Thomas Hardy", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1005, "Tim Adams", "Sweden", "BERGS", "London"));
        orderInfo.Add (new OrderInfo (1006, "Hanna Moos", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1007, "Andrew Fuller", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1008, "Martin King", "Spain", "BOLID", "Madrid"));
        orderInfo.Add (new OrderInfo (1009, "Lenny Lin", "France", "BONAP", "Marsiella"));
        orderInfo.Add (new OrderInfo (1010, "John Carter", "Canada", "BOTTM", "Lenny Lin"));
        orderInfo.Add (new OrderInfo (1011, "Laura King", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1012, "Anne Wilson", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1013, "Martin King", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1014, "Gina Irene", "UK", "AROUT", "London"));
    }
}
{% endhighlight %}

## Binding data to the SfDataGrid

To bind the data source to the SfDataGrid, set the [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ItemsSource) property as follows. You can bind the data source of the SfDataGrid either from XAML or in code. 

The following code example binds the collection created in previous step to `SfDataGrid.ItemsSource` property.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms" 
             x:Class="GettingStarted.Sample">

    <ContentPage.BindingContext>
        <local:OrderInfoRepository x:Name="viewModel" />
    </ContentPage.BindingContext>

    <ContentPage.Content>
        <syncfusion:SfDataGrid x:Name="dataGrid"
                               ItemsSource="{Binding OrderInfoCollection}">
        </syncfusion:SfDataGrid>
    </ContentPage.Content>
</ContentPage> 
{% endhighlight %}
{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
{% endhighlight %}
{% endtabs %}

Run the application to render the following output.

![DataGrid with default appearance](SfDataGrid_images/SfDataGrid-Xamarin_img3.png)

## Defining columns

By default, the SfDataGrid automatically creates columns for all the properties in the data source. The type of the column generated depends on the type of data in the column. When the columns are auto-generated, handle the [SfDataGrid.AutoGeneratingColumn](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) event to customize or cancel the columns before they are added to the columns collection in the SfDataGrid.
 
The columns can be manually defined by setting the [SfDataGrid.AutoGenerateColumns](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_AutoGenerateColumns) property to false and by adding the [GridColumn](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html) objects to the [SfDataGrid.Columns](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_Columns) collection. It can be done from both XAML and code. The following code example illustrates this:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
            ColumnSizer="Star"
            AutoGenerateColumns="False"
            ItemsSource="{Binding OrderInfoCollection}">

    <syncfusion:SfDataGrid.Columns x:TypeArguments="syncfusion:Columns">
        <syncfusion:GridTextColumn HeaderText="Order ID" 
                                   MappingName="OrderID" />
        <syncfusion:GridTextColumn HeaderText="Customer ID"
                                   MappingName="CustomerID" />
        <syncfusion:GridTextColumn MappingName="Customer" />
        <syncfusion:GridTextColumn HeaderText="Ship Country"
                                   MappingName="ShipCountry" />
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
dataGrid.AutoGenerateColumns = false;

GridTextColumn orderIdColumn = new GridTextColumn ();
orderIdColumn.MappingName = "OrderID";
orderIdColumn.HeaderText = "Order ID";

GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";

GridTextColumn customerColumn = new GridTextColumn ();
customerColumn.MappingName = "Customer";
customerColumn.HeaderText = "Customer";

GridTextColumn countryColumn = new GridTextColumn ();
countryColumn.MappingName = "ShipCountry";
countryColumn.HeaderText = "Ship Country";

dataGrid.Columns.Add (orderIdColumn);
dataGrid.Columns.Add (customerIdColumn);
dataGrid.Columns.Add (customerColumn);
dataGrid.Columns.Add (countryColumn); 
{% endhighlight %}
{% endtabs %}

## Sorting

The SfDataGrid allows sorting on its data by setting the [SfDataGrid.AllowSorting](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_AllowSorting) property to true.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid AllowSorting="True" />
{% endhighlight %}
{% highlight c# %}
dataGrid.AllowSorting = true; 
{% endhighlight %}
{% endtabs %}

Run the application and touch the header cell to sort the data and the following output will be displayed.
 
![DataGrid with sorting applied](SfDataGrid_images/SfDataGrid-Xamarin_img4.png)

Sorting can also be configured by adding the column to the [SfDataGrid.SortColumnDescriptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SortColumnDescriptions) collection as follows.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid.SortColumnDescriptions>
    <syncfusion:SortColumnDescription ColumnName="CustomerID" />
</syncfusion:SfDataGrid.SortColumnDescriptions> 
{% endhighlight %}
{% highlight c# %}
dataGrid.SortColumnDescriptions.Add (new SortColumnDescription () { ColumnName = "CustomerID" });
{% endhighlight %}
{% endtabs %}

## Grouping

The SfDataGrid allows grouping a column by adding the column to the [SfDataGrid.GroupColumnDescriptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GroupColumnDescriptions) collection as follows.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid.GroupColumnDescriptions>
    <syncfusion:GroupColumnDescription ColumnName="ShipCountry" />
</syncfusion:SfDataGrid.GroupColumnDescriptions> 
{% endhighlight %}
{% highlight c# %}
dataGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () { ColumnName = "ShipCountry" });
{% endhighlight %}
{% endtabs %}

Run the application to render the following output.

![DataGrid with grouping applied](SfDataGrid_images/SfDataGrid-Xamarin_img5.png)

## Selection

The SfDataGrid allows selecting the row or rows by setting the [SfDataGrid.SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectionMode) property. You can set the `SfDataGrid.SelectionMode` property to single, multiple, single deselect, or none. Information about the row or rows selected can be tracked using the [SfDataGrid.SelectedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedItem) and [SfDataGrid.SelectedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedItems) properties.

The selection operations can be handled with the help of the [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) and [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) events of the SfDataGrid.

## Launching the SfDataGrid inside a StackLayout

The StackLayout positions the child element one after the other. They are adding either horizontally or vertically. Space of the [StackLayout](https://docs.microsoft.com/en-us/dotnet/api/Xamarin.Forms.StackLayout?view=xamarin-forms) depends on the HorizontalOptions and VerticalOptions properties are set. But by default, the `StackLayout` will try to use the entire screen.

The SfDataGrid control can be loaded inside any layout such as [Grid](https://docs.microsoft.com/en-us/dotnet/api/Xamarin.Forms.Grid?view=xamarin-forms), `StackLayout`, etc., When loading SfDataGrid inside a `StackLayout`, set the Horizontal and/or VerticalOptions of the SfDataGrid and its parent to “LayoutOptions.FillAndExpand” based on the orientation of the container in which the SfDataGrid is loaded.

Refer to the following code example to load the SfDataGrid control inside a `StackLayout`. The VerticalOptions of the `StackLayout` and the SfDataGrid alone is set as “FillAndExpand” as the default orientation of the `StackLayout` is vertical.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GridInForms"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             x:Class="GridInForms.MainPage">
  <ContentPage.BindingContext>
    <local:ViewModel x:Name="viewModel"/>
  </ContentPage.BindingContext>
  <ContentPage.Content>
    <StackLayout VerticalOptions="FillAndExpand">
        <SearchBar Placeholder="UserName" TextChanged="searchBar_TextChanged" />
        <sfgrid:SfDataGrid x:Name="dataGrid"
                       ColumnSizer="Star"
                       ItemsSource="{Binding OrderInfoCollection}"
                       VerticalOptions="FillAndExpand" />
    </StackLayout>
  </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        private StackLayout stackLayout;
        private SfDataGrid dataGrid;
        private ViewModel viewModel;
        private SearchBar searchBar;
        public MainPage()
        {
            InitializeComponent();
            stackLayout = new StackLayout();
            dataGrid = new SfDataGrid();
            viewModel = new ViewModel();
            searchBar = new SearchBar();
            searchBar.Placeholder = "UserName";
            dataGrid.ItemsSource = viewModel.OrdersInfo;
            dataGrid.ColumnSizer = ColumnSizer.Star;
            stackLayout.VerticalOptions = LayoutOptions.FillAndExpand;
            stackLayout.HorizontalOptions = LayoutOptions.FillAndExpand;
            stackLayout.Children.Add(searchBar);
            stackLayout.Children.Add(dataGrid);
            this.Content = stackLayout;
        }
    }
}
{% endhighlight %}
{% endtabs %}

Refer to the following screenshot for the outcome.

![DataGrid inside a StackLayout](SfDataGrid_images/GridInStackLayout.png)

N> In case, if the orientation of the `StackLayout` is horizontal, set the HorizontalOptions instead. In some cases, set both the “VerticalOptions” and “HorizontalOptions” of the SfDataGrid based on its parent.

## Loading the SfDataGrid with customized height and width

The SfDataGrid can be load with specific height and width inside different layouts using the [SfDataGrid.HeightRequest](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) and [SfDataGrid.WidthRequest](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) properties. 

The following code example illustrates how this can be done.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GridInForms"
             x:Class="GridInForms.MainPage"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms" >

    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    
        <sfgrid:SfDataGrid x:Name="dataGrid"
                           ItemsSource="{Binding OrdersInfo}"
                           HeightRequest="290"
                           WidthRequest="200"
                           VerticalOptions="CenterAndExpand"
                           HorizontalOptions="Center"/>
    
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public MainPage()
{
    InitializeComponent();
    viewModel = new ViewModel();
    dataGrid = new SfDataGrid();
    dataGrid.ItemsSource = viewModel.OrdersInfo;
    dataGrid.HeightRequest = 290;
    dataGrid.WidthRequest = 200;
    dataGrid.VerticalOptions = LayoutOptions.CenterAndExpand;
    dataGrid.HorizontalOptions = LayoutOptions.Center;
    this.Content = dataGrid;
}
{% endhighlight %}
{% endtabs %}

The following screenshot shows how the SfDataGrid is loaded with specific height and width with VerticalOptions and HorizontalOptions.

![DataGrid with customized height and width](SfDataGrid_images/Loading_with specific_height_and_width.png)

N> Set [HorizontalOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) and [VerticalOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) to grid accordingly. When the `SfDataGrid` doesn't obtain finite size from its parent to layout in the View, the predefined `MinimumHeightRequest` and `MinimumWidthRequest`, which is 300, will be acquired.

## Linker issue in Xamarin.Forms.iOS

There are some known Framework issues in Xamarin.Forms.iOS platform.

When creating the SfDataGrid in `Xamarin.Forms` with `Linker behavior` in iOS renderer project as “Link Framework SDKs only”, sometimes `System.MethodMissingException` or `No method Count exists on type System.Linq.Queryable` exception will be thrown.

The above exceptions can be resolved by using the following workaround: 

**Workaround:**

The above exceptions can be resolved in two ways.
 
 1.	By setting LinkerBehavior as “Do not Link”.
 2.	By setting custom linker argument in iOS renderer project as in the following screenshot.


![DataGrid with linker settings](SfDataGrid_images/GettingStarted_img1.png)

## See also

[How to overcome the DisplayBinding converter is not firing problem when XamlCompilation attribute is set as XamlCompilationOptions.Compile](https://www.syncfusion.com/kb/7561)

[What will be the best practice way to update Xamarin controls in an existing project](https://www.syncfusion.com/kb/7519)

[How to solve the Android resources issue in Xamarin.Forms](https://www.syncfusion.com/kb/7481)

[How to convert Point to Index and Index to Point in SfDataGrid](https://www.syncfusion.com/kb/7456)

[How to load grid without borders](https://www.syncfusion.com/kb/7451)

[How to parse XML file and set as ItemsSource for SfDataGrid](https://www.syncfusion.com/kb/7439)

[How to configure package source and install Syncfusion NuGet packages in an existing project](https://www.syncfusion.com/kb/7441)

[How to render SfDataGrid for Xamarin.Forms.UWP in release mode](https://www.syncfusion.com/kb/7445)