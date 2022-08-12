---
layout: post
title: Events in Xamarin Chips control | Syncfusion
description: Learn about Events support in Syncfusion Essential Studio Xamarin Chips control, its elements and more.
platform: xamarin
control: Chips
documentation: ug
---

# Events in Xamarin Chips

## SelectionChanging Event
The [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) event is triggered before the Chip is selected. You can restrict a chip from being selected, by canceling this event, by setting [Cancel](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_Cancel) property in the event argument to true. The argument contains the following information,

 * [AddedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_AddedItem) - Used to get the selected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
 * [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_RemovedItem) - Used to get the previous selected or deselected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
 * [Cancel](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_Cancel) - Used to set the value indicating whether the selection should be canceled. 

## SelectionChanged Event
The [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html) event triggered after a chip is selected. The argument contains the following information,

 * [AddedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangedEventArgs_AddedItem) - Get the selected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
 * [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangedEventArgs_RemovedItem) - Get the previous selected or deselected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).

N>  Currently, [`Choice`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipsType.html#Syncfusion_XForms_Buttons_SfChipsType_Choice) and [`Filter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipsType.html#Syncfusion_XForms_Buttons_SfChipsType_Filter) types are only supported for [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) and [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html) events.

##  ChipClicked

The [`ChipClicked`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipClicked) event is triggered when a chip clicked in the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html). The event argument is type of `EventArgs`.

## ItemRemoved Event

The [ItemRemoved](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.ItemRemovedEventArgs.html) event is triggered after the chip is removed from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html). The argument contains the following information,

* [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.ItemRemovedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_ItemRemovedEventArgs_RemovedItem) - Get the removed chip item from the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).

N> The [ItemRemoved](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.ItemRemovedEventArgs.html) event is supported only in the [`Input`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipsType.html#Syncfusion_XForms_Buttons_SfChipsType_Input) type.

## See also

[How to remove the indicator icon from Xamarin.Forms chip group (SfChipGroup)](https://www.syncfusion.com/kb/11270/how-to-remove-the-indicator-icon-from-xamarin-forms-chip-group-sfchipgroup)

[How to restrict chip selection in Xamarin](https://www.syncfusion.com/kb/11205/how-to-restrict-chip-selection-in-xamarin)
