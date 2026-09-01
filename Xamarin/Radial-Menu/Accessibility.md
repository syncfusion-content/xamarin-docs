---
layout: post
title: Accessibility in Xamarin Radial Menu Control | Syncfusion
description: Discover accessibility support in the Syncfusion Xamarin Radial Menu (SfRadialMenu) control and more.
platform: Xamarin.Forms
control: SfRadialMenu
documentation: ug
---

# Accessibility in Xamarin Radial Menu (SfRadialMenu)

## AutomationId

The [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) control includes built-in `AutomationId` support for its inner elements. The `AutomationId` API enables the automation framework to find and interact with the inner elements of the [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) control. To ensure unique `AutomationIds`, these identifiers are updated based on the control's `AutomationId`.

For instance, if you assign the `AutomationId` of the SfRadialMenu as "Circular Menu" and the first SfRadialMenuItem's `AutomationId` as "Circular Menu List", the automation framework will identify the center button as "Circular Menu Center Button" and the first radial item as "Circular Menu List Item 4 of 6" (where 6 denotes the total item count).

Below is a screenshot illustrating the AutomationIds of inner elements. The automation framework will recognize the Center Back Button as "Circular Menu Center Back Button".

![AutomationId Image](images/AutomationId.png)
