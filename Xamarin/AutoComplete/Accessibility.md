---
layout : post
title : AutomationId support for Syncfusion AutoComplete control in Xamarin.Forms
description : Set AutomationId to find and interact with inner elements in AutoComplete
platform : Xamarin.Forms
control : SfAutoComplete
documentation : ug
---

# Accessibility

## AutomationId

The SfAutoComplete control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the SfAutoComplete control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`. 

For example, If you set SfAutoComplete's `AutomationId` as "Employee Autocomplete", then the Automation framework will interact with the Token Close Button as "Employee Autocomplete Frank Token Close Button". 

The following screenshot illustrates the AutomationIds of inner elements. The Automation framework will interact with the dropdown for scrolling the items as "Employee Autocomplete Dropdown". You can also interact with the elements inside the HeaderView and FooterView with the element's AutomationId. The Automation framework will not interact with the Input Clear Button when the `MultiSelectMode` is None and Delimiter mode. 

![AutomationId Image](images/AutomationId/AutomationId.png)
