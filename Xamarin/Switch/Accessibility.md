---
layout: post
title: Accessibility in Xamarin Switch Control | Syncfusion
description: Explore the accessibility support provided by the Syncfusion Xamarin Switch (SfSwitch) control.
platform: Xamarin.Forms
control: SfSwitch
documentation: ug
---

# Accessibility in Xamarin Switch (SfSwitch)

## AutomationId 

The [`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) control includes built-in `AutomationId` properties for its inner elements. This `AutomationId` API allows automation frameworks to locate and interact with the inner elements of the [`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) control. Each inner element's AutomationId is uniquely set based on the main control's `AutomationId`.

For instance, if the SfSwitch's `AutomationId` is set to "Turn on Night Mode," the automation framework will identify the [`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) as "Turn on Night Mode Track."
 
When the [`Indeterminate state`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.IndeterminateState.html) is enabled, the automation framework identifies the Off state as "Turn on Night Mode Off Track," the Indeterminate state as "Turn on Night Mode Indeterminate Track," and the On state as "Turn on Night Mode On Track."

N> AutomationId support is available on Android only.

![AutomationId Image](images/AutomationId.png)
