---
layout: post
title: Accessibility in Xamarin Tabbed View Control | Syncfusion
description: Learn about accessibility support in the Syncfusion Xamarin Tabbed View (SfTabView) control and more.
platform: Xamarin
control: SfTabView
documentation: ug
---

# Accessibility in Xamarin Tabbed View (SfTabView)

The [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html) control includes built-in `AutomationId` support for its inner elements. The `AutomationId` property enables automation frameworks to locate and interact with these inner elements within the [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html) control. To ensure uniqueness, the `AutomationId` of inner elements is updated based on the control's `AutomationId`.

For instance, if you set the `AutomationId` of SfTabView to "Phone menu", the automation framework will interact with the More button as "Phone menu More Button". The screenshot below illustrates the `AutomationId` setup for inner elements. The automation framework can also interact with the Center Button and the elements inside the tab item content using their respective `AutomationId`.

![AutomationId Image](images/AutomationId/AutomationId.png)
