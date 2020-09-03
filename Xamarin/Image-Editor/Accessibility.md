---
layout: post
title: Automation ID in Syncfusion SfImageEditor control in Xamarin.Forms
description: Learn how to use the automation ID in SfImageEditor control for running the test cases in Xamarin.Forms
platform: xamarin.forms
control: SfImageEditor
documentation : ug
---

# AutomationId in SfImageEditor

The SfImageEditor control has built-in automation Id for inner elements. The [`AutomationId`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html) API allows the automation framework to find and interact with the inner elements of the SfImageEditor control. To keep unique AutomationId, these inner elements' AutomationIds are updated based on the control's `AutomationId`. For example, if you set automationId as `ImageEditor`, then the automation framework will interact with the Undo button as `ImageEditorUndo`. The following screenshot illustrates the AutomationIds  for toolbar elements.

![SfImageEditor](ImageEditor_images/Automation.jpg)
![SfImageEditor](ImageEditor_images/TextAutomation.jpg)
![SfImageEditor](ImageEditor_images/TextAutomationId.jpg)
![SfImageEditor](ImageEditor_images/EditTextAutomation.jpg)
![SfImageEditor](ImageEditor_images/DeleteAutomation.jpg)
![SfImageEditor](ImageEditor_images/PathAutomation.jpg)
![SfImageEditor](ImageEditor_images/ColorAutomation.jpg)
![SfImageEditor](ImageEditor_images/ShapeAutomation.jpg)
![SfImageEditor](ImageEditor_images/TransformAutomation.jpg)
![SfImageEditor](ImageEditor_images/CropAutomation.jpg)