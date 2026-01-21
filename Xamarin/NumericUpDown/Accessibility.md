---
layout: post
title: Accessibility in Xamarin NumericUpDown Control | Syncfusion
description: Learn all about accessibility support in the Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control and more.
platform: Xamarin
control: NumericUpDown
documentation: ug
---

# AutomationId in Xamarin NumericUpDown (SfNumericUpDown)

The [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) control provides built-in automation IDs for its inner elements. To ensure each inner element has a unique ID, these automation IDs are updated based on the `SfNumericUpDown` control's own `AutomationId`. For example, if the `AutomationId` of the `SfNumericUpDown` control is set as `sfNumericUpDown.AutomationId = "numericUpDown"`, then the automation IDs of the inner elements will be as follows:

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
