---
layout: post
title: Events for Syncfusion ChipGroup control in Xamarin.Forms
description: This section describes the events in the Xamarin.Forms Syncfusion SfChipGroup Such as SelectionChanging and SelectionChanged
platform: Xamarin.Forms
control: Chips
documentation: ug
---

# Event of SfChipGroup

## SelectionChanging Event
The [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) event is triggered before the Chip is selected. You can restrict a chip from being selected, by canceling this event, by setting Cancel property in the event argument to true. The argument contains the following information,

 * [AddedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_AddedItem) - Used to get the selected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
 * [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_RemovedItem) - Used to get the previous selected or deselected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
 * [Cancel](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangingEventArgs_Cancel) - Used to set the value indicating whether the selection should be canceled. 

## SelectionChanged Event
The [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html) event triggered after a chip is selected. The argument contains the following information,

 * [AddedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangedEventArgs_AddedItem) - Get the selected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).
 * [RemovedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html#Syncfusion_Buttons_XForms_SfChip_SelectionChangedEventArgs_RemovedItem) - Get the previous selected or deselected chip from [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html).

N>  Currently, `Choice` and `Filter` types are only supported for [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) and [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html) events.

## See also

[How to remove the indicator icon from Xamarin.Forms chip group (SfChipGroup)](https://www.syncfusion.com/kb/11270/how-to-remove-the-indicator-icon-from-xamarin-forms-chip-group-sfchipgroup)

[How to restrict chip selection in Xamarin](https://www.syncfusion.com/kb/11205/how-to-restrict-chip-selection-in-xamarin)