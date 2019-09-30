---
layout: post
title: AutomationId for inner elements of Syncfusion Text Input Layout
description: How to set AutomationId for inner elements of Text Input Layout
platform: Xamarin
control: SfTextInputLayout
documentation: ug
---

# AutomationId

The text input layout control has built-in AutomationId for inner elements. To keep unique id for inner elements, AutomationId of inner elements are updated based on SfTextInputLayout's AutomationId. For example, if SfTextInputLayout's AutomationId is set as sfTextInputLayout.AutomationId = "textInputLayout", then AutomationId of inner elements will be updated as follows.

<table>
<tr>
 <th>Icon</th>
 <th>AutomationId</th>
</tr>
<tr>
<td>Password Toggle VisibleIcon</td>
<td>textInputLayout show password</td>
</tr>
<tr>
<td>Password Toggle CollapsedIcon</td>
<td>textInputLayout hide password</td>
</tr>
<tr>
<td>DropDown Button</td>
<td>textInputLayout drop down</td>
</tr>
</table>
