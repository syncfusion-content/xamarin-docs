---
layout: post
title: Events in Syncfusion SfComboBox control in Xamarin.Forms
description: This section describes how to use different types of events and interactvity in SfComboBox control (Xamarin.Forms)
platform: Xamarin
control: SfComboBox
documentation: ug
---

# Events and Interactivity in Xamarin SfComboBox

## ValueChanged Event

You can perform operation, while changing the value of [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) Text using the [`ValueChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_ValueChanged) event. [`ValueChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_ValueChanged) event returns the changed value in SfComboBox.

The ValueChanged event returns the following argument.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Displays changed value in SfComboBox</td>
</tr>
</table>

## SelectionChanged Event

The [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectionChanged) event is used to notify when an item is selected from the suggestion list or when dynamically setting the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndex) property of SfComboBox, the event is triggered. For more information, refer to [`this`](https://help.syncfusion.com/xamarin/combobox/retrieving-selected-values) link. The [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectionChanged) event returns the following argument.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds the selected items in SfComboBox</td>
</tr>
</table>

## SelectionChanging Event

The [`SelectionChanging`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectionChanging) event is used to notify, before the selection is going to changed by tapping the suggestion box or dynamically setting the SelectedIndex property of [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html).The [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectionChanged)  event returns the following argument.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Holds the selecting items in SfComboBox.</td>
</tr>
<tr>
<td>Cancel</td>
<td>Restricts the item to be selected.</td>
</tr>
</table>

## FocusChanged Event

The [`FocusChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_FocusChanged) event occurs when the control gets the focus and loses the focus. The argument contains the following information.

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

The [`FilterCollectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_FilterCollectionChanged) event is triggered whenever the items gets filtered in the suggestion.

For more information regarding this refer to [`this`](https://help.syncfusion.com/xamarin/combobox/dealing-with-suggestion-box) link. The [`FilterCollectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_FilterCollectionChanged) event returns the following argument.

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

The [`DropDownClosing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_DropDownClosing) event occurs when the drop-down closes.

### DropDownClosing event args

[`IsItemSelected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.DropDownCancelEventArgs.html#Syncfusion_XForms_ComboBox_DropDownCancelEventArgs_IsItemSelected) - It returns the value indicating whether the  item is selected or not when the dropdown window closes.

 [`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Core.CancelEventArgs.html#Syncfusion_XForms_Core_CancelEventArgs_Cancel) - Closing of the dropdown can be handled by setting the e.Cancel.

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

The [`Completed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_Completed) event is raised when the user finalizes the text in the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) editable mode by pressing return key on the keyboard.

## Tapped Event

The [`Tapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_Tapped) event occurs when the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) is tapped in Non-editable mode.

## LoadMoreButtonTapped Event

The [`LoadMoreButtonTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_LoadMoreButtonTapped) can be triggered only when you tap on the load more button. For more information, refer to [`this`](https://help.syncfusion.com/xamarin/combobox/maximum-display-item-with-expander#load-more-button-tapped-event) link.