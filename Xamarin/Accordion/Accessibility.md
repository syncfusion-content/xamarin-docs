---
layout: post 
title: Automation in Xamarin Accordion Control | Syncfusion
description: Describes about setting automation id to find and interact with inner elements in Accordion
platform: Xamarin
control: Accordion
documentation: ug
---
# AutomationId

The Accordion control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the Accordion control. To keep unique AutomationId, these inner element's AutomationIds are updated based on Accordion control `AutomationId`. 

For example, if we set Accordion's AutomationId as "Automation" then Automation framework will interact with expander icon of AccordionItem  as `AutomationItem1 Expander`. Here, along with the control's AutomationId, index of an item will also be added for differentiating each AccordionItem expander. 

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>Expander Icon</td>
<td>ControlAutomationId+Item+ItemIndex Expander</td>
<td>AutomationItem1 Expander</td>
</tr>
</table>

The following image denotes the AutomationIds of inner elements.

![Automation id for accordion](accordion_images/AccordionAutomationImage.png)