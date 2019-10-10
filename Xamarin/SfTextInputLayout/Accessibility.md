---
layout: post
title: AutomationId for inner elements of Syncfusion Text Input Layout
description: How to set AutomationId for inner elements(password toggle icon and drop down icon) of essential Xamarin.Forms text input layout control.
platform: Xamarin
control: SfTextInputLayout
documentation: ug
---

## AutomationId

The text input layout control has built-in AutomationId for inner elements. To keep unique id for inner elements, AutomationId of inner elements are updated based on SfTextInputLayout's AutomationId. For example, if SfTextInputLayout's AutomationId is set as sfTextInputLayout.AutomationId = "textInputLayout", then AutomationId of inner elements will be updated as follows.

<table>
<tr>
 <th>Element</th>
 <th>Element AutomationId</th>
 <th>Qualified AutomationId</th>
</tr>
<tr>
<td>Password Toggle VisibleIcon</td>
<td>show password</td>
<td>textInputLayout show password</td>
</tr>
<tr>
<td>Password Toggle CollapsedIcon</td>
<td>hide password</td>
<td>textInputLayout hide password</td>
</tr>
<tr>
<td>DropDown Button</td>
<td>drop down</td>
<td>textInputLayout drop down</td>
</tr>
</table>
