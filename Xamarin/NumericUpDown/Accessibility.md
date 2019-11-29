---
layout: post
title: AutomationId for inner elements of Syncfusion NumericUpDown
description: How to set AutomationId for inner elements(up and down buttons) of essential Xamarin.Forms numeric up down control.
platform: Xamarin
control: NumericUpDown
documentation: ug
---

## AutomationId

The NumericUpDown control has built-in AutomationId for inner elements. To keep unique id for inner elements, AutomationId of inner elements are updated based on NumericUpDown's AutomationId. For example, if NumericUpDown's AutomationId is set as sfNumericUpDown.AutomationId = "numericUpDown", then AutomationId of inner elements will be updated as follows.

<table>
<tr>
 <th>Element</th>
 <th>Element AutomationId</th>
 <th>Qualified AutomationId</th>
</tr>
<tr>
<td>Increment Button</td>
<td>increment button</td>
<td>numericUpDown increment button</td>
</tr>
<tr>
<td>Decrement Button</td>
<td>decrement button</td>
<td>numericUpDown decrement button</td>
</tr>
</table>
