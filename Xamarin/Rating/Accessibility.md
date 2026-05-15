---
layout: post
title: Accessibility in Xamarin Rating Control | Syncfusion
description: Explore how Accessibility is supported in the Syncfusion Xamarin Rating (SfRating) control, with a focus on AutomationId.
platform: Xamarin.Forms
control: SfRating
documentation: ug
---
# Accessibility in Xamarin Rating (SfRating)
## AutomationId 

The [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control includes built-in `AutomationId` properties for its inner elements. This feature allows the automation framework to effectively identify and interact with these elements within the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

Setting a unique `AutomationId` ensures that each element can be distinctly recognized. For instance, if you assign the `AutomationId` "Feedback" to `SfRating` and select the fourth item, the automation framework will interact with the control as "Feedback Rating 4". This is particularly useful when the rating component forms part of a custom view, facilitating interaction through the element's `AutomationId`.
> Note: AutomationId support is active only when the precision mode of [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) is configured as [`Standard`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.Precision.html#Syncfusion_SfRating_XForms_Precision_Standard).

![Example of AutomationID usage in SfRating](images/AutomationId.png)
