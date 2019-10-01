---
layout: post 
title: Automation | Accordion for Xamarin.Forms | Syncfusion.
description: Describes about automation id of Accordion.
platform: Xamarin
control: Accordion
documentation: ug
---
# Automation Id

The Accordion control has built in AutomationId for inner elements. Please find following table of AutomationIds of inner elements. To keep unique AutomationID, These inner element's Automation IDs get updated based on Accordion's Automation ID. For example, if we set Accordion's AutomationId as "Accordion.AutomationId = Automation" then Automation framework will interact the `Accordion` as `AutomationItem1 Expander` when you tap expander icon of first AccordionItem. Here, along with the control's AutomationId, count of an item will also be added. The following image denoted the AutomationIds of inner elements.

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>Expander Icon</td>
<td>ControlAutomationId+Item+ItemNumber Expander</td>
<td>Expander</td>
</tr>
</table>

![Automation id for accordion](accordion_images/AccordionAutomationImage.png)