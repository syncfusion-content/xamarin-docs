---
layout : post
title : Events for Syncfusion ChipGroup control for Xamarin.Forms
description : Learn how to use the SfChipGroup event
platform : xamarin
control : Chips
documentation : ug
---

# Event

## SelectionChanging Event
The [SelectionChanging](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) event is triggered before the Chip is selected. You can restrict a chip from being selected, by canceling this event, by setting Cancel property in the event argument to true. The argument contains the following information,

 * [AddedItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs~AddedItem.html) - Used to get the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfChipGroup.html) of selected chip.
 * [RemovedItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs~RemovedItem.html) - Used to get the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfChipGroup.html) previous selected or deselected chip.
 * [Cancel](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs~Cancel.html) - Used to set the value indicating whether the selection should be canceled. 

## SelectionChanged Event
The [SelectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html
) event will occur once selection process has been completed for the selected item in the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfChipGroup.html). [SelectionChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html
) has the following members which provides information for [SelectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html
) event.

 * [AddedItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs~AddedItem.html
) - Get the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfChipGroup.html) of selected chip.
 * [RemovedItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs~RemovedItem.html
) - Get the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfChipGroup.html) previous selected or deselected chip.

N>  Currently, the [SelectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangedEventArgs.html
) and [SelectionChanging](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.Buttons.XForms.SfChip.SelectionChangingEventArgs.html) event occurs only `Choice` and `Filter` types.

