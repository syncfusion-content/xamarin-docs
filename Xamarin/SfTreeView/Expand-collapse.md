---
layout: post
title: Expand and Collapse | TreeView for Xamarin.Forms | Syncfusion
description: Describes about expanding and collapsing nodes of TreeView.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Expand and Collapse

The TreeView allows you to expand and collapse the nodes either by user interaction on the nodes or by programmatically. 

##  Expand Action Target

 Expanding and Collapsing of nodes can be performed either by tapping the expander view or in both expander view and content view by setting the [ExpandActionTarget](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandActionTarget.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeView x:Name="TreeView" ExpandActionTarget="Node"/>

{% endhighlight %}
{% highlight c# %}

// Expands by tapping both expander view and content view.
treeView.ExpandActionTarget = ExpandActionTarget.Node;

{% endhighlight %}
{% endtabs %}

## Auto Expand Mode

By default, the treeview items will be in collapsed state. You can define how the nodes to be expanded while loading the TreeView by using [AutoExpandMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~AutoExpandMode.html) property.

The `AutoExpandMode` property is only applicable for bound mode. For Unbound mode you need to set `IsExpanded` property to `true` while creating the nodes, to be in expanded state while loading the TreeView.

* None : All items are collapsed when loaded.
* RootNodesExpanded : Expands only the root item when loaded.
* AllNodesExpanded : Expands all the items when loaded.

## Programmatic Expand and Collapse

TreeView allows programmatic expand and collapse based on the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) and level by using following methods.

* [ExpandNode(TreeViewNode item)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandNode.html) - Method to expand the particular `TreeViewNode` passed to it.
* [CollapseNode(TreeViewNode item)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~CollapseNode.html) - Method to collapse the particular `TreeViewNode` passed to it.
* [ExpandNodes(int level)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandNodes.html) - Method to expand the all items of level passed to it.
* [CollapseNodes(int level)](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~CollapseNodes.html) - Method to expand the all items of level passed to it.

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

TreeView allows to expand and collapse the nodes by using right and left arrows keys. To expand a node, press the right arrow key and to collapse a node, press the left arrow key on the focused item.

## Events

TreeView exposes following events to handle expanding and collapsing of items.

* [NodeCollapsing](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeCollapsing_EV.html) - It occurs when a node is being collapsed.
* [NodeExpanding](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeExpanding_EV.html) - It occurs when a node is being expanded.
* [NodeCollapsed](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeCollapsed_EV.html) - It occurs when a node is collapsed.
* [NodeExpanded](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeExpanded_EV.html) - It occurs when a node is expanded.

The expanding and collapsing interactions can be handled with the help of `NodeCollapsing` and `NodeExpanding` events and expanded and collapsed interactions can be handled with help of `NodeCollapsed` and `NodeExpanded` events.