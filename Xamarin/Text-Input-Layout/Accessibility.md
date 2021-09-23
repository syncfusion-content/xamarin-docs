---
layout: post
title: Accessibility in Xamarin Text Input Layout control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Text Input Layout (SfTextInputLayout) control and more.
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
