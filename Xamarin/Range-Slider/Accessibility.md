---
layout : post
title : AutomationId support for Syncfusion RangeSlider control in Forms
description : AutomationId to find and interact with inner elements in RangeSlider
platform : Xamarin.Forms
control : SfRangeSlider
documentation : ug
---

## AutomationId

`SfRangeSlider` does not have support for `AutomationId` to access the thumb along track. Instead, you can change the `RangeStart`, `RangeEnd` using the co-ordinates and `Value` with the button click event with its `AutomationId`.