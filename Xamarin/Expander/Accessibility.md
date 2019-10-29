---
layout: post 
title: Automation in Xamarin Expander Control | Syncfusion
description: Describes about setting automation id to find and interact with inner elements in Expander
platform: Xamarin
control: Expander
documentation: ug
---
# AutomationId

The Expander control has built-in `AutomationId` for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the Expander control. To keep unique AutomationId, these inner element's AutomationIds are updated based on Expander control `AutomationId`. 

For example, if we set Expander's AutomationId as "Automation" then Automation framework will interact with expander icon of Expander Header  as `Automation Expander`. 

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>Expander Icon</td>
<td>ControlAutomationId Expander</td>
<td>AutomationItem1 Expander<br/>
where `AutomationItem1` represents Control AutomationId and `Expander` represents the expander dropdownicon. 
</td>
</tr>
</table>

The following image denotes the AutomationIds of inner elements.

![Automation id for expander](expander_images/ExpanderAutomationImage.png)
