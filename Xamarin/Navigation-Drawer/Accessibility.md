---
layout: post
title: Accessibility in Xamarin Navigation Drawer Control | Syncfusion
description: Discover accessibility support in the Syncfusion Xamarin Navigation Drawer (SfNavigationDrawer) control.
platform: Xamarin.Forms
control: SfNavigationDrawer
documentation: ug
---

# Accessibility in Xamarin Navigation Drawer (SfNavigationDrawer)

The [`SfNavigationDrawer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html) control includes a built-in `AutomationId` for its inner elements. The `AutomationId` API enables the automation framework to locate and interact with the inner elements of the `NavigationDrawer` control. To ensure unique `AutomationIds`, these identifiers are updated based on the control's `AutomationId`.

For instance, if you assign the `AutomationId` of the SfNavigationDrawer as "DrawerMenu," the automation framework will identify the grey area as "DrawerMenu Gray Area."

Below is a screenshot illustrating the `AutomationIds` of the inner elements. Interaction with the elements inside the ContentView can be performed using the element's `AutomationId`.

![AutomationId Image](images/AutomationId.png)
