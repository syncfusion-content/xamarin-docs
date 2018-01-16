---
layout: post
title: Pull To Refresh | SfDataGrid | Xamarin | Syncfusion
description: How to perform pull to refresh and it's properties and customizations in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Pull To Refresh

The SfDataGrid allows `PullToRefresh` option by setting the [SfDataGrid.AllowPullToRefresh](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AllowPullToRefresh.html) property to `true`, and also by setting the [SfDataGrid.PullToRefreshCommand](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~PullToRefreshCommand.html) property. When `PullToRefresh` is enabled, the control refreshes the data source at runtime. 

### Pull to refresh command

The SfDataGrid allows refreshing the data in view at runtime by triggering an `ICommand` bound to the `SfDataGrid.PullToRefreshCommand` property. When the progress bar shows 100 %, this command is triggered to refresh the records in view. 

Set the [SfDataGrid.IsBusy](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~IsBusy.html) property to `true` before refreshing the records to notify the grid that pull to refresh action is being performed. Set the property to `false` after the view is refreshed. The pull to refresh animation time can also be altered from the sample by setting a delay based on the requirement.

To enable and perform pull to refresh operation, follow the code example:

{% highlight c# %}
//Enable PullToRefresh in SfDataGrid
dataGrid.AllowPullToRefresh = true;
dataGrid.PullToRefreshCommand = new Command(ExecutePullToRefreshCommand);
 
private async void ExecutePullToRefreshCommand()
{
    this.dataGrid.IsBusy = true;
    await Task.Delay(new TimeSpan(0, 0, 5));
    viewModel.ItemsSourceRefresh ();
    this.dataGrid.IsBusy = false;
} 

//ViewModel.cs
private OrderInfoRepository order;
public ViewModel()
{
    SetRowsToGenerate(50);
}

//ItemsSource
private ObservableCollection<OrderInfo> ordersInfo;

public ObservableCollection<OrderInfo> OrdersInfo
{
    get { return ordersInfo; }
    set { this.ordersInfo = value; }
}

//ItemsSource Generator
public void SetRowsToGenerate(int count)
{
    order = new OrderInfoRepository();
    ordersInfo = order.GetOrderDetails(count);
}

public void ItemsSourceRefresh()
{
    int count = random.Next (1, 6);

    for (int i = 11000; i < 11000 + count; i++) 
    {
        int value = i + random.Next (100, 150);
        this.OrdersInfo.Insert (0, order.RefreshItemsSource (value));
    }
} 

//OrderInfoRepository.cs
public ObservableCollection<OrderInfo> GetOrderDetails (int count)
{
    ObservableCollection<OrderInfo> orderDetails = new ObservableCollection<OrderInfo> ();

    for (int i = 10001; i <= count + 10000; i++) {
        var order = new OrderInfo () {
            OrderID = i,
            CustomerID = CustomerID [random.Next (7)],
            EmployeeID = random.Next (1700, 1800).ToString (),
            FirstName = FirstNames [random.Next (7)],
            LastName = LastNames [random.Next (7)]
        };
        orderDetails.Add (order);
    }
    return orderDetails;
}

public OrderInfo RefreshItemsource(int i)
{
    var order = new OrderInfo(){
        OrderID = i,
        CustomerID = CustomerID[random.Next(7)],
        EmployeeID = random.Next(1700, 1800).ToString(),
        FirstName = FirstNames[random.Next(7)],
        LastName = LastNames[random.Next(7)]
    };
    return order;
}

//Main DataSources
string[] FirstNames = new string[] {
    "Kyle",
    "Gina",
    "Irene",
    "Katie",
    "Michael",
    "Oscar",
    "Ralph"
};

string[] LastNames = new string[] {
    "Adams",
    "Crowley",
    "Ellis",
    "Gable",
    "Irvine",
    "Keefe",
    "Mendoza"
};

string[] CustomerID = new string[] {
    "Hanna",
    "Frans",
    "Maria",
    "John",
    "Andrew",
    "Fuller",
    "Carter"
};
{% endhighlight %}

Running application renders the following output:

![](SfDataGrid_images/PullToRefresh.png)
