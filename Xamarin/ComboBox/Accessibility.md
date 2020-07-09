---
layout : post
title: AutomationId support for Syncfusion ComboBox control in Xamarin.Forms
description: This topic describes about the support to set AutomationId to find and interact with inner elements in Xamarin.Forms ComboBox.  
platform : Xamarin.Forms
control : SfComboBox
documentation : ug
---

# AutomationId for Xamarin.Forms ComboBox

The SfComboBox control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the SfComboBox control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`.

 For example, If you set SfComboBox's `AutomationId` as "Employee ComboBox", then the automation framework will interact with the drop-down button as "Employee ComboBox Dropdown Button". 

The following screenshot illustrates the AutomationIds of inner elements. The automation framework will interact with the dropdown for scrolling the items as "Employee ComboBox Dropdown". You can also interact with the elements inside the HeaderView and FooterView with the element's AutomationId. The Automation framework will not interact with the Input Clear Button when the `MultiSelectMode` is None and Delimiter mode.

![AutomationId Image](images/AutomationId/AutomationId.png)
