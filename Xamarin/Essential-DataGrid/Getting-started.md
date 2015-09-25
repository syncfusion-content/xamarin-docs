---
layout: post
title: Getting started | Essential DataGrid | Xamarin | Syncfusion
description: getting started
platform: xamarin
control: Essential-DataGrid
documentation: ug
---

# Getting started

This section provides a quick overview for working with Essential DataGridfor Xamarin.Android, Xamarin.Forms and Xamarin.iOS. After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\13.2.0.29\lib


N> Assemblies are available in unzipped package location in Mac.

## Essential DataGrid for Android

This topic describes about the assembly that is required in your Android application, when you use SfDataGrid.

Add the following assemblies to your Android project.

Syncfusion.Linq.Android.dll

Syncfusion.SfDataGrid.Android.dll

Syncfusion.GridCommon.Portable.dll



## Essential DataGrid for iOS

This topic describes about the assembly that is required in your iOS application, when you use SfDataGrid.

Add the following assemblies to your iOS project.

Syncfusion.Linq.iOS.dll

Syncfusion.SfDataGrid.iOS.dll

Syncfusion.GridCommon.Portable.dll



## Essential DataGrid for Xamarin.Forms

This topic describes the assembly required in your Forms application when you use the SfDataGrid.

Add the following assemblies to the respective projects as follows:

### PCL project:

pcl\Syncfusion.Data.Portable.dll

pcl\Syncfusion.GridCommon.Portable.dll

pcl\Syncfusion.SfDataGrid.XForms.dll

### Android project:

android\Syncfusion.SfDataGrid.XForms.Android.dll

### iOS project:

pcl\Syncfusion.GridCommon.Portable.dll

ios\Syncfusion.SfDataGrid.XForms.iOS.dll

### WindowsPhone project:

wp8\Syncfusion.SfDataGrid.XForms.WinPhone.dll

Currently, an additional step is required for Windows Phone and iOS projects. You need to initialize the DataGrid renderer. Call the SfDataGridRenderer.Init() in the MainPage constructor of the Windows Phone project as follows.

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

## Create you first DataGrid in Xamarin.Android

This section explains how to create a DataGrid and configure it.

1.Create a new Android application in XamarinStudio.

2.Now, create a simple data source as shown in the following code example. Add the following code example in a newly created class file and save it as OrderInfo.cs file.

{% highlight C# %}  
public class OrderInfo 
{
private int orderID;
private string customerID;
private string customer;
private string shipCity;
private string shipCountry;

public int OrderID  
{
get 
{ 
     return orderID; 
}
set 
{ 
	this.orderID  =  value; 
}
}

public string CustomerID  
{
get 
{ 
    return customerID; 
}
set 
{ 
	this.customerID  =  value; 
}
}

public string ShipCountry  
{
get  
{ 
    return shipCountry; 
}
 set 
{ 
	this.shipCountry  =  value; 
}
}

public string Customer  
{
get  
{ 
    return this.customer; 
}
set  
{ 
	this.customer  =  value; 
}
}

public string ShipCity  
{
get  
{ 
    return shipCity; 
}
set  
{ 
	this.shipCity  =  value; 
}
}

public OrderInfo  (int orderId,  string customerId,  string country,  string customer,  string shipCity) 
{
    this.OrderID  =  orderId;
    this.CustomerID  =  customerId;
   	this.Customer  =  customer;
   	this.ShipCountry  =  country;
   	this.ShipCity  =  shipCity;
}  
}
 
{% endhighlight %}
  




3.Add the following code example in a newly created class file and save it as OrderInfoRepositiory.cs file.

{% highlight C# %}  

public class OrderInfoRepository 
{
private ObservableCollection < OrderInfo >  orderInfo;
public ObservableCollection < OrderInfo >  OrderInfoCollection  
{
get  
{ 
	return orderInfo; 
}
set  
{ 
	this.orderInfo  =  value; 
}
}
public OrderInfoRepository  () 
{
	orderInfo  =  new ObservableCollection < OrderInfo >   ();
	this.GenerateOrders  ();
}

private void GenerateOrders  () 
{
	orderInfo.Add  (new OrderInfo  (1001,  
	"Maria Anders",  
	"Germany",  
	"ALFKI",  
	"Berlin"));
	orderInfo.Add  (new OrderInfo  (1002,  
	"Ana Trujilo",  
	"Mexico",  
	"ANATR",  
	"México D.F."));
	orderInfo.Add  (new OrderInfo  (1003,  
	"Ant Fuller",  
	"Mexico",  
	"ANTON",  
	"México D.F."));
	orderInfo.Add  (new OrderInfo  (1004,  
	"Thomas Hardy",  
	"UK",  
	"AROUT",  
	"London"));
	orderInfo.Add  (new OrderInfo  (1005,  
	"Tim Adams",  
	"Sweden",  
	"BERGS",  
	"Luleå"));
	orderInfo.Add  (new OrderInfo  (1006,  
	"Hanna Moos",  
	"Germany",  
	"BLAUS",  
	"Mannheim"));
	orderInfo.Add  (new OrderInfo  (1007,  
	"Andrew Fuller",  
	"France",  
	"BLONP",  
	"Strasbourg"));
	orderInfo.Add  (new OrderInfo  (1008,  
	"Martin King",  
	"Spain",  
	"BOLID",  
	"Madrid"));
	orderInfo.Add  (new OrderInfo  (1009,  
	"Lenny Lin",  
	"France",  
	"BONAP",  
	"Marseille"));
	orderInfo.Add  (new OrderInfo  (1010,  
	"John Carter",  
	"Canada",  
	"BOTTM",  
	"Tsawassen"));
	orderInfo.Add  (new OrderInfo  (1011,  
	"Lauro King",  
	"UK",  
	"AROUT",  
	"London"));
	orderInfo.Add  (new OrderInfo  (1012,  
	"Anne Wilson",  
	"Germany",  
	"BLAUS",  
	"Mannheim"));
}
}

{% endhighlight %}
  


4.You can set the data source of the DataGrid by using the SfDataGrid.ItemsSource property as follows.

{% highlight C# %}  

[Activity  (Label  =  "GettingStarted",  MainLauncher  =  true)]
public class MainActivity :  Activity 
{
SfDataGrid sfGrid;
protected override void OnCreate  (Bundle bundle) 
{
	base.OnCreate  (bundle);
	SetContentView  (Resource.Layout.Main);
	RelativeLayout layout  =   (RelativeLayout) FindViewById  (Resource.Id.Relative);
	sfGrid  =  new SfDataGrid  (BaseContext);
	sfGrid.ItemsSource  =   (new OrderInfoRepository  ().OrderInfoCollection);
	layout.AddView  (sfGrid);
}
}
	
{% endhighlight %}
  
5.By default, the Essential DataGrid for Android automatically creates columns for all properties in the data source.

6.Run the application to render the following output.


![](Create-you-first-DataGrid-in-XamarinAndroid_images/img1.png)


7.You can also define the columns manually by setting the SfDataGrid.AutoGenerateColumns property to false and add the GridColumn objects to the SfDataGrid.Columns collection. The following code example illustrates this.

{% highlight C# %}  

sfGrid.AutoGenerateColumns    =  false;

GridTextColumn orderIdColumn  =  new GridTextColumn  ();
orderIdColumn.MappingName     =  "OrderID";
orderIdColumn.HeaderText      =  "Order ID";


GridTextColumn customerIdColumn  =  new GridTextColumn  ();
customerIdColumn.MappingName     =  "CustomerID";
customerIdColumn.HeaderText      =  "Customer ID";


GridTextColumn customerColumn  =  new GridTextColumn  ();
customerColumn.MappingName     =  "Customer";
customerColumn.HeaderText      =  "Customer";


GridTextColumn countryColumn  =  new GridTextColumn  ();
countryColumn.MappingName     =  "ShipCountry";
countryColumn.HeaderText      =  "Ship Country";


sfGrid.Columns.Add  (orderIdColumn);
sfGrid.Columns.Add  (customerIdColumn);
sfGrid.Columns.Add  (customerColumn);
sfGrid.Columns.Add  (countryColumn);
	
{% endhighlight %}
  






8.Essential DataGrid for Android allows you to apply sorting on its data by setting AllowSorting to true. The following code illustrates this.

{% highlight C# %}  

    sfGrid.AllowSorting = true; 
	
{% endhighlight %}
  




9.Run the application and touch the header cell to sort the data and the following output is displayed. 

   ![](Create-you-first-DataGrid-in-XamarinAndroid_images/img2.png)

10.You can also specify the column to be sorted from the code behind by adding the column to the SfDataGrid.SortColumnDescriptions collection. The following code illustrates this.


{% highlight C# %}  

sfGrid.SortColumnDescriptions.Add (new SortColumnDescription () 
{ 
	ColumnName = "OrderID" 
});
	
{% endhighlight %}
   


11.Essential DataGrid for Android allows you to group a column by adding the column to the SfDataGrid.GroupColumnDescriptions collection. The following code example illustrates this.
    
{% highlight C# %}        

sfGrid.GroupColumnDescriptions.Add (new GroupColumnDescription ()
{ 
	ColumnName = "ShipCountry" 
}); 
	
{% endhighlight %}
   





12.Run the application to render the following output.

![](Create-you-first-DataGrid-in-XamarinAndroid_images/img3.png)

13.Essential DataGrid for Android allows you to filter the records in the view by using the SfDataGrid.View.Filter property. You have to call SfDataGrid.View.RefreshFilter() method after assigning the Filter property for the records to get filtered in view. The following code example illustrates this.

{% highlight C# %}  

//Create an EditText in the layout and assign its text to a property. When the property gets changed, run the below code for filtering the view.


if  (sfGrid.View  !=  null)  
{
	this.sfGrid.View.Filter  =  viewModel.FilerRecords;
	this.sfGrid.View.RefreshFilter  ();
}

//create a method FilterRecords in the viewModel
public bool FilerRecords  (object orderInfo) 
{

	 //your code

	 //For Example

	var order  =  orderInfo as OrderInfo;
	if  (order.CustomerID.Contains  ("An")) return true;
	false;
}

{% endhighlight %}
   

## Create your first DataGrid in Xamarin.Forms

This section explains how to create a DataGrid and configure it. The DataGrid control can be configured entirely in C# code or by using XAML markup.

1.Create a new BlankApp (Xamarin.Forms.Portable) application in XamarinStudio or Visual Studio.
2.Now, create a simple DataSource as shown in the following code example. Add the following code example in a newly created class file and save it as OrderInfo.cs file.

{% highlight C# %}  

public class OrderInfo
{
private int orderID;
private string customerID;
private string customer;
private string shipCity;
private string shipCountry;

public int OrderID 
{
get 
{ 
	return orderID; 		
}
set 
{ 
	this.orderID = value; 
}
}

public string CustomerID 
{
get 
{ 
	return customerID; 
}
set 
{ 
	this.customerID = value; 
}
}

public string ShipCountry 
{
get 
{ 
	return shipCountry; 
}
set 
{ 
	this.shipCountry = value; 
}
}
				
public string Customer 
{
get 
{ 
	return this.customer; 
}
set 
{ 
	this.customer = value; 
}
}
				
public string ShipCity 
{
get 
{ 
	return shipCity; 
}
set 
{ 
	this.shipCity = value; 
}
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
  

3.Add the following code example in the newly created class file and save it as OrderInfoRepositiory.cs file.


{% highlight C# %}  

public class OrderInfoRepository 
{
private ObservableCollection < OrderInfo >  orderInfo;
public ObservableCollection < OrderInfo >  OrderInfoCollection  
{
get  
{ 
	return orderInfo; 
}
set  
{ 
	this.orderInfo  =  value; 
}
}
public OrderInfoRepository  () 
{
	orderInfo  =  new ObservableCollection < OrderInfo >   ();
	this.GenerateOrders  ();
}
private void GenerateOrders  () 
{
	orderInfo.Add  (new OrderInfo  (1001,  
	"Maria Anders",  
	"Germany",  
	"ALFKI",  
	"Berlin"));
	orderInfo.Add  (new OrderInfo  (1002,  
	"Ana Trujilo",  
	"Mexico",  
	"ANATR",  
	"México D.F."));
	orderInfo.Add  (new OrderInfo  (1003,  
	"Ant Fuller",  
	"Mexico",  
	"ANTON",  
	"México D.F."));
	orderInfo.Add  (new OrderInfo  (1004,  
	"Thomas Hardy",  
	"UK",  
	"AROUT",  
	"London"));
	orderInfo.Add  (new OrderInfo  (1005,  
	"Tim Adams",  
	"Sweden",  
	"BERGS",  
	"Luleå"));
	orderInfo.Add  (new OrderInfo  (1006,  
	"Hanna Moos",  
	"Germany",  
	"BLAUS",  
	"Mannheim"));
	orderInfo.Add  (new OrderInfo  (1007,  
	"Andrew Fuller",  
	"France",  
	"BLONP",  
	"Strasbourg"));
	orderInfo.Add  (new OrderInfo  (1008,  
	"Martin King",  
	"Spain",  
	"BOLID",  
	"Madrid"));
	orderInfo.Add  (new OrderInfo  (1009,  
	"Lenny Lin",  
	"France",  
	"BONAP",  
	"Marseille"));
	orderInfo.Add  (new OrderInfo  (1010,  
	"John Carter",  
	"Canada",  
	"BOTTM",  
	"Tsawassen"));
	orderInfo.Add  (new OrderInfo  (1011,  
	"Lauro King",  
	"UK",  
	"AROUT",  
	"London"));
	orderInfo.Add  (new OrderInfo  (1012,  
	"Anne Wilson",  
	"Germany",  
	"BLAUS",  
	"Mannheim"));
}
}

{% endhighlight %}
  

4.You can set the Data Source of the DataGrid by using the SfDataGrid.ItemsSource property as follows.


{% highlight C# %}       

public class App: Application
{

SfDataGrid sfGrid;

public App() 
{
 	sfGrid = new SfDataGrid();
 	sfGrid.ItemsSource  =  new OrderInfoRepository().OrderInfoCollection;
 	MainPage = new ContentPage 
	{
 		Content = sfGrid;
 	};
}
}          
	
{% endhighlight %}
  

{% highlight xml %}        

xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
			
	<sfgrid:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrderInfoCollection}" /> 
		
	
{% endhighlight %}
  

5.By default, the Essential DataGrid for Xamarin.Forms automatically creates columns for all the properties in the DataSource. 
6.Run the application to render the following output.

![](Create-your-first-DataGrid-in-XamarinForms_images/img1.png)


7.You can also define the columns manually by setting the SfDataGrid.AutoGenerateColumns property to false and by adding the GridColumn objects to the SfDataGrid.Columns collection. The following code example illustrates this. 

{% highlight C# %}  
     
sfGrid.AutoGenerateColumns = false;
			
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
countryColumn.HeaderText = "Ship Country";
			
sfGrid.Columns.Add (orderIdColumn);
sfGrid.Columns.Add (customerIdColumn);
sfGrid.Columns.Add (customerColumn);
sfGrid.Columns.Add (countryColumn);             
	
{% endhighlight %}
  

{% highlight xml %}       

<sfgrid:SfDataGrid.Columns x:TypeArguments="sfgrid:Columns">
			
<sfgrid:GridTextColumn HeaderText="Order ID" MappingName="OrderID" />
<sfgrid:GridTextColumn HeaderText="Customer ID" MappingName="CustomerID" />
<sfgrid:GridTextColumn MappingName="Customer" />
<sfgrid:GridTextColumn HeaderText="Ship Country" MappingName="ShipCountry" />			
</sfgrid:SfDataGrid.Columns> 
	
{% endhighlight %}
  


8.Essential DataGrid for Xamarin.Forms allows you to sort its data by setting AllowSorting to true. The following code illustrates this.

{% highlight C# %}       

sfGrid.AllowSorting = true; 
	
{% endhighlight %}
  

{% highlight xml %} 

<sfgrid:SfDataGrid AllowSorting="True" />
	
{% endhighlight %}
  


9.Run the application and touch the header cell to sort the data and the following output is displayed. 

   ![](Create-your-first-DataGrid-in-XamarinForms_images/img2.png)



10.You can also specify the column to be sorted from the code behind by adding the column to the SfDataGrid.SortColumnDescriptions collection. The following code illustrates this.


{% highlight C# %}  

sfGrid.SortColumnDescriptions.Add (new SortColumnDescription () { ColumnName = "CustomerID" });
	
{% endhighlight %}
   

{% highlight xml %}       

<sfgrid:SfDataGrid.SortColumnDescriptions>
<sfgrid:SortColumnDescription ColumnName="CustomerID" />
</sfgrid:SfDataGrid.SortColumnDescriptions> 
	
{% endhighlight %}
   






11.Essential DataGrid for Xamarin.Forms allows you to group a column by adding the column to the SfDataGrid.GroupColumnDescriptions collection. The following code example illustrates this.

{% highlight C# %}  

sfGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () 
{ 
ColumnName = "ShipCountry" 
});
	
{% endhighlight %}
   
{% highlight xml %} 

<sfgrid:SfDataGrid.GroupColumnDescriptions>
<sfgrid:GroupColumnDescription ColumnName="ShipCountry" />
</sfgrid:SfDataGrid.GroupColumnDescriptions> 
	
{% endhighlight %}
   

12.Run the application to render the following output.

![](Create-your-first-DataGrid-in-XamarinForms_images/img3.png)



13.Essential DataGrid for Xamarin.Forms allows you to filter the records in the view by using the SfDataGrid.View.Filter property. You have to call the SfDataGrid.View.RefreshFilter() method after assigning the Filter property for the records to get filtered in view. The following code example illustrates this.


{% highlight C# %}  

//Create a SearchBar in the layout and assign its text to a property. When the property gets changed, run the following code for filtering the view. 
			
if (sfGrid.View != null) 
{
this.sfGrid.View.Filter = viewModel.FilerRecords;
this.sfGrid.View.RefreshFilter ();
} 
			
//Create a method FilterRecords in the viewModel.
			
public bool FilerRecords (object orderInfo)
{
//Your code.
				
//For Example.
				
var order = orderInfo as OrderInfo;
if (order.CustomerID.Contains ("An"))
return true;
false;
} 
	
{% endhighlight %}
   
	
## Create you first DataGrid in Xamarin.iOS

This section explains how to create a DataGrid and configure it.

1.Create new iOS application in XamarinStudio.

2.Now, create a simple data source as shown in the following code example. Add the following code example in a newly created class file and save it as OrderInfo.cs file.


{% highlight C# %}         

public class OrderInfo
{
private int orderID;
private string customerID;
private string customer;
private string shipCity;
private string shipCountry;

public int OrderID 
{
get 
{ 
	return orderID; 
}
set 
{ 
	this.orderID = value; 
}
}

public string CustomerID 
{
get 
{ 
	return customerID; 
}
set 
{ 
	this.customerID = value; 
}
}

public string ShipCountry 
{
get 
{ 
	return shipCountry; 
}
set 
{ 
	this.shipCountry = value; 
}
	}
				
public string Customer 
{
get 
{ 
	return this.customer; 
}
set 
{ 
	this.customer = value; 
}
}
				
public string ShipCity 
{
get 
{ 
	return shipCity; 
}
set 
{ 
	this.shipCity = value; 
}
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
  


3.Add the following code example in a newly created class file and save it as OrderInfoRepositiory.cs file.

{% highlight C# %}  
       
public class OrderInfoRepository
{
private ObservableCollection<OrderInfo> orderInfo;
public ObservableCollection<OrderInfo> OrderInfoCollection 
{
get 
{ 
	return orderInfo; 
}
set 
{ 
	this.orderInfo = value; 
}
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
}
} 
	
{% endhighlight %}
  

4.You can set the data source of the DataGrid by using the SfDataGrid.ItemsSource property as follows.


{% highlight C# %}        

public partial class GettingStartedViewController : UIViewController
{
SfDataGrid sfGrid;
				
static bool UserInterfaceIdiomIsPhone 
{
get 
{ 
	return UIDevice.CurrentDevice.UserInterfaceIdiom == UIUserInterfaceIdiom.Phone; 
}
}
				
public GettingStartedViewController ()
	: base (UserInterfaceIdiomIsPhone ? "GettingStartedViewController_iPhone" : "GettingStartedViewController_iPad", null)
{
	sfGrid = new SfDataGrid ();
	sfGrid.ItemsSource = (new OrderInfoRepository ().OrderInfoCollection);
	sfGrid.HeaderRowHeight = 45;
	sfGrid.RowHeight = 45;
}
				
public override void ViewDidLoad ()
{
	base.ViewDidLoad ();
	sfGrid.Frame = new CGRect (0, 30, View.Frame.Width, View.Frame.Height);
	View.AddSubview (sfGrid);
}
} 
	
{% endhighlight %}
  


5.By default, the Essential DataGrid for iOS automatically creates columns for all the properties in the data source. 

6.Run the application to render the following output.

![](Create-you-first-DataGrid-in-XamariniOS_images/img1.png)


7.You can also define the columns manually by setting the SfDataGrid.AutoGenerateColumns property to false and add the GridColumn objects to the SfDataGrid.Columns collection. The following code example illustrates this. 


{% highlight C# %}         

sfGrid.AutoGenerateColumns = false;
			
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
countryColumn.HeaderText = "Ship Country";
			
sfGrid.Columns.Add (orderIdColumn);
sfGrid.Columns.Add (customerIdColumn);
sfGrid.Columns.Add (customerColumn);
sfGrid.Columns.Add (countryColumn); 
	
{% endhighlight %}
  

8.Essential DataGrid for iOS allows you to apply sorting on its data by setting AllowSorting to true. The following code illustrates this.

{% highlight C# %} 

    sfGrid.AllowSorting = true; 
			
{% endhighlight %}
  


9.Run the application and touch the header cell to sort the data and the following output is displayed. 


![](Create-you-first-DataGrid-in-XamariniOS_images/img2.png)



10.You can also specify the column to be sorted from the code behind by adding the column to the SfDataGrid.SortColumnDescriptions collection. The following code illustrates this.

{% highlight C# %}  

sfGrid.SortColumnDescriptions.Add (new SortColumnDescription () 
{ 

	ColumnName = "OrderID" 

});
	
{% endhighlight %}
   


11.Essential DataGrid for iOS allows you to group a column by adding the column to the SfDataGrid.GroupColumnDescriptions collection. Following code example illustrates this.

{% highlight C# %}  

sfGrid.GroupColumnDescriptions.Add (new GroupColumnDescription ()
{ 
	ColumnName = "ShipCountry" 
}); 
	
{% endhighlight %}
   




12.Run the application to render the following output.

![](Create-you-first-DataGrid-in-XamariniOS_images/img3.png)


13.Essential DataGrid for iOS allows you to filter the records in the view by using the SfDataGrid.View.Filter property. You have to call SfDataGrid.View.RefreshFilter() method after assigning the Filter property for the records to get filtered in view. The following code example illustrates this.


{% highlight C# %}        

//Create an EditText in the layout and assign its text to a property. When the property gets changed, run the below code for filtering the view.


if  (sfGrid.View  !=  null)  
{
    this.sfGrid.View.Filter  =  viewModel.FilerRecords;
    this.sfGrid.View.RefreshFilter  ();
}

 //create a method FilterRecords in the viewModel
public bool FilerRecords  (object orderInfo) 
{

    //your code

     //For Example

    var order  =  orderInfo as OrderInfo;
    if  (order.CustomerID.Contains  ("An")) return true;
    false;
}
	 
{% endhighlight %}
	
   
	

