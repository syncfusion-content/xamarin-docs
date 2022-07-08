---
layout : post
title: Accessibility in Xamarin Navigation Drawer control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Navigation Drawer (SfNavigationDrawer) control and more.
platform : Xamarin.Forms
control : SfNavigationDrawer
documentation : ug
---

# Accessibility in Xamarin Navigation Drawer (SfNavigationDrawer)

The SfNavigationDrawer control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the [`NavigationDrawer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html) control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`. 

For example, if you set SfNavigationDrawer's `AutomationId` as "DrawerMenu", then the automation framework will interact with the gray area as "DrawerMenu Gray Area". 

The following screenshot illustrates the AutomationIds of inner elements. You can also interact with the elements inside the ContentView with the element's AutomationId.

![AutomationId Image](images/AutomationId.png)
