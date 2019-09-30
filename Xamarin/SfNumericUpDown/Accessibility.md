---
layout: post
title: AutomationId for inner elements of Syncfusion NumericUpDown
description: How to set AutomationId for inner elements of NumericUpDown
platform: Xamarin
control: NumericUpDown
documentation: ug
---

# AutomationId

The NumericUpDown control has built-in AutomationId for inner elements. To keep unique id for inner elements, AutomationId of inner elements are updated based on NumericUpDown's AutomationId. For example, if NumericUpDown's AutomationId is set as sfNumericUpDown.AutomationId = "numericUpDown", then AutomationId of inner elements will be updated as follows.

<table>
<tr>
 <th>Icon</th>
 <th>AutomationId</th>
</tr>
<tr>
<td>Increment Button</td>
<td>numericUpDown increment button</td>
</tr>
<tr>
<td>Decrement Button</td>
<td>numericUpDown decrement button</td>
</tr>
</table>
