---
layout : post
title: AutomationId support for Syncfusion NavigationDrawer control in Forms
description: This topic describes about the support to set AutomationId to find and interact with inner elements in Xamarin.Forms SfNavigationDrawer
platform : Xamarin.Forms
control : SfNavigationDrawer
documentation : ug
---

# AutomationId for Xamarin.Forms NavigationDrawer 

The SfNavigationDrawer control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the `NavigationDrawer` control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`. 

For example, if you set SfNavigationDrawer's `AutomationId` as "DrawerMenu", then the automation framework will interact with the gray area as "DrawerMenu Gray Area". 

The following screenshot illustrates the AutomationIds of inner elements. You can also interact with the elements inside the ContentView with the element's AutomationId.

![AutomationId Image](images/AutomationId.png)
