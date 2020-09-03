---
layout: post 
title: Automation in Xamarin TreeView Control | Syncfusion
description: Describes about setting automation id to TreeView for automation framework to find and interact with control inner elements.
platform: Xamarin
control: TreeView
documentation: ug
---
# AutomationId in Xamarin Treeview (SfTreeView)

The TreeView control has built-in `AutomationId` for inner elements. The [AutomationId](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) API allows the automation framework to find and interact with the inner elements of the TreeView control. To keep unique AutomationId, these inner element's AutomationIds are updated based on TreeView control `AutomationId`. 

For example, if we set TreeView's AutomationId as "Automation" then Automation framework will interact with expander icon of TreeNodeItem  as `AutomationItem1 Expander`. Here, along with the control's AutomationId, index of an item will also be added for differentiating each TreeNodeItem expander. 

<table>
<tr>
<th align="center" >View</th>
<th align="center" >AutomationId Format</th>
<th align="center" >Example</th>
</tr>

<tr>
<td>Expander View</td>
<td>ControlAutomationId+Item+ItemIndex Expander</td>
<td>AutomationItem1 Expander<br/><br/>
where <b>Automation</b> represents Control AutomationId, <b>Item1</b> represents Item text appended with item index which has been generated based on item position and <b>Expander</b> represents the expander dropdown icon. 
</td>
</tr>
</table>

The following image denotes the AutomationIds of inner elements.

![Automation id for expander](TreeView_images/TreeViewAutomationImage.png)
