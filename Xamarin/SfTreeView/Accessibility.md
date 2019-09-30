---
layout: post 
title: Automation | TreeView for Xamarin.Forms | Syncfusion.
description: Describes about automation id of expander view
platform: Xamarin
control: SfTreeView
documentation: ug
---
# Automation Id

The TreeView control has built in AutomationId for inner elements. Please find following table of AutomationIds of inner elements. To keep unique 
AutomationID, These inner element's Automation IDs get updated based on Control's Automation ID. For example, if we set SfTreeView's AutomationId as
"SfTreeView.AutomationId = TreeView" then Automation framework will intract the `Expander` as `TreeViewItem0 Expander`. The following
image denoted the AutomationIds of inner elements.

![Automation id for expander](TreeView_images/TreeViewAutomationImage.png)
