---
layout: post
title: Editing | SfDataGrid | Xamarin | Syncfusion
description: Editing the cell values with SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: ug
---

# Editing
SfDataGrid provides support for editing the cell values by setting [SfDataGrid.AllowEditing](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AllowEditing.html) property.

The following code example shows how to enable editing in SfDataGrid. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AllowEditing="True"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% highlight c# %}
dataGrid.AllowEditing = true;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/Editing_Column_Forms.png)

## Column Editing

You can enable or disable editing for particular column by setting [GridColumn.AllowEditing](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~AllowEditing.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:GridTextColumn AllowEditing="True" MappingName="OrderID" />
{% endhighlight %}
{% highlight c# %}
GridTextColumn column = new GridTextColumn();
column.AllowEditing = false;
{% endhighlight %}
{% endtabs %}

N> `GridColumn.AllowEditing` takes higher priority than `SfDataGrid.AllowEditing`.

## Entering into edit mode

You can enter into edit mode by selecting the row and touching the cell. Users can also choose to edit the cell in single tap or double tap by setting by [SfDataGrid.EditTapAction](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~EditTapAction.html) property.

{% tabs %}
{% highlight xaml %}
<sfgrid:SfDataGrid x:Name="dataGrid"
                           AllowEditing="True"
                           AutoGenerateColumns="True"
                           EditTapAction="OnTap">
{% endhighlight %}
{% highlight c# %}
//Enter edit mode in single tap
this.dataGrid.EditTapAction = TapAction.OnTap;
//Enter edit mode in double tap
this.dataGrid.EditTapAction = TapAction.OnDoubleTap;
{% endhighlight %}
{% endtabs %}

## Cursor behavior
When the cell enters into edit mode, cursor is placed based on [SfDataGrid.EditorSelectionBehavior](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~EditorSelectionBehavior.html) property.

* SelectAll – selects the text of edit element loaded inside cell.
* MoveLast – places the cursor at the last of edit element loaded inside cell.

{% tabs %}
{% highlight xaml %}
<sfgrid:SfDataGrid x:Name="dataGrid"
                           AllowEditing="True"
                           AutoGenerateColumns="True"
                           EditTapAction="OnTap"
                           EditorSelectionBehavior="SelectAll">
{% endhighlight %}
{% highlight c# %}
//Selects all the text in the edit mode
this.dataGrid.EditorSelectionBehavior = EditorSelectionBehavior.SelectAll;
//Places the cursor at the last
this.dataGrid.EditorSelectionBehavior = EditorSelectionBehavior.MoveLast;
{% endhighlight %}
{% endtabs %}

N> Editing support for GridTemplateColumn and GridUnboundColumn are not provided yet.

## Editing Events
SfDataGrid triggers the following events while editing.

### CurrentCellBeginEdit

[SfDataGrid.CurrentCellBeginEdit](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CurrentCellBeginEdit_EV.html) event occurs when the CurrentCell enters into edit mode. [GridCurrentCellBeginEditEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCurrentCellBeginEditEventArgs.html) has the following members which provides information for `SfDataGrid.CurrentCellBeginEdit` event.

* [Cancel](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) : When set to ‘true’, the event is canceled and the CurrentCell does not enter into the edit mode.
* RowColumnIndex : Gets the current row,column index of the DataGrid.
* Column : Gets the Grid Column of the SfDataGrid.

### CurrentCellEndEdit

[CurrentCellEndEdit](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CurrentCellEndEdit_EV.html) event occurs when the CurrentCell exits the edit mode. [GridCurrentCellEndEditEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCurrentCellEndEditEventArgs.html) has following members which provides information for `SfDataGrid.CurrentCellEndEdit` event.

* RowColumnIndex : Gets the current row,column index of the DataGrid.
* [Cancel](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) : When set to ‘true’, the event is canceled and the edited value is not committed in the underlying collection.


## Programmatically edit a cell

### Begin editing

SfDataGrid allows you to edit the cell programmatically by calling the [SfDataGrid.BeginEdit](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~BeginEdit.html) method. Calling this method makes that particular cell enter the edit mode after which you can customize the data manually. The below code example shows how to edit a cell programmatically.

{% highlight c# %}
this.dataGrid.Loaded += dataGrid_Loaded;
void dataGrid_Loaded(object sender, RoutedEventArgs e)
{
    //Edit the cell at 2nd row,2nd column programmatically
    this.dataGrid.BeginEdit(2, 2);
}
{% endhighlight %}

### End editing

You can call the [SfDataGrid.EndEdit](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~EndEdit.html) method to programmatically end editing. Calling this method for a cell currently undergoing editing commits the edited value to the underlying collection and exits the edit mode. The below code example shows how to end the editing programmatically.

{% highlight c# %}
this.dataGrid.EndEdit();
{% endhighlight %}

### Cancel editing

You can call the [SfDatagrid.CancelEdit](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CancelEdit.html) method to programmatically cancel the editing. Calling this method for a cell currently undergoing editing will exit the edit mode without committing the value in the underlying collection. The below code example shows how to cancel the editing programmatically.

{% highlight c# %}
this.dataGrid.CancelEdit();
{% endhighlight %}

## How to 

### Cancel Editing

You can use the `SfDataGrid.CurrentCellBeginEdit` event to cancel the editing operation for the corresponding cell. The below code example shows how to cancel the editing operation using the `SfDataGrid.CurrentCellBeginEdit` event.

{% highlight c# %}
this.dataGrid.CurrentCellBeginEdit += DataGrid_CurrentCellBeginEdit;
private void DataGrid_CurrentCellBeginEdit(object sender, GridCurrentCellBeginEditEventArgs args)
{
    if (args.Column.MappingName == "OrderID" || args.RowColumnIndex.RowIndex == 2)
        args.Cancel = true;
}
{% endhighlight %}

### Cancel edited value from getting committed

You can prevent the edited value from getting committed using the `SfDataGrid.CurrentCellEndEdit` event. The below code example shows how to prevent the edited values from getting committed in the underlying collection.

{% highlight c# %}
this.dataGrid.CurrentCellEndEdit += DataGrid_CurrentCellEndEdit;

private void DataGrid_CurrentCellEndEdit(object sender, GridCurrentCellEndEditEventArgs args)
{
    if (args.RowColumnIndex.RowIndex == 2)
        args.Cancel == true;
}
{% endhighlight %}