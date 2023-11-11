---
layout: post
title: Data Binding in Xamarin DataGrid control | Syncfusion
description: Learn here all about Data Binding support in Syncfusion Xamarin DataGrid (SfDataGrid) control and more.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Data Binding in Xamarin DataGrid (SfDataGrid)

The [Xamarin Datagrid](https://www.syncfusion.com/xamarin-ui-controls/xamarin-datagrid) Control is bound to an external data source to display the data. It supports data sources such as [List](https://learn.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.observablecollection-1?view=net-5.0), and so on. The [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ItemsSource) property helps to bind this control with collection of objects.

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

If the data source implements `ICollectionChanged` interface, then the SfDataGrid will automatically refresh the view when an item is added, removed, or cleared. When you add or remove an item in `ObservableCollection`, it automatically refreshes the view as the `ObservableCollection`. That implements the [INotifyCollectionChanged](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.inotifycollectionchanged?view=net-5.0). But when you do the same in `List`, it will not refresh the view automatically.

If the data model implements the [INotifyPropertyChanged](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged?view=net-5.0) interface, then the SfDataGrid responds to the property change at runtime to update the view.

N> The SfDataGrid does not supports `DataTable` binding in `Xamarin.Forms` since `System.Data` is inaccessible in `Portable Class Library`.

## Binding with IEnumerable

The SfDataGrid control supports to bind any collection that implements the [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-5.0) interface. All the data operations such as sorting, grouping, and filtering are supported when binding collection derived from `IEnumerable`.

## Binding with DataTable
`SfDataGrid` control supports to bind the [DataTable](https://learn.microsoft.com/en-us/dotnet/api/system.data.datatable?view=netframework-4.8). SfDataGrid control automatically refresh the UI when binding DataTable as `ItemsSource` when rows are added, removed or cleared.

{% tabs %}
{% highlight xaml %}
<sfGrid:SfDataGrid x:Name="dataGrid"
                   AutoGenerateColumns="False"
                   ItemsSource="{Binding Table}">
</sfGrid:SfDataGrid>
{% endhighlight %} 
{% highlight c# %}
DataTable Table = this.GetDataTable();
this.sfDataGrid1.ItemsSource = Table;
{% endhighlight %}
{% endtabs %}

Below are the limitations when binding DataTable as `ItemsSource` to SfDataGrid.

* Custom sorting is not supported.
* [SfDataGrid.View.Filter](https://help.syncfusion.com/cr/xamarin/Syncfusion.Data.CollectionViewAdv.html#Syncfusion_Data_CollectionViewAdv_Filter) is not supported.
* Advanced Filtering does not support Case Sensitive filtering.
* [GridUnboundColumn.Expression](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridUnboundColumn.html#Syncfusion_SfDataGrid_XForms_GridUnboundColumn_Expression) is not supported. This can be achieved by using the [DataColumn](https://learn.microsoft.com/en-us/dotnet/api/system.data.datacolumn?redirectedfrom=MSDN&view=net-5.0) of DataTable by setting [DataColumn.Expression](https://learn.microsoft.com/en-us/dotnet/api/system.data.datacolumn.expression?redirectedfrom=MSDN&view=net-5.0#System_Data_DataColumn_Expression) property.
* [SfDataGrid.LiveDataUpdateMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.Data.CollectionViewAdv.html#Syncfusion_Data_CollectionViewAdv_LiveDataUpdateMode) is not supported.
* Filtering with [TimeSpan](https://learn.microsoft.com/en-us/dotnet/api/system.timespan?redirectedfrom=MSDN&view=net-5.0) values is not supported.
* Filtering with sub second components in `DateTime` values is not supported.

## Binding complex properties

The SfDataGrid control supports to bind complex property to its columns. To bind complex property to the [GridColumn](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html), set the complex property path to the [MappingName](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_MappingName).

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

The DataGrid has the [View](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_View) property of type [ICollectionViewAdv](https://help.syncfusion.com/cr/xamarin/Syncfusion.Data.CollectionViewAdv.html) interface that implements `ICollectionView` interface. `View` is responsible for maintaining and manipulating data and other advanced operations, like [Sorting](https://help.syncfusion.com/xamarin/datagrid/getting-started#sorting), [Grouping](https://help.syncfusion.com/xamarin/datagrid/getting-started#grouping), and etc.,

When you bind collection to the [ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ItemsSource) property of the SfDataGrid, then `View` will be created and maintains the operations on `Data` such as `Grouping`, `Sorting`, `Insert`, `Delete`, and `Modification`.

N> The DataGrid creates different types of view derived from `ICollectionViewAdv` interface based on the `ItemsSource`.

I> `View` related properties can be used only after creating `SfDataGrid` view. Hence changes related to view can be done in `SfDataGrid.GridViewCreated` or `SfDataGrid.GridLoaded` event or in runtime only. 

The following property is associated with `View`

### LiveDataUpdateMode

The SfDataGrid supports to update the view during data manipulation operations and property changes using the [LiveDataUpdateMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.Data.CollectionViewAdv.html#Syncfusion_Data_CollectionViewAdv_LiveDataUpdateMode). It allows to update the view based on the `SfDataGrid.View.LiveDataUpdateMode` property.

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

The [RecordPropertyChanged](https://help.syncfusion.com/cr/xamarin/) event is raised when `DataModel` property value is changed, if `DataModel` implements the [INotifyPropertyChanged](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged?view=net-5.0) interface. The event receives with two arguments namely sender that handles the `DataModel` and the [PropertyChangedEventArgs](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.propertychangedeventargs?view=net-5.0) as argument.

`PropertyChangedEventArgs` has the following property:

 [PropertyName](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.propertychangedeventargs.propertyname?view=net-5.0): It denotes the `PropertyName` of the changed value.

### CollectionChanged

The [CollectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.Data.CollectionViewAdv.html) event is raised when changes in `Records/DisplayElements` collection. The event receives two arguments namely sender that handles `View` object and the [NotifyCollectionChangedEventArgs](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs?view=net-5.0) as argument.

`NotifyCollectionChangedEventArgs` has the following properties:

 [Action](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.action?view=net-5.0): It contains the current action. (i.e.)` Add`, `Remove`, `Move`, `Replace`, `Reset`.
 [NewItems](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.newitems?view=net-5.0): It contains the list of new items involved in the change.
 [OldItems](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.olditems?view=net-5.0): It contains the list of old items affected by the `Action`.
 [NewStartingIndex](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.newstartingindex?view=net-5.0): It contains the index at which the change occurred.
 [OldStartingIndex](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.oldstartingindex?view=net-5.0): It contains the index at which the `Action` occurred.

### SourceCollectionChanged

The [SourceCollectionChanged](https://help.syncfusion.com/cr/xamarin/) event is raised when making changes in `SourceCollection`. For example, adding or removing the collection. The event receives two arguments namely sender that handles `GridQueryableCollectionViewWrapper` object and the [NotifyCollectionChangedEventArgs](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs?view=net-5.0) as argument.

`NotifyCollectionChangedEventArgs` has the following properties:

 [Action](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.action?view=net-5.0): It contains the current action. (i.e.) `Add`, `Remove`, `Move`, `Replace`, `Reset`.
 [NewItems](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.newitems?view=net-5.0): It contains the list of new items involved in the change.
 [OldItems](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.olditems?view=net-5.0): It contains the list of old items affected by the `Action`.
 [NewStartingIndex](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.newstartingindex?view=net-5.0): It contains the index at which the change occurred.
 [OldStartingIndex](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs.oldstartingindex?view=net-5.0): It contains the index at which the `Action` occurred.

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
Data grid provides support to handle the large amount of data through built-in virtualization feature. With Data virtualization, the record entries will be created in the runtime only upon scrolling to the vertical end which increases the  performance of grid loading time.

To set SfDataGrid.EnableDataVirtualization property to true, follow the code example:

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

### NotificationSubscriptionMode

Data grid exposed [SfDataGrid.NotificationSubscriptionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.Data.NotificationSubscriptionMode.html) property that allows you to set whether the underlying source collection items can listen to the INotifyCollectionChanged or INotifyPropertyChanging events. You can handle the property change or collection change by setting the NotificationSubscriptionMode property.

<table>
<tr>
<th>NotificationSubscriptionMode</th>
<th>Description</th>
</tr>
<tr>
<td>CollectionChange</td>
<td>Denotes a view that listens System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged event of the SourceCollection. </td>
</tr>
<tr>
<td>None</td>
<td>Denotes System.ComponentModel.INotifyPropertyChanging.PropertyChanging, System.ComponentModel.INotifyPropertyChanged.PropertyChanged, and System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged events will not be listened.</td>
</tr>
<tr>
<td>PropertyChange</td>
<td>Denotes a view that listens the System.ComponentModel.INotifyPropertyChanging.PropertyChanging and System.ComponentModel.INotifyPropertyChanged.PropertyChanged events of the data object.</td>
</tr>
</table>

To set the NotificationSubscriptionMode property, follow the code example.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding EmployeeDetails}"
                       NotificationSubscriptionMode="CollectionChange">
{% endhighlight %} 
{% highlight c# %}
dataGrid.NotificationSubscriptionMode = NotificationSubscriptionMode.CollectionChange;
{% endhighlight %}
{% endtabs %}

### Binding SfDataGrid.SelectedIndex property
You can bind any int value to the bindable property [SfDataGrid.SelectedIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedIndex) which gets or sets the lastly selected row's index in the SfDataGrid.

Refer the below code to bind the `SfDataGrid.SelectedIndex` from the ViewModel.

{% highlight xaml%}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}"
                    SelectionMode="Multiple"
                    SelectedIndex="{Binding SelectedIndex}">
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private int _selectedIndex;

        public int SelectedIndex
        {
            get { return _selectedIndex; }
            set { this._selectedIndex = value;RaisePropertyChanged("SelectedIndex"); }
        }

         public ViewModel()
        {
           this.SelectedIndex = 5;
        }

{% endhighlight %}

### Binding SfDataGrid.SelectedItem property

You can bind any object value to the bindable property [SfDataGrid.SelectedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedItem) which gets or sets the selected item in the SfDataGrid.

Refer the below code to bind the `SfDataGrid.SelectedItem` from the ViewModel.

{% highlight xaml%}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}"
                    SelectionMode="Multiple"
                    SelectedItem="{Binding SelectedItem}">
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private object _selectedItem;

         public object SelectedItem
        {
            get { return _selectedItem; }
            set { this._selectedItem = value; RaisePropertyChanged("SelectedItem"); }
        }

         public ViewModel()
        {
            this.SelectedItem = this.OrderInfoCollection[8];
        }

{% endhighlight %}

### Binding SfDataGrid.SelectedItems property
You can bind any object type collection to the bindable property SfDataGrid[SfDataGrid.SelectedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedItems) which gets or sets the collection of `SelectedItems` collection in the SfDataGrid.

Refer the below code to bind the `SfDataGrid.SelectedItems` from the ViewModel.

{% highlight xaml%}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}"
                    SelectionMode="Multiple"
                    SelectedItems="{Binding SelectedItems}">
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private ObservableCollection<object> _selectedItems;

        public ObservableCollection<object> SelectedItems
        {
            get { return _selectedItems; }
            set { this._selectedItems = value; RaisePropertyChanged("SelectedItems"); }
        }

         public ViewModel()
        {
          this.SelectedItems.Add(OrderInfoCollection[1]);
          this.SelectedItems.Add(OrderInfoCollection[5]);
          this.SelectedItems.Add(OrderInfoCollection[8]);
        }

{% endhighlight %}

### Binding GridColumn properties

You can also assign value via binding to the properties of the [GridColumn](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html) such as [HeaderCellTextSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_HeaderCellTextSize),[CellTextSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_CellTextSize),[FontAttribute](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_FontAttribute),[RecordFont](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_RecordFont),[HeaderFont](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_HeaderFont) etc. 

Refer the below code to bind the GridColumn properties from the ViewModel.

{% highlight xaml%}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}">
    <sfgrid:SfDataGrid.Columns>
        <sfgrid:GridTextColumn MappingName="Customer" CellTextSize="{Binding CellTextSize,Source={x:Reference viewModel}}"/>
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private double _cellTextSize;

        public double CellTextSize
        {
            get { return _cellTextSize; }
            set { this._cellTextSize = value; RaisePropertyChanged("CellTextSize"); }
        }

         public ViewModel()
        {
          this.CellTextSize = 20;
        }

{% endhighlight %}


### Binding GridPickerColumn ItemsSource from ViewModel

You can assign any object typed collection to the [GridPickerColumn.ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridPickerColumn.html#Syncfusion_SfDataGrid_XForms_GridPickerColumn_ItemsSource) to display a list of items in the `GridPickerColumn` when entering edit mode. 

Refer the below code to bind the ItemsSource of GridPickerColumn from the ViewModel.

{% highlight xaml%}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}">
    <sfgrid:SfDataGrid.Columns>
         <sfgrid:GridPickerColumn BindingContext="{x:Reference viewModel}"
                                  MappingName="ShipCity" 
                                  ItemsSource="{Binding CustomerNames}" HeaderText="PickerColumn"/>
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private ObservableCollection<string> _customerNames;

       public ObservableCollection<string> CustomerNames
        {
            get { return _customerNames; }
            set { this._customerNames = value; RaisePropertyChanged("CustomerNames"); }
        }

         public ViewModel()
        {
           this.CustomerNames = customerNames.ToObservableCollection();
        }

        string[] customerNames = { "Thomas", "John", "Hanna", "Laura", "Gina" };

{% endhighlight %}

### Binding the ItemsSource in ViewModel to the Picker loaded inside template

The `ItemsSource` of a picker which is loaded inside the [GridTemplateColumn](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridTemplateColumn.html) can also be assigned any value via binding by passing the binding context as the `Source` to the `ItemsSource` property.

Refer the below code to bind the ItemsSource of Picker loaded inside the GridTemplateColumn from the ViewModel.

{% highlight xaml%}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}">
    <sfgrid:SfDataGrid.Columns>
         <sfgrid:GridTemplateColumn   MappingName="Customer" HeaderText="Picker">
        <sfgrid:GridTemplateColumn.CellTemplate>
          <DataTemplate>
              <Picker ItemsSource="{Binding SelectedModels,Source={x:Reference viewModel}}" SelectedIndex="0"/>
          </DataTemplate>
        </sfgrid:GridTemplateColumn.CellTemplate>
    </sfgrid:GridTemplateColumn>
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private List<String> _vehicleModel;

        public List<String> SelectedModels
        {
            get { return _vehicleModel; }
            set { this._vehicleModel = value;RaisePropertyChanged("SelectedCars"); }
        }

         public ViewModel()
        {
           this.SelectedModels = selectedModels.ToList();
        }

        string [] selectedModels = { "Select Car", "Audi", "Bentley", "Mercedes Benz", "Porsche" };

{% endhighlight %}

### Binding the button command in template column to ViewModel

You can also assign any value to the Command property of the Button loaded inside the GridTemplateColumn via binding.

Refer the below code to bind the command property of Button loaded inside the GridTemplateColumn from the ViewModel.

{% highlight xaml%}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}">
    <sfgrid:SfDataGrid.Columns>    
        <sfgrid:GridTemplateColumn MappingName="Customer">
             <sfgrid:GridTemplateColumn.CellTemplate>

                 <DataTemplate>
                     <Button Text="Template" Command="{Binding ButtonCommand,Source={x:Reference viewModel}}"/>
                 </DataTemplate>
            </sfgrid:GridTemplateColumn.CellTemplate>
        </sfgrid:GridTemplateColumn>
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private Command _buttonCommand;

        public Command ButtonCommand
        {
            get { return _buttonCommand; }
            set { this._buttonCommand = value;RaisePropertyChanged("ButtonCommand"); }
        }

         public ViewModel()
        {
          this.ButtonCommand = new Command(CustomMethod);
        }

        public void CustomMethod()
        {
            // Customize your code here
        }

{% endhighlight %}

You can download the source code of binding the SfDataGrid properties sample [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/SfGrid_Sample788022149)

N> You can refer to our [Xamarin DataGrid](https://www.syncfusion.com/xamarin-ui-controls/xamarin-datagrid) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms DataGrid example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/DataGrid) to knows various chart types and how to easily configured with built-in support for creating stunning visual effects.

## See also

[How to bind a column collection from view model in SfDataGrid Xamarin.Forms](https://support.syncfusion.com/kb/article/8477/how-to-bind-a-column-collection-from-view-model-in-sfdatagrid-xamarin-forms)

[How to resolve "Cannot resolve reference `Xamarin.Android.Support.Interpolate'" in Xamarin.Forms Android projects](https://support.syncfusion.com/kb/article/9422/how-to-resolve-cannot-resolve-reference-xamarin-android-support-interpolator-in-xamarin)

[How to resolve SfDataGrid not rendering issue in iOS and UWP](https://support.syncfusion.com/kb/article/7358/how-to-resolve-sfdatagrid-not-rendering-issue-in-ios-and-uwp)

[How to configure and install SfDataGrid NuGet package in Visual Studio](https://support.syncfusion.com/kb/article/7356/how-to-configure-and-install-sfdatagrid-nuget-package-in-visual-studio)

[How to make Syncfusion.Xamarin.SfDataGrid to work in release mode in UWP when .NET Native tool chain is enabled](https://support.syncfusion.com/kb/article/7355/how-to-make-syncfusion-xamarin-sfdatagrid-to-work-in-release-mode-in-uwp-when-net-native)

[How to apply the custom assemblies when configured the project with Syncfusion NuGet packages](https://support.syncfusion.com/kb/article/7355/how-to-make-syncfusion-xamarin-sfdatagrid-to-work-in-release-mode-in-uwp-when-net-native)

[How to bind button command to ViewModel from TemplateColumn of DataGrid](https://support.syncfusion.com/kb/article/7976/how-to-bind-button-command-to-viewmodel-from-templatecolumn-of-datagrid)

[How to update the modified GridCell value for Dictionary](https://support.syncfusion.com/kb/article/7280/how-to-update-the-modified-gridcell-value-for-dictionary)

[How to use SfDataGrid in Prism](https://support.syncfusion.com/kb/article/7198/how-to-use-sfdatagrid-in-prism)

[How to commit the edited values when binding Dictionary in SfDataGrid](https://support.syncfusion.com/kb/article/7181/how-to-commit-the-edited-values-when-binding-dictionary-in-sfdatagrid)

[How to load SfDataGrid dynamically with JSON data without POCO classes](https://support.syncfusion.com/kb/article/7037/how-to-load-sfdatagrid-dynamically-with-json-data-without-poco-classes)

[How to retain the SfDataGrid properties when changing the data source](https://support.syncfusion.com/kb/article/7246/how-to-retain-the-sfdatagrid-properties-when-changing-the-data-source)

[How to bind a view model property to header template](https://support.syncfusion.com/kb/article/7054/how-to-bind-a-view-model-property-to-header-template)

[How to overcome the DisplayBinding converter is not firing problem when XamlCompilation attribute is set as XamlCompilationOptions.Compile](https://support.syncfusion.com/kb/article/6906/how-to-overcome-the-displaybinding-converter-is-not-firing-problem-when-xamlcompilation)

[How to parse XML file and set as ItemsSource for SfDataGrid](https://support.syncfusion.com/kb/article/6563/how-to-parse-xml-file-and-set-as-itemssource-for-sfdatagrid)

[How to configure package source and install Syncfusion NuGet packages in an existing project](https://support.syncfusion.com/kb/article/6565/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing)

[How to render SfDataGrid for Xamarin.Forms.UWP in release mode](https://support.syncfusion.com/kb/article/6569/how-to-render-sfdatagrid-for-xamarin-forms-uwp-in-release-mode)

[How to get the X and Y coordinates when interacting with SfDataGrid](https://support.syncfusion.com/kb/article/6531/how-to-get-the-x-and-y-coordinates-when-interacting-with-sfdatagrid)

[How to resolve "Expecting class path separator ';' before" error in Xamarin.Forms.Android](https://support.syncfusion.com/kb/article/6698/how-to-resolve-expecting-class-path-separator-before-error-in-xamarin-forms-android)

[How to display an animation while loading the data in the SfDataGrid](https://support.syncfusion.com/kb/article/6524/how-to-display-an-animation-while-loading-the-data-in-the-sfdatagrid)