---
layout: post
title: Events in Syncfusion SfComboBox Control in Xamarin.Forms
description: This section describes how to use different types of events and interactivity in the SfComboBox control (Xamarin.Forms)
platform: Xamarin
control: SfComboBox
documentation: ug
---

# Events and Interactivity in Xamarin SfComboBox

## ValueChanged Event

You can perform operations while changing the text value of the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) using the [`ValueChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_ValueChanged) event. This event returns the changed value in the SfComboBox.

The `ValueChanged` event provides the following argument:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Displays the changed value in the SfComboBox</td>
</tr>
</table>

## SelectionChanged Event

The [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectionChanged) event is triggered when an item is selected from the suggestion list or when the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndex) property of the SfComboBox is set dynamically.

For more information, refer to [this link](https://help.syncfusion.com/xamarin/combobox/retrieving-selected-values). The `SelectionChanged` event returns the following argument:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds the selected items in the SfComboBox</td>
</tr>
</table>

## SelectionChanging Event

The [`SelectionChanging`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectionChanging) event notifies you before the selection changes, either by tapping the suggestion box or dynamically setting the SelectedIndex property of the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html).

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds the items being selected in the SfComboBox.</td>
</tr>
<tr>
<td>Cancel</td>
<td>Prevents the item from being selected.</td>
</tr>
</table>

## FocusChanged Event

The [`FocusChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_FocusChanged) event occurs when the control gains or loses focus. The argument contains the following information.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>HasFocus</td>
<td>Indicates whether the control is in focused state or not.</td>
</tr>
</table>

## FilterCollectionChanged Event

The [`FilterCollectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_FilterCollectionChanged) event is triggered when items are filtered in the suggestion list.

For more information, refer to [this link](https://help.syncfusion.com/xamarin/combobox/dealing-with-suggestion-box). The `FilterCollectionChanged` event returns the following argument.
<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds the filtered items in the suggestion.</td>
</tr>
</table>

## DropDownOpen Event

The [`DropDownOpen`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.DropDownOpenEventHandler.html) event occurs when the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) drop-down is opened.

## DropDownClosing Event

The [`DropDownClosing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DropDownClosing) event occurs when the drop-down is about to close.

### DropDownClosing event args

[`IsItemSelected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.DropDownCancelEventArgs.html#Syncfusion_XForms_ComboBox_DropDownCancelEventArgs_IsItemSelected) returns a value indicating whether an item is selected when the dropdown closes.

[`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Core.CancelEventArgs.html#Syncfusion_XForms_Core_CancelEventArgs_Cancel) allows handling the closure of the dropdown by setting `e.Cancel`.

{% tabs %}

{% highlight xaml %}

    <combobox:SfComboBox HeightRequest="40"
                             x:Name="comboBox"
                             DataSource="{Binding EmployeeCollection}"
                             DropDownClosing="SfComboBox_DropDownClosing"
                             DisplayMemberPath="Name"
                             />

{% endhighlight %}

{% highlight C# %}

     public MainPage()
     {
       InitializeComponent();
       comboBox.DropDownClosing += SfComboBox_DropDownClosing;
     }

     private void SfComboBox_DropDownClosing(object sender, DropDownCancelEventArgs e)
     {
            if (e.IsItemSelected)
            {
                e.Cancel = true;
            }
            else
            {

                e.Cancel = false;
            }
     }

{% endhighlight %}

{% endtabs %}


## DropDownClosed Event

The [`DropDownClosed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DropDownClosed) event occurs when the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) drop-down is closed.

## Completed Event

The [`Completed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_Completed) event is raised when the user finalizes the text in the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) editable mode by pressing the return key on the keyboard.

## Tapped Event

The [`Tapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_Tapped) event occurs when the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) is tapped in non-editable mode.

## LoadMoreButtonTapped Event

The [`LoadMoreButtonTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_LoadMoreButtonTapped) event is triggered only when the load more button is tapped. For more information, refer to [this link](https://help.syncfusion.com/xamarin/combobox/maximum-display-item-with-expander#load-more-button-tapped-event).
