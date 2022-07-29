---
layout: post
title: Accessibility in Xamarin Picker control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Picker (SfPicker) control and more.
platform: Xamarin
control: SfPicker
documentation: ug
---

# Accessibility in Xamarin Picker (SfPicker)

The Xamarin Picker control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the [`SfPicker`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPicker.XForms.SfPicker.html) control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`. 

For example, if you set SfPicker's `AutomationId` as "Date picker", then the automation framework will interact with the OK button as "Date picker OK Button". The following screenshot illustrates the AutomationIds of inner elements. 

You can only interact with the header, column header, OK, and Cancel buttons.

![AutomationId Image](images/AutomationId.png)

N> You can refer to our [Xamarin Picker](https://www.syncfusion.com/xamarin-ui-controls/xamarin-picker) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms Picker example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/Picker) to knows the functionalities of each feature.