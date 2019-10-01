---
layout: post 
title: Automation | TreeView for Xamarin.Forms | Syncfusion.
description: Describes about automation id of expander view
platform: Xamarin
control: SfTreeView
documentation: ug
---
# Automation Id

The TreeView control has built in AutomationId for inner elements. Please find following table of AutomationIds of inner elements. To keep unique AutomationID, These inner element's Automation IDs get updated based on Control's Automation ID. For example, if we set SfTreeView's AutomationId as
"SfTreeView.AutomationId = TreeView" then Automation framework will interact the `Expander` as `TreeViewItem0 Expander`.Here, along with the controls AutomationId Count of the treeview item will be appended. For example - if you tap expander icon of first item then `Item0` will add after control's AutomationId. The following image denoted the AutomationIds of inner elements.

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>Expander View</td>
<td>ControlAutomationId+Item+ItemNumber Expander</td>
<td>Expander</td>
</tr>
</table>

![Automation id for expander](TreeView_images/TreeViewAutomationImage.png)
