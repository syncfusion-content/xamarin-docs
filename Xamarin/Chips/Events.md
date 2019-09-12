---
layout : post
title : Events for Syncfusion ChipGroup control for Xamarin.Forms
description : Learn how to customize the basic features of SfChipGroup
platform : xamarin
control : Chips
documentation : ug
---

# Event

## SelectionChanging Event
The `SelectionChanging` event is raised while selecting an item at the execution time. `SelectionChangingEventArgs` has the following members which provides the information for `SelectionChanging` event:

 * `AddedItem` - Used to get the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfChipGroup.html) of selected chip.
 * `RemovedItem` - Used to get the [SfChipGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfChipGroup.html) previous selected or deselected chip.
 * `Cancel` - Used to set the value indicating whether the selection should be canceled. 

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
) and `SelectionChanging` event occurs only `Choice` and `Filter` types.

