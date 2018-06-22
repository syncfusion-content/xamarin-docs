---
layout: post
title: Data Binding | SfDataGrid | Xamarin | Syncfusion
description: Data Binding and different sources that can be bound to a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Data Binding

The SfDataGrid is bound to an external data source to display the data. It supports data sources such as [List](https://msdn.microsoft.com/en-us/library/6sh2ey19(v=vs.110).aspx), [ObservableCollection](https://msdn.microsoft.com/en-us/library/ms668604(v=vs.110).aspx), and so on. The [SfDataGrid.ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ItemsSource.html) property helps to bind this control with collection of objects.

In order to bind data source of the SfDataGrid, set the `SfDataGrid.ItemsSource` property as follows. Such that each row in the SfDataGrid would bind to an object in data source. Each column would bind to a property in the data model object.

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

If the data source implements `ICollectionChanged` interface, then the SfDataGrid will automatically refresh the view when an item is added, removed, or cleared. When you add or remove an item in `ObservableCollection`, it automatically refreshes the view as the `ObservableCollection`. That implements the [INotifyCollectionChanged](https://msdn.microsoft.com/en-us/library/system.collections.specialized.inotifycollectionchanged(v=vs.110).aspx). But when you do the same in `List`, it will not refresh the view automatically.

If the data model implements the [INotifyPropertyChanged](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifypropertychanged(v=vs.110).aspx) interface, then the SfDataGrid responds to the property change at runtime to update the view.

N> The SfDataGrid does not supports `DataTable` binding in `Xamarin.Forms` since `System.Data` is inaccessible in `Portable Class Library`.

## Binding with IEnumerable

The SfDataGrid control supports to bind any collection that implements the [IEnumerable](https://msdn.microsoft.com/en-us/library/system.collections.ienumerable) interface. All the data operations such as sorting, grouping, and filtering are supported when binding collection derived from `IEnumerable`.

## Binding complex properties

The SfDataGrid control supports to bind complex property to its columns. To bind complex property to the [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html), set the complex property path to the [MappingName](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~MappingName.html).

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

The DataGrid has the [View](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~View.html) property of type [ICollectionViewAdv](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Data.Portable~Syncfusion.Data.CollectionViewAdv.html) interface that implements `ICollectionView` interface. `View` is responsible for maintaining and manipulating data and other advanced operations, like [Sorting](https://help.syncfusion.com/xamarin/sfdatagrid/getting-started#sorting), [Grouping](https://help.syncfusion.com/xamarin/sfdatagrid/getting-started#grouping), and etc.,

When you bind collection to the [ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ItemsSource.html) property of the SfDataGrid, then `View` will be created and maintains the operations on `Data` such as `Grouping`, `Sorting`, `Insert`, `Delete`, and `Modification`.

N> The DataGrid creates different types of view derived from `ICollectionViewAdv` interface based on the `ItemsSource`.

I> `View` related properties can be used only after creating `SfDataGrid` view. Hence changes related to view can be done in `SfDataGrid.GridViewCreated` or `SfDataGrid.GridLoaded` event or in runtime only. 

The following property is associated with `View`

### LiveDataUpdateMode

The SfDataGrid supports to update the view during data manipulation operations and property changes using the [LiveDataUpdateMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Data.Portable~Syncfusion.Data.CollectionViewAdv~LiveDataUpdateMode.html). It allows to update the view based on the `SfDataGrid.View.LiveDataUpdateMode` property.

<table>
<tr>
<th>LiveDataUpdateMode</th>
<th>Description</th>
</tr>
<tr>
<td>Default</td>
<td>Data operations are not updated. </td>
</tr>
<tr>
<td>AllowSummaryUpdate</td>
<td>Summaries are updated during data manipulation change.</td>
</tr>
<tr>
<td>AllowDataShaping</td>
<td>Data operations like sorting, grouping, and filtering are updated during data manipulation change.</td>
</tr>
</table>

{% highlight c# %}
dataGrid.GridViewCreated += DataGrid_GridViewCreated;
private void DataGrid_GridViewCreated(object sender, GridViewCreatedEventArgs e)
{
    dataGrid.View.LiveDataUpdateMode = LiveDataUpdateMode.Default;
}
{% endhighlight %}

The following events are associated with `View`.

### RecordPropertyChanged

The [RecordPropertyChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Data.Portable~Syncfusion.Data.ICollectionViewAdv~RecordPropertyChanged_EV.html) event is raised when `DataModel` property value is changed, if `DataModel` implements the [INotifyPropertyChanged](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifypropertychanged(v=vs.110).aspx) interface. The event receives with two arguments namely sender that handles the `DataModel` and the [PropertyChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.PropertyChangedEventArgs)&rd=true) as argument.

`PropertyChangedEventArgs` has the following property:

 [PropertyName](https://msdn.microsoft.com/en-us/library/system.componentmodel.propertychangedeventargs.propertyname): It denotes the `PropertyName` of the changed value.

### CollectionChanged

The [CollectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Data.Portable~Syncfusion.Data.CollectionViewAdv~CollectionChanged_EV.html) event is raised when changes in `Records/DisplayElements` collection. The event receives two arguments namely sender that handles `View` object and the [NotifyCollectionChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs)&rd=true) as argument.

`NotifyCollectionChangedEventArgs` has the following properties:

 [Action](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.Action)&rd=true): It contains the current action. (i.e.)` Add`, `Remove`, `Move`, `Replace`, `Reset`.
 [NewItems](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewItems)&rd=true): It contains the list of new items involved in the change.
 [OldItems](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldItems)&rd=true): It contains the list of old items affected by the `Action`.
 [NewStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewStartingIndex)&rd=true): It contains the index at which the change occurred.
 [OldStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex)&rd=true): It contains the index at which the `Action` occurred.

### SourceCollectionChanged

The [SourceCollectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Data.Portable~Syncfusion.Data.ICollectionViewAdv~SourceCollectionChanged_EV.html) event is raised when making changes in `SourceCollection`. For example, adding or removing the collection. The event receives two arguments namely sender that handles `GridQueryableCollectionViewWrapper` object and the [NotifyCollectionChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs)&rd=true) as argument.

`NotifyCollectionChangedEventArgs` has the following properties:

 [Action](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.Action)&rd=true): It contains the current action. (i.e.) `Add`, `Remove`, `Move`, `Replace`, `Reset`.
 [NewItems](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewItems)&rd=true): It contains the list of new items involved in the change.
 [OldItems](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldItems)&rd=true): It contains the list of old items affected by the `Action`.
 [NewStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewStartingIndex)&rd=true): It contains the index at which the change occurred.
 [OldStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex)&rd=true): It contains the index at which the `Action` occurred.

The following methods are associated with `View` which can be used to defer refresh the view:

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