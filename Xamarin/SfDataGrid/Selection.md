---
layout: post
title: Selection | SfDataGrid | Xamarin | Syncfusion
description: Selection
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Selection

This section explains you about how to enable selection in **SfDataGrid** and about the selection modes, properties, events that involve in selection and customizations available for Selection in **SfDataGrid**.

**SfDataGrid** lets you to select a specific row or group of rows either programmatically or by touch interactions. To enable Selection in **SfDataGrid**, you need to set the **SfDataGrid.SelectionMode** property to value other than “None”. **SfDataGrid** has different selection modes to perform selection operation as listed below.

* None: Disables selection and no rows can be selected. This is the default value.
* Single: Allows you to select a single row only. Upon selecting the next row the selection in the previous row is cleared.
* Multiple: Allows you to select more than one row. Selection is not cleared when selecting more than one records. When you click on a selected row for the second time, selection is cleared.
* SingleDeselect: Allows you to select only a single row, however upon tapping the row again the Selection is cleared. Similar to “Single” mode, upon selecting the next row the selection in the previous row is cleared.

The following code example illustrates how to set the selection mode in **SfDataGrid**.

{% highlight c# %}
dataGrid.SelectionMode = SelectionMode.Single; 
{% endhighlight %}

## Programmatic Selection

When **SfDataGrid.SelectionMode** is set a value other than “None”, you can also select the row / rows in **SfDataGrid** from the code by setting the **SfDataGrid.SelectedIndex**, **SfDataGrid.SelectedItem** or **SfDataGrid.SelectedItems** property based on the selection mode. The following code example illustrates how to enable selection from code in **SfDataGrid**.

When the selection mode is “Single” you can programmatically select a row in two ways, either by setting the row index to the **SfDataGrid.SelectedIndex** property or by setting the underlying object to be selected to the **SfDataGrid.SelectedItem** property. 

The following code example illustrates how to programmatically select a row from the code.

{% highlight c# %}
//Perform selection using selected index
dataGrid.SelectedIndex = 3;
 
//Perform selection using selected item
dataGrid.SelectedItem = viewModel.OrdersInfo [5];
{% endhighlight %}

## Selection Events

The **SfDataGrid** provides you the following Events for Selection:

* SelectionChanging – This Event is raised while selecting a row at the execution time before the row is selected. Hence it allows you to cancel the selection action by setting the Cancel property of GridSelectionChangingEventArgs.
* SelectionChanged – This Event is raised after the column is selected.

These two events are triggered with GridSelectionChangingEventArgs and GridSelectionChangedEventArgs that contain the following properties.

* AddedItems – Gets the collection of underlying data objects that are added for selection.
* RemovedItems – Gets the collection of underlying data objects that are removed selection.

The following code example illustrates how to hook the SelectionChanging event and cancel the selection of a column.

{% highlight c# %}
dataGrid.SelectionChanging += DataGrid_SelectionChanging;  

void DataGrid_SelectionChanging (object sender, GridSelectionChangingEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}

## Clear Selection

**SfDataGrid** allows you to clear the selection applied in the grid rows in two ways, either by setting the **SfDataGrid.SelectionMode** to “None” or by calling the **SfDataGrid.SelectionController.ClearSelection()** method.

The following code example illustrates how to clear selection in **SfDataGrid**.

{% highlight c# %}
//Clear selection using selection mode
dataGrid.SelectionMode = SelectionMode.None;

//Clear selection using selection controller
dataGrid.SelectionController.ClearSelection (); 
{% endhighlight %}
