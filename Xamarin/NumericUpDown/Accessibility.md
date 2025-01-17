---
layout: post
title: Accessibility in Xamarin NumericUpDown control | Syncfusion<sup>®</sup>
description: Learn here all about Accessibility support in Syncfusion<sup>®</sup> Xamarin NumericUpDown (SfNumericUpDown) control and more.
platform: Xamarin
control: NumericUpDown
documentation: ug
---

# AutomationId in Xamarin NumericUpDown (SfNumericUpDown)

The [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) control has built-in AutomationId for inner elements. To keep unique id for inner elements, AutomationId of inner elements are updated based on NumericUpDown's AutomationId. For example, if NumericUpDown's AutomationId is set as sfNumericUpDown.AutomationId = "numericUpDown", then AutomationId of inner elements will be updated as follows.

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
