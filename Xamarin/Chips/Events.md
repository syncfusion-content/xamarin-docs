---
layout: post
title: Events in Xamarin Chips Control | Syncfusion
description: Learn about events support in Syncfusion Essential Studio® Xamarin Chips control, including its elements and more.
platform: Xamarin
control: Chips
documentation: ug
---

# Events in Xamarin Chips

## SelectionChanging Event
The [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) event is triggered before a chip is selected. You can restrict a chip from being selected by canceling this event, which is done by setting the [Cancel](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_Cancel) property in the event argument to true. The argument contains the following information:

 * [AddedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_AddedItem) - Used to get the selected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
  * [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_RemovedItem) - Used to get the previously selected or deselected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
 * [Cancel](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_Cancel) - Used to set the value indicating whether the selection should be canceled. 

## SelectionChanged Event
The [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html) event is triggered after a chip is selected. The argument contains the following information:

  * [AddedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangedEventArgs_AddedItem) - Gets the selected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
  * [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangedEventArgs_RemovedItem) - Gets the previously selected or deselected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).

> **Note:** Currently, the [`Choice`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipsType.html#Syncfusion_XForms_Buttons_SfChipsType_Choice) and [`Filter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipsType.html#Syncfusion_XForms_Buttons_SfChipsType_Filter) types are only supported for [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) and [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html) events.

## ChipClicked

The [`ChipClicked`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipClicked) event is triggered when a chip is clicked within the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html). The event argument is of type `EventArgs`.

## ItemRemoved Event

The [ItemRemoved](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.ItemRemovedEventArgs.html) event is triggered after a chip is removed from the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html). The argument contains the following information:

  * [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.ItemRemovedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_ItemRemovedEventArgs_RemovedItem) - Gets the removed chip item from the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).

> **Note:** The [ItemRemoved](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.ItemRemovedEventArgs.html) event is supported only in the [`Input`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipsType.html#Syncfusion_XForms_Buttons_SfChipsType_Input) type.

## See also

- [How to remove the indicator icon from Xamarin.Forms chip group (SfChipGroup)](https://support.syncfusion.com/kb/article/9826/how-to-remove-the-indicator-icon-from-xamarin-forms-chip-group-sfchipgroup)

- [How to restrict chip selection in Xamarin](https://support.syncfusion.com/kb/article/9678/how-to-restrict-chip-selection-in-xamarin)
