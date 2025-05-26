---
layout: post
title: Accessibility in Xamarin Rotator Control | Syncfusion
description: Understand the accessibility support in the Syncfusion Xamarin Rotator (SfRotator) control.
platform: Xamarin
control: SfRotator
documentation: ug
---

# Accessibility in Xamarin Rotator (SfRotator)

The [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html) control includes built-in `AutomationId` support for its inner elements. The `AutomationId` API lets the automation framework locate and interact with the inner elements of the [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html) control. To ensure unique `AutomationId` values, these IDs are updated based on the control's `AutomationId`.

For instance, if you set the SfRotator's `AutomationId` to "Book Display Rotator" and want to select the fifth index, the automation framework will interact with the [`Thumbnail`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.NavigationStripMode.html#Syncfusion_SfRotator_XForms_NavigationStripMode_Thumbnail) as "Book Display Rotator Index 5 of 5."

The automation framework will only interact with the [`Dots`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.NavigationStripMode.html#Syncfusion_SfRotator_XForms_NavigationStripMode_Dots) and [`Thumbnail`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.NavigationStripMode.html#Syncfusion_SfRotator_XForms_NavigationStripMode_Thumbnail) [`NavigationStripMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_NavigationStripMode). You cannot interact with the rotator item if you want to select an index that is not visible in the view.

> **Note:** Providing `AutomationId` is not possible when the rotator item is populated with a custom template.

![AutomationId Image](images/AutomationId.png)
