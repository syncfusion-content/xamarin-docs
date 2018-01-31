---
layout: post
title: Data Binding | SfDataGrid | Xamarin | Syncfusion
description: Data Binding and different sources that can be bound to a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Data Binding

The SfDataGrid is bound to an external data source to display the data. It supports the data sources such as [List](https://msdn.microsoft.com/en-us/library/6sh2ey19(v=vs.110).aspx), [ObservableCollection](https://msdn.microsoft.com/en-us/library/ms668604(v=vs.110).aspx), and so on. [SfDataGrid.ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ItemsSource.html) property helps to bind the SfDataGrid with the collection of objects.

In order to bind the data source of the SfDataGrid, set the `SfDataGrid.ItemsSource` property as shown below such that each row in the SfDataGrid would bind to an object in the data source and each column would bind to a property in the data model object.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DataGridDemo;assembly=DataGridDemo"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms" 
             x:Class="DataGridDemo.Sample">

    <ContentPage.BindingContext>
        <local:OrderInfoRepository x:Name="viewModel" />
    </ContentPage.BindingContext>

    <ContentPage.Content>
        <syncfusion:SfDataGrid x:Name="dataGrid"
                               ItemsSource="{Binding OrderInfoCollection}">
        </syncfusion:SfDataGrid>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %} 
{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
{% endhighlight %}
{% endtabs %}

If the data source implements `ICollectionChanged` interface, then SfDataGrid will automatically refresh the view when an item is added, removed or cleared. When you add or remove an item in `ObservableCollection`, the SfDataGrid automatically refreshes the view as the `ObservableCollection` implements the [INotifyCollectionChanged](https://msdn.microsoft.com/en-us/library/system.collections.specialized.inotifycollectionchanged(v=vs.110).aspx). But when you do the same in `List`, SfDataGrid will not refresh the view automatically.

If the data model implements the [INotifyPropertyChanged](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifypropertychanged(v=vs.110).aspx) interface, then the SfDataGrid responds to the property change in runtime to update the view.

N> SfDataGrid does not supports `DataTable` binding in `Xamarin.Forms` since `System.Data` is inaccessible in `Portable Class Library`.

## Binding with IEnumerable

SfDataGrid control supports to bind any collection that implements the [IEnumerable](https://msdn.microsoft.com/en-us/library/system.collections.ienumerable) interface. All the data operations such as sorting, grouping, filtering are supported when you are binding collection derived from `IEnumerable`.

## Binding Complex properties

SfDataGrid control provides support to bind complex property to its columns. To bind the complex property to [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html), set the complex property path to [MappingName](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~MappingName.html).

{% tabs %}
{% highlight xaml %}
<sfGrid:SfDataGrid x:Name="dataGrid"
                   AutoGenerateColumns="False"
                   ItemsSource="{Binding OrdersInfo}">
    <sfGrid:SfDataGrid.Columns>
        <sfGrid:GridTextColumn MappingName="OrderID.Order" />
        <sfGrid:GridTextColumn MappingName="CustomerID" />
        <sfGrid:GridTextColumn MappingName="Freight" />
        <sfGrid:GridTextColumn MappingName="Country" />
    </sfGrid:SfDataGrid.Columns>
</sfGrid:SfDataGrid>
{% endhighlight %} 
{% highlight c# %}
this.dataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID.Order" });
{% endhighlight %}
{% endtabs %}

## View

DataGrid has the [View](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~View.html) property of type [ICollectionViewAdv](https://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.CollectionViewAdv.html) interface that implements `ICollectionView` interface. `View` is responsible for maintaining and manipulating data and other advanced operations like [Sorting](https://help.syncfusion.com/xamarin/sfdatagrid/getting-started#sorting), [Grouping](https://help.syncfusion.com/xamarin/sfdatagrid/getting-started#grouping), and etc.

When you bind collection to [ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ItemsSource.html) property of SfDataGrid, then `View` will be created and maintains the operations on `Data` such as `Grouping`, `Sorting`, `Insert`, `Delete`, and `Modification`.

N> DataGrid creates different types of views derived from `ICollectionViewAdv` interface based on `ItemsSource`.

I> `View` related properties can be used only after creating `SfDataGrid` view. Hence changes related to view can be done in `SfDataGrid.GridViewCreated` or `SfDataGrid.GridLoaded` event or in runtime only. 

The following property is associated with `View`

### LiveDataUpdateMode

SfDataGrid provides support to update the view during data manipulation operations and property changes using [LiveDataUpdateMode](https://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.CollectionViewAdv~LiveDataUpdateMode.html). It allows you to customize when to update the view based on the `SfDataGrid.LiveDataUpdateMode` property.

<table>
<tr>
<th>LiveDataUpdateMode</th>
<th>Description</th>
</tr>
<tr>
<td>Default</td>
<td>Data operations are not updated </td>
</tr>
<tr>
<td>AllowSummaryUpdate</td>
<td>Summaries are updated during data manipulation change</td>
</tr>
<tr>
<td>AllowDataShaping</td>
<td>Data operations like sorting, grouping and filtering are updated during data manipulation change</td>
</tr>
</table>
{% tabs %}

{% highlight xaml %}
    <syncfusion:SfDataGrid x:Name="dataGrid" AllowResizingColumn="True" AllowGroupExpandCollapse="True"
                       AutoGenerateColumns="False" LiveDataUpdateMode="Default"
                       ColumnSizer="Star">
    </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
dataGrid.GridViewCreated += DataGrid_GridViewCreated;
private void DataGrid_GridViewCreated(object sender, GridViewCreatedEventArgs e)
{
    dataGrid.LiveDataUpdateMode = LiveDataUpdateMode.Default;
}
{% endhighlight %}

{% endtabs %}
The following events are associated with `View`.

### RecordPropertyChanged

[RecordPropertyChanged](https://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.ICollectionViewAdv~RecordPropertyChanged_EV.html) event is raised when the `DataModel` property value is changed, if the `DataModel` implements the [INotifyPropertyChanged](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifypropertychanged(v=vs.110).aspx) interface. The event receives with two arguments namely sender that handles the `DataModel` and [PropertyChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.PropertyChangedEventArgs)&rd=true) as argument.

`PropertyChangedEventArgs` has below property,

[PropertyName](https://msdn.microsoft.com/en-us/library/system.componentmodel.propertychangedeventargs.propertyname)  -  It denotes the `PropertyName` of the changed value.

### CollectionChanged

[CollectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.CollectionViewAdv~CollectionChanged_EV.html) event is raised whenever that is some change in `Records / DisplayElements` collection. The event receives two arguments namely sender that handles `View` object and [NotifyCollectionChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs)&rd=true) as argument.

`NotifyCollectionChangedEventArgs` has below properties,

[Action](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.Action)&rd=true) - It contains the current action. (i.e.)` Add`, `Remove`, `Move`, `Replace`, `Reset`.

[NewItems](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewItems)&rd=true) - It contains the list of new items involved in the change.

[OldItems](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldItems)&rd=true) - It contains the list of old items affected by the `Action`.

[NewStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewStartingIndex)&rd=true) - It contains the index at which the change occurred.

[OldStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex)&rd=true) - It contains the index at which the `Action` occurred.

### SourceCollectionChanged

[SourceCollectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.ICollectionViewAdv~SourceCollectionChanged_EV.html) event is raised when you make changes in `SourceCollection` for example add or remove the collection. The event receives two arguments namely sender that handles `GridQueryableCollectionViewWrapper` object and [NotifyCollectionChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs)&rd=true) as argument.

`NotifyCollectionChangedEventArgs` has below properties,

[Action](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.Action)&rd=true) - It contains the current action. (i.e.) `Add`, `Remove`, `Move`, `Replace`, `Reset`.

[NewItems](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewItems)&rd=true) - It contains the list of new items involved in the change.

[OldItems](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldItems)&rd=true) - It contains the list of old items affected by the `Action`.

[NewStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewStartingIndex)&rd=true) - It contains the index at which the change occurred.

[OldStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex)&rd=true) - It contains the index at which the `Action` occurred.

The following are the methods that are associated with `View` which can be used to defer refresh the view.

<table>
<tr>
<th>
Method Name
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
DeferRefresh
</td>
<td>
Enter the defer cycle so that you can perform all data operations in view and update once.
</td>
</tr>
<tr>
<td>
BeginInit & EndInit
</td>
<td>
When BeginInit method is called it suspends all the updates until EndInit method is called. You can suspend and resume all the operations in these methods and update the view at once.
</td>
</tr>
</table>

### Data Virtualization
SfDataGrid allows you to load large amount of data in less time by setting SfDataGrid.EnableDataVirtualization property to true.

To set the EnableDataVirtualization property, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding EmployeeDetails}"
                       EnableDataVirtualization="True">
{% endhighlight %} 
{% highlight c# %}
datagrid.EnableDataVirtualization = true;
{% endhighlight %}
{% endtabs %}

### Notify property change

The data grid control provides an option to notify property changes and refresh the view programmatically in runtime.

{% highlight c# %}
    datagrid.Refresh();
{% endhighlight %}