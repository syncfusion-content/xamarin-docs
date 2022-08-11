---

layout : post
title: Accessibility in Xamarin Rating control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Rating (SfRating) control and more.
platform : Xamarin.Forms
control : SfRating
documentation : ug

---

## AutomationId 

The [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the SfRating control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`. 

For example, if you set SfRating's `AutomationId` as "Feedback" and you select the fourth item, then the automation framework will interact with the SfRating as "Feedback Rating 4". When the rating is added as custom view, the Automation framework will interact with the element's `AutomationId`.

N> AutomationId support works only when the precision mode of [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) is set as Standard.

![AutomationId Image](images/AutomationId.png)
