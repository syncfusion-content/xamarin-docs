---
layout: post
title: Expand and Collapse | TreeView for Xamarin.Forms | Syncfusion
description: Describes about expanding and collapsing nodes of TreeView.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Expand and Collapse

The TreeView allows you to expand and collapse the nodes either by user interaction on the nodes or by programmatically. The expanding and collapsing interactions can be handled with the help of [NodeCollapsing](httpshelp://.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeCollapsing_EV.html) and [NodeExpanding](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeExpanding_EV.html) events of the TreeView. You can expand or collapse the items using touch interactions or by programmatically. By tapping the expander icon, the items get collapse if the item is in expand state and vice-versa.

##  Expand Action Target
  Also, the TreeView allows you to set the restrictions whether expanding and collapsing of nodes can be performed by [ExpandActionTarget](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandActionTarget.html).
  To expand and collapse items by tapping in expander view by setting `ExpandActionTarget.Expander` or in both expander view and content view by using `ExpandActionTarget.Node`.By default `ExpandActionTarget` is set to `Expander`

## Auto Expand Mode
By default, the treeview items will be in collapsed state in the TreeView.
You can define how the nodes to be expanded while loading the TreeView by using [AutoExpandMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~AutoExpandMode.html) property for bound mode and by setting `TreeViewNode.IsExpanded` property to `true` while creating the nodes for unbound mode.
By default `AutoExpandMode` is None.

None : All items are collapsed when loaded.
RootNodesExpanded : Expands only the root item when loaded.
AllNodesExpanded : Expands all the items when loaded.

 N> `AutoExpandMode` property is only applicable for bound mode. For Unbound mode you need to set `IsExpanded` property to `true` while creating the nodes, to be in expanded state while loading the TreeView.

## Programmatic Expand and Collapse

TreeView allows programmatic expand and collapse based on the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) and level by exposing following methods.

[ExpandNode(TreeViewNode item)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandNode.html) - method to expand the particular TreeViewNode passed to it.
[CollapseNode(TreeViewNode item)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~CollapseNode.html) - method to collapse the particular TreeViewNode passed to it.
[ExpandNodes(int level)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandNodes.html) - method to expand the all items of level passed to it.
[CollapseNodes(int level)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~CollapseNodes.html) - method to expand the all items of level passed to it.

Following example explains how to expand and collapse items of treeview programmatically

{% tabs %}
{% highlight c# %}
// Expands all the nodes of root level '0'
treeView.ExpandNodes(0);

// Collapses all the nodes of root level '0'
treeView.CollapseNodes(0);

// Expand a particular node.
treeView.ExpandNode(node);

// Expand a particular node.
treeView.CollapseNode(node);

{% endhighlight %}
{% endtabs %}

## Expand and Collapse using Keyboard

TreeView allows to Expand and collapse using keyboard interactions with the use right and left navigation arrows keys.
To expand a node press right navigation key.To collapse a node press left navigation key.

## Events

TreeView exposes following events to handle expanding and collapsing of items of TreeView
* [NodeCollapsed](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeCollapsed_EV.html)
* [NodeExpanded](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeExpanded_EV.html)
* [NodeCollapsing](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeCollapsing_EV.html)
* [NodeExpanding](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeExpanding_EV.html)

The expanding and collapsing interactions can be handled with the help of `NodeCollapsing` and `NodeExpanding` events and expanded and collapsed interactions can be handled with help `NodeCollapsed` and `NodeExpanded` of the TreeView