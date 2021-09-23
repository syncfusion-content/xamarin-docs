---
layout : post
title: Accessibility in Xamarin Range Slider control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Range Slider (SfRangeSlider) control and more.
platform : Xamarin.Forms
control : SfRangeSlider
documentation : ug
---

## AutomationId

`SfRangeSlider` does not have support for `AutomationId` to access the thumb along track. Instead, you can change the `RangeStart`, `RangeEnd` using the co-ordinates and `Value` with the button click event with its `AutomationId`.