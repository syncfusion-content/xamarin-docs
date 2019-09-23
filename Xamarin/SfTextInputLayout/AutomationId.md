---
layout: post
title: AutomationId for inner elements of Syncfusion Text Input Layout
description: How to set AutomationId for inner elements of Text Input Layout
platform: Xamarin
control: SfTextInputLayout
documentation: ug
---

# AutomationId

The text input layout control has built-in AutomationId for inner elements. To keep unique id for inner elements, AutomationId of inner elements are updated based on SfTextInputLayout's AutomationId. For example, if SfTextInputLayout's AutomationId is set as sfTextInputLayout.AutomationId = "textInputLayout", then AutomationId of inner elements will be updated as below:

* `Password Toggle VisibleIcon` - textInputLayout show password.
* `Password Toggle CollapsedIcon` - textInputLayout hide password.
* `DropDown Button` - textInputLayout drop down.
