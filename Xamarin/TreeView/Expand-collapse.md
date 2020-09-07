---
layout: post
title: Expand and Collapse | TreeView for Xamarin.Forms | Syncfusion
description: Describes expanding and collapsing treeview nodes in xamarin.forms. And also explains about events associated with expanding and collapsing.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Expand and Collapse in Xamarin TreeView (SfTreeView)

The TreeView allows you to expand and collapse the nodes either by user interaction on the nodes or by programmatically. 

##  Expand Action Target

 Expanding and Collapsing of nodes can be performed either by tapping the expander view or in both expander view and content view by setting the [ExpandActionTarget](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ExpandActionTarget) property.

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

By default, the treeview items will be in collapsed state. You can define how the nodes to be expanded while loading the TreeView by using [AutoExpandMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_AutoExpandMode) property.

The `AutoExpandMode` property is only applicable for bound mode. For Unbound mode you need to set `IsExpanded` property to `true` while creating the nodes, to be in expanded state while loading the TreeView.

* None : All items are collapsed when loaded.
* RootNodesExpanded : Expands only the root item when loaded.
* AllNodesExpanded : Expands all the items when loaded.

## Programmatic Expand and Collapse

TreeView allows programmatic expand and collapse based on the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) and level by using following methods.

* [ExpandNode(TreeViewNode item)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ExpandNode_Syncfusion_TreeView_Engine_TreeViewNode_) - Method to expand the particular `TreeViewNode` passed to it.
* [CollapseNode(TreeViewNode item)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CollapseNode_Syncfusion_TreeView_Engine_TreeViewNode_) - Method to collapse the particular `TreeViewNode` passed to it.
* [ExpandNodes(int level)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ExpandNodes_System_Int32_) - Method to expand the all items of level passed to it.
* [CollapseNodes(int level)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CollapseNodes_System_Int32_) - Method to expand the all items of level passed to it.

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

### Expand and Collapse all the nodes

Expand and Collapse all the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) programmatically at runtime by using the [SfTreeView.ExpandAll](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ExpandAll) method and [SfTreeView.CollapseAll](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CollapseAll) method.

{% tabs %}
{% highlight c# %}

//Expands all the nodes
treeView.ExpandAll();

//Collapses all the nodes
treeView.CollapseAll();

{% endhighlight %}
{% endtabs %}

## Expand and Collapse using Keyboard

TreeView allows to expand and collapse the nodes by using right and left arrows keys. To expand a node, press the right arrow key and to collapse a node, press the left arrow key on the focused item.

## Events

TreeView exposes following events to handle expanding and collapsing of items.

* [NodeCollapsing](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) - It occurs when a node is being collapsed.
* [NodeExpanding](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) - It occurs when a node is being expanded.
* [NodeCollapsed](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) - It occurs when a node is collapsed.
* [NodeExpanded](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) - It occurs when a node is expanded.

The expanding and collapsing interactions can be handled with the help of `NodeCollapsing` and `NodeExpanding` events and expanded and collapsed interactions can be handled with help of `NodeCollapsed` and `NodeExpanded` events.

You can also achieve handle expand and collapse operation using [ExpandCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ExpandCommand) and [CollapseCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CollapseCommand) .

## See also

[How to expand and collapse TreeView node using image instead expander](https://www.syncfusion.com/kb/10289/)                                                                                                                                                                                           
[How to expand the particular TreeView node in Xamarin.Forms (SfTreeView)](https://www.syncfusion.com/kb/11361/)                                                                                                                                                                                                                        
[How to expand the TreeView node using MR.Gesture in Xamarin.Forms (SfTreeView)](https://www.syncfusion.com/kb/11368/)                                                                                                                                                                                                                                  