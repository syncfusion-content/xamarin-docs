---
layout: post
title: Getting started | SfDataGrid | Xamarin | Syncfusion
description: Getting started with SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: ug
---

# Getting Started

This section provides a quick overview for working with [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) for **Xamarin.Forms**, **Xamarin.Android** and **Xamarin.iOS**. You will walk through the entire process of creating a real world [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).


## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

N> Assemblies can be found in unzipped package location in Mac

### SfDataGrid for Xamarin.Forms

The following list of assemblies need to be added as reference from the lib folder to use [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) in your application.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Pcl</td>
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
<td>WindowsPhone Renderer</td>
<td>pcl\Syncfusion.Data.Portable.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfDataGrid.XForms.dll<br/>wp8\Syncfusion.SfDataGrid.XForms.WinPhone.dll<br/></td>
</tr>
<tr>
<td>WindowsPhone 8.1 Renderer</td>
<td>pcl\Syncfusion.Data.Portable.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfDataGrid.XForms.dll<br/>wp81\Syncfusion.SfDataGrid.XForms.WinPhone.dll<br/></td>
</tr>
<tr>
<td>WinRT Renderer</td>
<td>pcl\Syncfusion.Data.Portable.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfDataGrid.XForms.dll<br/>winrt\Syncfusion.SfDataGrid.XForms.WinRT.dll<br/></td>
</tr>
</table>

In order to use export to excel and export to pdf functionalities of [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html), add the below assembly to your pcl project.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Pcl</td>
<td>pcl\Syncfusion.SfGridConverter.XForms.dll<br/>pcl\Syncfusion.Compression.Portable.dll<br/>pcl\Syncfusion.Pdf.Portable.dll<br/>pcl\Syncfusion.XlsIO.Portable.dll<br/></td>
</tr>
</table>

Currently, an additional step is required for Windows Phone, WindowsPhone 8.1, WinRT and iOS projects. You need to initialize the SfDataGridRenderer. 

Call the SfDataGridRenderer.Init() in the MainPage constructor of the Windows Phone, Windows Phone 8.1 and WinRT projects as follows.

{% highlight c# %}
public MainPage()
{
    …
    SfDataGridRenderer.Init();
    …
}
{% endhighlight %}

Call the SfDataGridRenderer.Init() in the FinishedLaunching overridden method of the AppDelegate class in the iOS Project as follows.

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    SfDataGridRenderer.Init();
    …
}
{% endhighlight %}

### SfDataGrid for Xamarin.Android and Xamrain.iOS

The following list of assemblies need to be added as reference from the lib folder to use [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) in your application.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.Android</td>
<td>Syncfusion.Linq.Android.dll<br/>Syncfusion.SfDataGrid.Android.dll<br/>Syncfusion.GridCommon.Portable.dll<br/></td>
</tr>
<tr>
<td>Xamarin.iOS</td>
<td>Syncfusion.Linq.iOS.dll<br/>Syncfusion.SfDataGrid.iOS.dll<br/>Syncfusion.GridCommon.Portable.dll<br/></td>
</tr>
</table>

In order to use export to excel and export to pdf functionalities of [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html), add the below assembly to your project.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.Android</td>
<td>Syncfusion.SfGridConverter.Android.dll<br/>pcl\Syncfusion.Compression.Portable.dll<br/>pcl\Syncfusion.Pdf.Portable.dll<br/>pcl\Syncfusion.XlsIO.Portable.dll<br/></td>
</tr>
<tr>
<td>Xamarin.iOS</td>
<td>Syncfusion.SfGridConverter.iOS.dll<br/>pcl\Syncfusion.Compression.Portable.dll<br/>pcl\Syncfusion.Pdf.Portable.dll<br/>pcl\Syncfusion.XlsIO.Portable.dll<br/></td>
</tr>
</table>


## Create a simple SfDataGrid 

This section explains how to create a [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) and configure it. The [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) control can be configured entirely in C# code or by using XAML markup. This is how the final output will look like on iOS, Android and Windows Phone devices.
 
![](SfDataGrid_images/SfDataGrid-Xamarin_img2.png)

You can download the entire source code of this demo for **Xamarin.Forms** from [here](http://files2.syncfusion.com/Installs/v13.2.0.29/Samples/Xamarin/DataGrid_GettingStartedForms.zip).
 
You can download the entire source code of this demo for **Xamarin.Android** from [here](http://files2.syncfusion.com/Installs/v13.2.0.29/Samples/Xamarin/DataGrid_GettingStartedAndroid.zip).
 
You can download the entire source code of this demo for **Xamarin.iOS** from [here](http://files2.syncfusion.com/Installs/v13.2.0.29/Samples/Xamarin/DataGrid_GettingStartediOS.zip). 

In this walk through, you will create a new application that contains the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) which includes the below topics.

* [Creating the project](#creating-the-project) 
* [Adding SfDataGrid in Xamarin.Forms](#adding-sfdatagrid-in-xamarinforms) 
* [Adding SfDataGrid in Xamarin.Android](#adding-sfdatagrid-in-xamarinandroid) 
* [Adding SfDataGrid in Xamarin.iOS](#adding-sfdatagrid-in-xamarinios)
* [Create data model](#create-datamodel-for-the-sfdatagrid)  
* [Binding data](#binding-data-to-sfdatagrid) 
* [Defining columns](#defining-columns) 
* [Sorting](#sorting) 
* [Grouping](#grouping) 
* [Selection](#selection)

## Creating the project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for **Xamarin.Forms**.

Create a new Android application in Xamarin Studio or Visual Studio for **Xamarin.Android**.

Create a new iOS application in Xamarin Studio or Visual Studio for **Xamarin.iOS**.

## Adding SfDataGrid in Xamarin.Forms 

1. Add the required assembly references to the pcl and renderer projects as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) control namespace Syncfusion.SfDataGrid.XForms.

3. Set the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) control as content to the ContentPage.


{% tabs %}
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
{% endtabs %}

## Adding SfDataGrid in Xamarin.Android

1. Add the required assembly references to the project as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) control namespace Syncfusion.SfDataGrid.

3. Create an instance of [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) control and add as a child to the view hosted in the Activity.

{% highlight c# %}
using Syncfusion.SfDataGrid; 

[Activity (Label = "GettingStarted", MainLauncher = true)]
public class MainActivity : Activity
{
    SfDataGrid dataGrid;
    protected override void OnCreate (Bundle bundle)
    {
        base.OnCreate (bundle);
        SetContentView (Resource.Layout.Main);
        RelativeLayout layout = (RelativeLayout)FindViewById (Resource.Id.Relative);
        dataGrid = new SfDataGrid (BaseContext);
        layout.AddView (dataGrid);
    }
}
{% endhighlight %}

## Adding SfDataGrid in Xamarin.iOS

1. Add the required assembly references to the project as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) control namespace Syncfusion.SfDataGrid.

3. Create an instance of [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) control and add as a SubView to a UIViewController.


{% highlight c# %}
using Syncfusion.SfDataGrid; 
public partial class GettingStartedViewController : UIViewController
{
    SfDataGrid dataGrid;

    static bool UserInterfaceIdiomIsPhone {
        get { return UIDevice.CurrentDevice.UserInterfaceIdiom == UIUserInterfaceIdiom.Phone; }
    }

    public GettingStartedViewController ()
        : base (UserInterfaceIdiomIsPhone ? "GettingStartedViewController_iPhone" : "GettingStartedViewController_iPad", null)
    {
        dataGrid = new SfDataGrid ();
        dataGrid.HeaderRowHeight = 45;
        dataGrid.RowHeight = 45;
    }

    public override void ViewDidLoad ()
    {
        base.ViewDidLoad ();
        dataGrid.Frame = new CGRect (0, 30, View.Frame.Width, View.Frame.Height);
        View.AddSubview (dataGrid);
    }
}
{% endhighlight %}

## Create DataModel for the SfDataGrid

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) is a data-bound control. Hence you must create a data model to bind it to the control. 

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

N> If you want your data model to respond to property changes, then implement INotifyPropertyChanged interface in your model class

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

In order to bind the data source of the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html), set the **SfDataGrid.ItemsSource** property as shown below. You can bind the data source of the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) either from XAML or in code. 

The following code example binds the collection created in previous step to **SfDataGrid.ItemsSource** property.

{% tabs %}
{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
{% endhighlight %}
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
{% endtabs %}

Now run the application to render the following output.

![](SfDataGrid_images/SfDataGrid-Xamarin_img3.png)

## Defining Columns

By default, the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) automatically creates columns for all the properties in the data source. The type of the column generated depends on the type of data in the column. When the columns are auto-generated, you can handle the AutoGeneratingColumn event to customize or cancel the columns before they are added to the Columns collection in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).
 
You can also define the columns manually by setting the **SfDataGrid.AutoGenerateColumns** property to false and by adding the GridColumn objects to the **SfDataGrid.Columns** collection. It can be done from both XAML and code. The following code example illustrates this. 

{% tabs %}
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
{% endtabs %}

## Sorting

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to apply sorting on its data by setting the **SfDataGrid.AllowSorting** property to true.
 
{% tabs %}
{% highlight c# %}
dataGrid.AllowSorting = true; 
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfDataGrid AllowSorting="True" />
{% endhighlight %}
{% endtabs %}

Run the application and touch the header cell to sort the data and the following output will be displayed.
 
![](SfDataGrid_images/SfDataGrid-Xamarin_img4.png)

You can also configure sorting by adding the column to the **SfDataGrid.SortColumnDescriptions** collection as below.

{% tabs %}
{% highlight c# %}
dataGrid.SortColumnDescriptions.Add (new SortColumnDescription () { ColumnName = "CustomerID" });
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfDataGrid.SortColumnDescriptions>
    <syncfusion:SortColumnDescription ColumnName="CustomerID" />
</syncfusion:SfDataGrid.SortColumnDescriptions> 
{% endhighlight %}
{% endtabs %}

## Grouping

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to group a column by adding the column to the **SfDataGrid.GroupColumnDescriptions** collection as shown below.

{% tabs %}
{% highlight c# %}
dataGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () { ColumnName = "ShipCountry" });
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfDataGrid.GroupColumnDescriptions>
    <syncfusion:GroupColumnDescription ColumnName="ShipCountry" />
</syncfusion:SfDataGrid.GroupColumnDescriptions> 
{% endhighlight %}
{% endtabs %}

Run the application to render the following output. 

![](SfDataGrid_images/SfDataGrid-Xamarin_img5.png)

## Selection

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to select the row/rows by setting the **SfDataGrid.SelectionMode** property. You can set the **SfDataGrid.SelectionMode** property to single, multiple, single deselect or none based on your requirements. Information about the row/rows selected can be tracked using **SfDataGrid.SelectedItem** and **SfDataGrid.SelectedItems** properties.

You can handle the selection operations with the help of **SelectionChanging** and **SelectionChanged** events of the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).
