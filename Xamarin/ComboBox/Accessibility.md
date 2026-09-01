---
layout: post
title: Accessibility in Xamarin ComboBox Control | Syncfusion
description: Learn here all about accessibility support in Syncfusion Xamarin ComboBox (SfComboBox) control and more.
platform: Xamarin.Forms
control: SfComboBox
documentation: ug
---

# Accessibility in Xamarin ComboBox (SfComboBox)

The [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) control has built-in `AutomationId` properties for its inner elements. The `AutomationId` API enables the automation framework to locate and interact with these elements. To ensure unique `AutomationId` values, the `AutomationId` for inner elements is updated based on the control's `AutomationId`.

For example, if you set the `AutomationId` of the SfComboBox to "Employee ComboBox", the automation framework will reference the drop-down button as "Employee ComboBox Dropdown Button".

The following screenshot illustrates the AutomationIds of inner elements. The automation framework will refer to the dropdown for scrolling items as "Employee ComboBox Dropdown". You can also interact with elements within the HeaderView and FooterView using their `AutomationId`. Note that the automation framework will not interact with the Input Clear Button when the [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_MultiSelectMode) is set to [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.MultiSelectMode.html#Syncfusion_XForms_ComboBox_MultiSelectMode_None) or [`Delimiter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.MultiSelectMode.html#Syncfusion_XForms_ComboBox_MultiSelectMode_Delimiter) mode.

![AutomationId Image](images/AutomationId/AutomationId.png)
