---
layout : post
title: Accessibility in Xamarin ComboBox control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin ComboBox (SfComboBox) control and more.
platform : Xamarin.Forms
control : SfComboBox
documentation : ug
---

# Accessibility in Xamarin ComboBox (SfComboBox)

The [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`.

 For example, If you set SfComboBox's `AutomationId` as "Employee ComboBox", then the automation framework will interact with the drop-down button as "Employee ComboBox Dropdown Button". 

The following screenshot illustrates the AutomationIds of inner elements. The automation framework will interact with the dropdown for scrolling the items as "Employee ComboBox Dropdown". You can also interact with the elements inside the HeaderView and FooterView with the element's AutomationId. The Automation framework will not interact with the Input Clear Button when the [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_MultiSelectMode) is [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.MultiSelectMode.html#Syncfusion_XForms_ComboBox_MultiSelectMode_None) and [`Delimiter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.MultiSelectMode.html#Syncfusion_XForms_ComboBox_MultiSelectMode_Delimiter) mode.

![AutomationId Image](images/AutomationId/AutomationId.png)
