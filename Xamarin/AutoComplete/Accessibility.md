---
layout: post
title: Accessibility in Xamarin AutoComplete control | Syncfusion
description: Learn about Accessibility support in Syncfusion Xamarin AutoComplete (SfAutoComplete) control and more details.
platform: xamarin
control: SfAutoComplete
documentation: ug
---

# Accessibility in Xamarin AutoComplete (SfAutoComplete)

## AutomationId

The [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) control provides built-in `AutomationId` support for its inner elements. This feature allows automation frameworks to find and interact with specific components within the control. To maintain uniqueness, the AutomationIds of inner elements are dynamically updated based on the control's own `AutomationId`.

For example, if you set the SfAutoComplete's `AutomationId` as "Employee Autocomplete", the automation framework will interact with a token close button as "Employee Autocomplete Frank Token Close Button".

The following screenshot illustrates the AutomationIds of inner elements:
![AutomationId Image](images/AutomationId/AutomationId.png)

The automation framework will interact with:
- The dropdown for scrolling items as "Employee Autocomplete Dropdown"
- Elements inside HeaderView and FooterView using their respective AutomationIds

**Note:** The automation framework will not interact with the Input Clear Button when the [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_MultiSelectMode) is set to either [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.MultiSelectMode.html#Syncfusion_SfAutoComplete_XForms_MultiSelectMode_None) or [`Delimiter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.MultiSelectMode.html#Syncfusion_SfAutoComplete_XForms_MultiSelectMode_Delimiter) mode.

## See Also

* [Xamarin AutoComplete Features Overview](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete)
* [Xamarin.Forms AutoComplete Examples](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete)
