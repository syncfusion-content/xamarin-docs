---
layout: post
title: Selection | SfListView | Xamarin | Syncfusion
description: How to enable selection, about the selection modes, selection gestures, properties and events available for selection in a SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Selection

This section explains you about how to enable selection in SfListView and about the selection modes, selection gestures, properties, events that involve in selection for SfListView.

## UI Selection

SfListView lets you to select the items either programmatically or by touch interactions. To enable Selection in SfListView, you need to set the [SfListView.SelectionMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionMode.html) property to value other than `None`. SfListView has different selection modes to perform selection operation as listed below.

* None: Disables the selection and no item can be selected.
* Single: Allows you to select a single item only. Upon selecting the next item, the selection in the previous item is cleared and when you click on a selected item for the second time, selection is cleared. This is the default value for `SfListView.SelectionMode`.
* Multiple: Allows you to select more than one item. Selection is not cleared when selecting more than one items. When you click on a selected item for the second time, selection is cleared.

SfListView allows you to select one or more items on different user interactions such as tap, double tap and hold. This can be achieved by setting the [SfListView.SelectionGesture](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionGesture.html).

The following code example illustrates how to set the selection mode and selection gesture in SfListView.

{% highlight c# %}
listView.SelectionMode = SelectionMode.Multiple;
listView.SelectionGesture = TouchGesture.Hold;
{% endhighlight %}

## Programmatic Selection

When [SfListView.SelectionMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionMode.html) is set a value other than `None`, you can also select the item / items in SfListView from the code by setting the [SfListView.SelectedItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItem.html) or [SfListView.SelectedItems](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItems.html) property based on the selection mode. The following code example illustrates how to enable selection from code in SfListView.

When the selection mode is `Single` you can programmatically select an item by setting the underlying object to be selected to the `SfListView.SelectedItem` property. 

The following code example illustrates how to programmatically select the item from the code.

{% highlight c# %}

//Perform selection using selected item
listView.SelectedItem = viewModel.Items[5];
{% endhighlight %}

When the selection mode is `Multiple` you can programmatically select more than one item by adding the underlying object to be selected to the `SfListView.SelectedItems` property. 

The following code example illustrates how to programmatically select more than one item from the code.

{% highlight c# %} 
//Perform multiple selection using selected items
listView.SelectedItems.Add (viewModel.Items [4]);
listView.SelectedItems.Add (viewModel.Items[5]);
{% endhighlight %}

You can select all the items in the collection by using [SfListView.SelectAll()](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectAll.html) method.

{% highlight c# %} 
listView.SelectAll();
{% endhighlight %}

## Get Selected Items

SfListView allow you to get the selected item and current selected item by using [SfListView.SelectedItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItem.html) and [SfListView.CurrentItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~CurrentItem.html). The `SelectedItem` property returns the data object of the selected item and the `CurrentItem` returns the data object that currently selected. You can get all the selected items through [SelectedItems](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItems.html) property. 

N> The `SelectedItem` denotes the first selected item in multiple selection. 

### CurrentItem vs SelectedItem

Both [SelectedItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItem.html) and [CurrentItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~CurrentItem.html) returns the same data object when single item is selected in SfListView. When you have selected more than one items, the item that had been selected initially is maintained in `SelectedItem` and the item that currently have focus is maintained in `CurrentItem`.

## Selection Events

### SelectionChanging Event

[SelectionChanging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionChanging_EV.html) event is raised while selecting an item at the execution time before the item is selected. [ItemSelectionChangingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemSelectionChangingEventArgs.html) has the following members which provides the information for `SelectionChanging` event.

* AddedItems – Gets the collection of underlying data objects where the selection going to process.
* RemovedItems – Gets the collection of underlying data objects where the selection going to remove.

You can cancel the selection process within this event by setting `ItemSelectionChangingEventArgs.Cancel` property as true.

The following code example illustrates how to hook the `SelectionChanging` event and cancel the selection of an item.

{% highlight c# %}
listView.SelectionChanging += ListView_SelectionChanging;  

private void ListView_SelectionChanging(object sender, ItemSelectionChangingEventArgs e)
{
  if (e.AddedItems.Count > 0 && e.AddedItems[0] == ViewModel.Items[0])
      e.Cancel = true;
}
{% endhighlight %}

### SelectionChanged Event

The [SelectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionChanged_EV.html) event will occurs once the selection process has been completed for the selected item in SfListView. [ItemSelectionChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemSelectionChangedEventArgs.html) has following members which provides information for `SelectionChanged` event.

* AddedItems – Gets the collection of underlying data objects where the selection has been processed.
* RemovedItems – Gets the collection of underlying data objects from where the selection has been removed.

The following code example illustrates how to hook the `SelectionChanged` event.

{% highlight c# %}
listView.SelectionChanged += ListView_OnSelectionChanged;  

private void ListView_OnSelectionChanged(object sender, ItemSelectionChangedEventArgs e)
{
}
{% endhighlight %}

## Selection Background Color

SfListView allows you set the background color for the selected items by using [SfListView.SelectionBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionBackgroundColor.html) property. By default, the selection background color is `Color.Transparent`. You can change the selection background color at run time by using `SfListView.SelectionBackgroundColor` property.

{% highlight c# %}
listView.SelectionBackgroundColor = Color.Blue;
{% endhighlight %}

## Limitations

When you set the background color for the custom view in [SfListView.ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html), you need to set the `InputTransparent` as `true` for the custom view to process the selection.