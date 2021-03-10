---
layout: post
title: Automation ID in Syncfusion SfCardView control in Xamarin.Forms
description: Learn how to use the automation ID in SfCardView control for running the test cases in Xamarin.Forms
platform: xamarin
control: SfCardView
documentation : ug
---

# AutomationId in SfCardView

The SfCardView control has built-in automation Id for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the `SfCardView` control. To keep unique AutomationId, these inner elements’ AutomationIds are updated based on the control’s `AutomationId`.

For example, if you set SfCardLayout’s `AutomationId` as “CardLayout”, then the automation framework will interact the second card view as “CardLayout 2 of 3” (3 denotes the total count).

