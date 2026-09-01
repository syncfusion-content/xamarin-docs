---
layout: post
title: Accessibility in Xamarin Range Slider Control | Syncfusion
description: Discover how to implement accessibility features in the Syncfusion Xamarin Range Slider (SfRangeSlider) control.
platform: Xamarin.Forms
control: SfRangeSlider
documentation: ug
---

# Accessibility in Xamarin Range Slider

The [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) control currently does not support the `AutomationId` property for accessing the slider thumb along the track. However, you can manipulate the [`RangeStart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_RangeStart), [`RangeEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_RangeEnd), and [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Value) properties using coordinates. Additionally, these values can be adjusted through a button click event utilizing its `AutomationId`.
