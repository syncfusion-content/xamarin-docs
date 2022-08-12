---
layout : post
title: Accessibility in Xamarin Switch control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Switch (SfSwitch) control and more.
platform : Xamarin.Forms
control : SfSwitch
documentation : ug
---

# Accessibility in Xamarin Switch(SfSwitch)

## AutomationId 

The [`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the [`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`.

For example, if you set SfSwitch's `AutomationId` as "Turn on Night mode", then the automation framework will interact the [`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) as "Turn on Night mode Track".
 
When you enable the [`Indeterminate state`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.IndeterminateState.html), then the Automation framework will interact the Off state as "Turn on Night mode Off Track", [`Indeterminate state`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.IndeterminateState.html) as "Turn on Night mode Indeterminate Track" and the On state as "Turn on Night mode On Track".

N> AutomationId support works on Android only.

![AutomationId Image](images/AutomationId.png)
