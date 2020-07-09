---
layout : post
title: AutomationId support for Syncfusion TabView Control in Xamarin.Forms
description: This topic describes about the support to set AutomationId to find and interact with inner elements in Xamarin.Forms TabView.
platform : Xamarin.Forms
control : SfTabView
documentation : ug
---

# AutomationId for Xamarin.Forms TabView

The SfTabView control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the SfTabView control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`. 

For example, if you set SfTabView's `AutomationId` as "Phone menu", then the Automation framework will interact with the More button as "Phone menu More Button". The following screenshot illustrates the AutomationIds of inner elements. The Automation framework will also interact with the Center Button and the element's inside the tab item content with the element's AutomationId.

![AutomationId Image](images/AutomationId/AutomationId.png)
