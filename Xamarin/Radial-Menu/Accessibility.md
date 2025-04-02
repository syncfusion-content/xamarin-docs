---
layout : post
title: Accessibility in Xamarin Radial Menu control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Radial Menu (SfRadialMenu) control and more.
platform : Xamarin.Forms
control : SfRadialMenu
documentation : ug
---

# Accessibility in Xamarin RadialMenu(SfRadialMenu)
## AutomationId

The [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) control. To keep unique AutomationId, these inner elements AutomationIds are updated based on the control's `AutomationId`. 

For example, if you set SfRadialMenu's `AutomationId` as "Circular Menu" and the first SfRadialMenuItem's `AutomationId` as "Circular Menu List", then the automation framework will interact with the center button as "Circular Menu Center Button" and the first radial item as "Circular Menu List Item 4 of 6" (6 denotes the total count). 

The following screenshot illustrates the AutomationIds of inner elements. The automation framework will interact with the Center Back Button as "Circular Menu Center Back Button".

![AutomationId Image](images/AutomationId.png)
