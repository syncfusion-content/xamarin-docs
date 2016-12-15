---
layout: post
title: Getting started | SfDataGrid | Xamarin | Syncfusion
description: Getting started with SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: ug
---

# Getting Started

This section provides a quick overview for working with SfDataGrid for Xamarin.Forms. You will walk through the entire process of creating a real world SfDataGrid.


## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac

### SfDataGrid for Xamarin.Forms

The following list of assemblies need to be added as reference from the lib folder to use SfDataGrid in your application.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.Data.Portable.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfDataGrid.XForms.dll<br/></td>
</tr>
<tr>
<td>Android Renderer</td>
<td>pcl\Syncfusion.Data.Portable.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfDataGrid.XForms.dll<br/>android\Syncfusion.SfDataGrid.XForms.Android.dll<br/></td>
</tr>
<tr>
<td>iOS Renderer</td>
<td>pcl\Syncfusion.Data.Portable.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfDataGrid.XForms.dll<br/>ios-unified\Syncfusion.SfDataGrid.XForms.iOS.dll<br/></td>
</tr>
<tr>
<td>UWP Renderer</td>
<td>pcl\Syncfusion.Data.Portable.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfDataGrid.XForms.dll<br/>uwp\Syncfusion.SfDataGrid.XForms.UWP.dll<br/></td>
</tr>
</table>

In order to use export to excel and export to PDF functionalities of SfDataGrid, add the below assembly to your pcl project.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfGridConverter.XForms.dll<br/>pcl\Syncfusion.Compression.Portable.dll<br/>pcl\Syncfusion.Pdf.Portable.dll<br/>pcl\Syncfusion.XlsIO.Portable.dll<br/></td>
</tr>
</table>

## Launching the SfDataGrid on each platform

To use SfDataGrid inside an application, each platform application must initialize the SfDataGrid renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android

The Android launches the SfDataGrid without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the SfDataGrid in iOS, you need to call the `SfDataGridRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called, as demonstrated in the following code example:

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    SfDataGridRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 

### Universal Windows Platform (UWP)

To launch the SfDataGrid in UWP, you need to call the `SfDataGridRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called, as demonstrated in the following code example:

{% highlight c# %}
public MainPage()
{
    …
    SfDataGridRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %}

## Create a simple SfDataGrid 

This section explains how to create a SfDataGrid and configure it. The SfDataGrid control can be configured entirely in C# code or by using XAML markup. This is how the final output will look like on iOS, Android and Windows Phone devices.
 
![](SfDataGrid_images/SfDataGrid-Xamarin_img2.png)

You can download the entire source code of this demo for Xamarin.Forms from [here](http://files2.syncfusion.com/Xamarin.Forms/Samples/DataGrid_GettingStartedForms.zip).

In this walk through, you will create a new application that contains the SfDataGrid which includes the below topics.

* [Creating the project](#creating-the-project) 
* [Adding SfDataGrid in Xamarin.Forms](#adding-sfdatagrid-in-xamarinforms)     
* [Create data model](#create-datamodel-for-the-sfdatagrid)  
* [Binding data](#binding-data-to-sfdatagrid) 
* [Defining columns](#defining-columns) 
* [Sorting](#sorting) 
* [Grouping](#grouping) 
* [Selection](#selection)

## Creating the project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for Xamarin.Forms.

## Adding SfDataGrid in Xamarin.Forms 

1. Add the required assembly references to the pcl and renderer projects as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import SfDataGrid control namespace Syncfusion.SfDataGrid.XForms.

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

SfDataGrid is a data-bound control. Hence you must create a data model to bind it to the control. 

Create a simple data source as shown in the following code example in a new class file and save it as OrderInfo.cs file. 

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

N> If you want your data model to respond to property changes, then implement `INotifyPropertyChanged` interface in your model class

Create a model repository class with OrderInfo collection property initialized with required number of data objects in a new class file as shown in the following code example and save it as OrderInfoRepository.cs file.

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
        orderInfo.Add (new OrderInfo (1002, "Ana Trujilo", "Mexico", "ANATR", "México D.F."));
        orderInfo.Add (new OrderInfo (1003, "Ant Fuller", "Mexico", "ANTON", "México D.F."));
        orderInfo.Add (new OrderInfo (1004, "Thomas Hardy", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1005, "Tim Adams", "Sweden", "BERGS", "Luleå"));
        orderInfo.Add (new OrderInfo (1006, "Hanna Moos", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1007, "Andrew Fuller", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1008, "Martin King", "Spain", "BOLID", "Madrid"));
        orderInfo.Add (new OrderInfo (1009, "Lenny Lin", "France", "BONAP", "Marseille"));
        orderInfo.Add (new OrderInfo (1010, "John Carter", "Canada", "BOTTM", "Tsawassen"));
        orderInfo.Add (new OrderInfo (1011, "Lauro King", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1012, "Anne Wilson", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1013, "Alfki Kyle", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1014, "Gina Irene", "UK", "AROUT", "London"));
    }
}
{% endhighlight %}

## Binding data to SfDataGrid

In order to bind the data source of the SfDataGrid, set the [SfDataGrid.ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ItemsSource.html) property as shown below. You can bind the data source of the SfDataGrid either from XAML or in code. 

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

Now run the application to render the following output.

![](SfDataGrid_images/SfDataGrid-Xamarin_img3.png)

## Defining Columns

By default, the SfDataGrid automatically creates columns for all the properties in the data source. The type of the column generated depends on the type of data in the column. When the columns are auto-generated, you can handle the [SfDataGrid.AutoGeneratingColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGeneratingColumn_EV.html) event to customize or cancel the columns before they are added to the Columns collection in SfDataGrid.
 
You can also define the columns manually by setting the [SfDataGrid.AutoGenerateColumns](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGenerateColumns.html) property to false and by adding the GridColumn objects to the [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~Columns.html) collection. It can be done from both XAML and code. The following code example illustrates this. 

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

SfDataGrid allows you to apply sorting on its data by setting the [SfDataGrid.AllowSorting](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AllowSorting.html) property to true.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid AllowSorting="True" />
{% endhighlight %}
{% highlight c# %}
dataGrid.AllowSorting = true; 
{% endhighlight %}
{% endtabs %}

Run the application and touch the header cell to sort the data and the following output will be displayed.
 
![](SfDataGrid_images/SfDataGrid-Xamarin_img4.png)

You can also configure sorting by adding the column to the [SfDataGrid.SortColumnDescriptions](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SortColumnDescriptions.html) collection as below.

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

SfDataGrid allows you to group a column by adding the column to the [SfDataGrid.GroupColumnDescriptions](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GroupColumnDescriptions.html) collection as shown below.

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

![](SfDataGrid_images/SfDataGrid-Xamarin_img5.png)

## Selection

SfDataGrid allows you to select the row/rows by setting the [SfDataGrid.SelectionMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectionMode.html) property. You can set the `SfDataGrid.SelectionMode` property to single, multiple, single deselect or none based on your requirements. Information about the row/rows selected can be tracked using [SfDataGrid.SelectedItem](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedItem.html) and [SfDataGrid.SelectedItems](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedItems.html) properties.

You can handle the selection operations with the help of [SelectionChanging](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectionChanging_EV.html) and [SelectionChanged](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectionChanged_EV.html) events of the SfDataGrid.

## Launching the SfDataGrid inside a StackLayout

The StackLayout positions the child element one after the other, either horizontally or vertically in the order they were added. How much space the StackLayout will use depends on how the HorizontalOptions and VerticalOptions properties are set, but by default the StackLayout will try to use the entire screen.

SfDataGrid control can be loaded inside any layout such as GridLayout, StackLayout etc. When you load SfDataGrid inside a StackLayout, you have to set the Horizontal and/or VerticalOptions of the SfDataGrid and its parent to “LayoutOptions.FillAndExpand” based on the orientation of the container in which SfDataGrid is loaded.

Refer the following code example to load the SfDataGrid control inside a StackLayout. The VerticalOptions of the StackLayout and SfDataGrid alone is set as “FillAndExpand” as the default orientation of the StackLayout is vertical. In case, if the orientation of the StackLayout is horizontal, then you have to set the HorizontalOptions instead. In some case, you may have to set both the “VerticalOptions” and “HorizontalOptions” of the SfDataGrid based on its parent.

{% highlight xaml %}
<StackLayout VerticalOptions="FillAndExpand">
    <SearchBar Placeholder="UserName" TextChanged="searchBar_TextChanged" />
    <sfgrid:SfDataGrid x:Name="dataGrid"
                       ColumnSizer="Star"
                       ItemsSource="{Binding OrdersInfo}"
                       VerticalOptions="FillAndExpand" />
</StackLayout>
{% endhighlight %}

## Linker problem in Forms.iOS

There are some known framework issues in Forms.iOS platform.

When creating `Xamarin.Forms` samples that use SfDataGrid with `Linker behavior` in iOS renderer project as “Link Framework SDKs only”, sometimes `System.MethodMissingException` or `No method Count exists on type System.Linq.Queryable` exception will be thrown.

The above exceptions can be resolved by using the below workaround.

**Workaround:**

The above exceptions can be resolved in two ways.
 
1.	By setting LinkerBehavior as “Don’t Link” 
2.	By setting custom linker argument in iOS renderer project as like in below screenshot,


![](SfDataGrid_images/GettingStarted_img1.png)


Refer the following screenshot for the final outcome 

![](SfDataGrid_images/SfDataGrid-in-StackLayout.jpeg)