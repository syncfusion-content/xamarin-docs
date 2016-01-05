---
layout: post
title: Sorting | SfDataGrid | Xamarin | Syncfusion
description: How to sort the data and about the properties and events that involve in sorting in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Sorting 

This section explains you about Sorting the data and about the properties and events that involve in Sorting in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).
 
[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to apply sorting on its data by setting the **SfDataGrid.AllowSorting** property to true. It allows you to sort the data against one or more columns. When sorting is applied, the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) automatically rearranges the data to match with the current sort criteria. When **SfDataGrid.AllowSorting** is true, you can sort the data simply by tapping the column header you wish to sort. Once sorting is applied, the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) shows a sort icon in the respective column header indicating the direction of sorting.


## Programmatic Sorting

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) also allows to perform sorting from the code. This requires you to manually define the SortColumnDescription objects and add it in the **SfDataGrid.SortColumnDescriptions** collection. [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) sorts the data based on the SortColumnDescription objects that are added to this collection.

SortColumnDescription object holds following two properties:

* ColumnName: Name of the sorted column.
* SortDirection: An object of type ListSortDirection defines the sorting direction.

The following code example illustrates this.

{% tabs %}
{% highlight c# %}
dataGrid.AllowSorting = true;

dataGrid.SortColumnDescriptions.Add (new SortColumnDescription () {
    ColumnName = "OrderID",
    SortDirection = ListSortDirection.Descending
}); 
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
            ItemsSource="{Binding OrdersInfo}">

    <syncfusion:SfDataGrid.SortColumnDescriptions>
        <syncfusion:SortColumnDescription ColumnName="OrderID" 
                                          SortDirection="Descending" />
        </syncfusion:SfDataGrid.SortColumnDescriptions>
    </syncfusion:SfDataGrid> 
{% endhighlight %}
{% endtabs %}


## Tri-State Sorting

In addition to sort the data in ascending / descending orders, [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) also allows you to unsort the data in the original order by clicking the header again after sorting to descending order by setting the **SfDataGrid.AllowTriStateSorting** property to **true**. When this property is set Sorting in each column iterates through three sort states; ascending, descending, and unsorted.

The following code example shows how to enable Tri-State sorting in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).

{% tabs %}
{% highlight c# %}
dataGrid.AllowTriStateSorting = true;
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfDataGrid AllowTriStateSorting="True" />
{% endhighlight %}
{% endtabs %}


## Multi Sorting

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to sort the data against more than one columns by setting the **SfDataGrid.AllowMultiSorting** property to **true**. The number of columns by which the data can be sorted is unlimited. To apply sorting for multiple columns, tap the desired column headers after setting the **SfDataGrid.AllowMultiSorting** property.

The following code example shows how to enable multi-sorting in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).

{% tabs %}
{% highlight c# %}
dataGrid.AllowMultiSorting = true;
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfDataGrid AllowMultiSorting="True" />
{% endhighlight %}
{% endtabs %}


## Sorting Events

The [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) provides you the following Events for the sorting functionality:

* SortColumnsChanging – This Event is raised while sorting the column at execution time before the column gets sorted. It helps to cancel the sorting action by setting the Cancel property of DataGridSortColumnsChangingEventArgs.
* SortColumnsChanged – This Event is raised after the column is sorted.

These two events are triggered with DataGridSortColumnsChangingEventArgs and DataGridSortColumnsChangedEventArgs that contain the following properties.

* AddedItems – Gets the collection of SortColumnDescription objects that are added to **SfDataGrid.SortColumnDescriptions** collection for Sorting.
* RemovedItems – Gets the collection of SortColumnDescription objects that are removed from **SfDataGrid.SortColumnDescriptions** collection.

The following code example illustrates how to hook the SortColumnsChanging event and cancel the sorting of a column.

{% tabs %}
{% highlight c# %}
dataGrid.SortColumnsChanging += DataGrid_SortColumnsChanging; 
{% endhighlight %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
            AllowSorting="True"
            SortColumnsChanging="DataGrid_SortColumnsChanging"
            ItemsSource="{Binding OrdersInfo}">
</syncfusion:SfDataGrid> 
{% endhighlight %}
{% endtabs %}

{% highlight c# %}
void DataGrid_SortColumnsChanging (object sender, DataGridSortColumnsChangingEventArgs e)
{
    if(e.AddedItems[0].ColumnName == "OrderID")
    {
        e.Cancel = true;
    }
}
{% endhighlight %}


## Custom sorting

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to sort columns based on custom logic when the standard sorting techniques do not meet the requirements. For each column, you can apply different sorting criteria by adding SortComparer objects to **SfDataGrid.SortComparersCollection**.

A SortComparer object has the following properties:

* PropertyName: MappingName of the column that applies custom sorting.
* Comparer: Gets or sets the custom comparer that implements the **IComparer** and **ISortDirection** interfaces.

The following code example illustrates how to perform custom sorting for FirstName column based on the string length of the names.

{% tabs %}
{% highlight c# %}
dataGrid.SortComparers.Add (new SortComparer () {
    PropertyName = "FirstName",
    Comparer = new CustomComparer()
});

dataGrid.SortColumnDescriptions.Add (new SortColumnDescription () {
    ColumnName = "FirstName",
    SortDirection = ListSortDirection.Descending
}); 
{% endhighlight %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:data="clr-namespace:Syncfusion.Data;assembly=Syncfusion.Data.Portable"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:local ="clr-namespace:DataGridSample;assembly=DataGridSample"
             x:Class="DataGridSample.Sample">

    <ContentPage.Resources>
        <ResourceDictionary>
            <local:CustomerInfo x:Key="Comparer" />
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel" />
    </ContentPage.BindingContext>

    <syncfusion:SfDataGrid x:Name="dataGrid"
                           AllowSorting="True"
                           ItemsSource="{Binding OrdersInfo}">

        <syncfusion:SfDataGrid.SortComparers>
            <data:SortComparer Comparer="{StaticResource Comparer}"
                               PropertyName="FirstName" />
        </syncfusion:SfDataGrid.SortComparers>

        <syncfusion:SfDataGrid.SortColumnDescriptions>
            <syncfusion:SortColumnDescription ColumnName="FirstName" 
                                              SortDirection="Descending" />
        </syncfusion:SfDataGrid.SortColumnDescriptions>
    </syncfusion:SfDataGrid>
</ContentPage> 
{% endhighlight %}
{% endtabs %}

The following code example illustrates how to write a Custom Comparer.

{% highlight c# %}
public class CustomerInfo : IComparer<Object>, ISortDirection
{
    public int Compare(object x, object y)
    {
        int namX;
        int namY;

        //For OrderInfo type data
        if (x.GetType () == typeof(OrderInfo)) {
            //Calculating the length of FirstName in OrderInfo objects
            namX = ((OrderInfo)x).FirstName.Length;
            namY = ((OrderInfo)y).FirstName.Length;
        }

        //For Group type data                                   
        else if (x.GetType () == typeof(Group)) {
            //Calculating the group key length
            namX = ((Group)x).Key.ToString ().Length;
            namY = ((Group)y).Key.ToString ().Length;
        } else {
            namX = x.ToString ().Length;
            namY = y.ToString ().Length;
        }

        // Objects are compared and return the SortDirection
        if (namX.CompareTo (namY) > 0)
            return SortDirection == ListSortDirection.Ascending ? 1 : -1;
        else if (namX.CompareTo (namY) == -1)
            return SortDirection == ListSortDirection.Ascending ? -1 : 1;
        else
            return 0; 
    }

    //Gets or sets the SortDirection value
    public ListSortDirection SortDirection { get; set; }
}
{% endhighlight %}


## Disable sorting for an individual column

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to disable the sorting for individual columns by using the **GridColumn.AllowSorting** property. The default value of this property is true and hence all the columns in the **SfDataGrid.Columns** collection can be sorted when **SfDataGrid.AllowSorting** is set to true.
