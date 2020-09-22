---
layout: post
title: Working with Xamarin.Forms TreeView | Syncfusion
description: This topic describes how to use Syncfusion Xamarin.Forms TreeView along with interacting events and other different functionalities
platform: xamarin
control: SfTreeView
documentation: ug
---

# Working with TreeView in Xamarin TreeView (SfTreeView)

## Interacting with TreeView Items

### Loaded event

The [Loaded](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) event is raised when the TreeView is loading in view for the first time.

{% tabs %}
{% highlight c# %}
treeView.Loaded += TreeView_Loaded;

private void TreeView_Loaded(object sender, TreeViewLoadedEventArgs e)
{
   DisplayAlert("Message", "TreeView is Loaded", "Done");
}
{% endhighlight %}
{% endtabs %}

The `Loaded` event is used for the following use case:

* To scroll the desired item by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html).

### Tapped event

The [ItemTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) event will be triggered whenever tapping the item.  [ItemTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.ItemTappedEventArgs.html) has the following members which provides the information for `ItemTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the tapped item as its arguments.
 * `Position`: Gets the touch position in the tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView" ItemTapped="TreeView_ItemTapped" />
{% endhighlight %}
{% highlight c# %}

treeView.ItemTapped += TreeView_ItemTapped;

private void TreeView_ItemTapped(object sender, ItemTappedEventArgs e)
{
    DisplayAlert("Item Tapped", "TreeView item tapped", "Close");
}

{% endhighlight %}
{% endtabs %}

You can also download the entire source code of this demo from [here](https://github.com/SyncfusionExamples/item-tapped-treeview-xamarin)

### ItemDoubleTapped event

The [ItemDoubleTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) event will be triggered whenever double tapping the item. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.ItemDoubleTappedEventArgs.html) has the following members providing information for the `ItemDoubleTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the double tapped item as its arguments.
 * `Position`: Gets the touch position in the double tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView" ItemDoubleTapped="TreeView_ItemDoubleTapped" />
{% endhighlight %}
{% highlight c# %}

treeView.ItemDoubleTapped += TreeView_ItemDoubleTapped;

private void TreeView_ItemDoubleTapped(object sender, ItemDoubleTappedEventArgs e)
{
    DisplayAlert("Item DoubleTapped", "TreeView item double tapped", "Close");
}

{% endhighlight %}
{% endtabs %}

You can also download the entire source code of this demo from [here](https://github.com/SyncfusionExamples/item-double-tapped-treeview-xamarin)

### ItemHolding event

The [ItemHolding](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) event will be triggered whenever the item is long pressed.
 [ItemHoldingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.ItemHoldingEventArgs.html) has the following members which provides the information for `ItemHolding` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the hold item as its arguments.
 * `Position`: Gets the touch position in the hold item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView" ItemHolding="TreeView_ItemHolding" />
{% endhighlight %}
{% highlight c# %}

treeView.ItemHolding += TreeView_ItemHolding;
private void TreeView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
    DisplayAlert("Item Hold", "TreeView item is holding","Close");   
}

{% endhighlight %}
{% endtabs %}

You can also download the entire source code of this demo from [here](https://github.com/SyncfusionExamples/item-hold-treeview-xamarin)

### Update the runtime changes

The [PropertyChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_PropertyChanged) event will be triggered whenever a property in the customized TreeViewNode is changed. You can get the name of the property that changed by using the `PropertyName` property of the `PropertyChangedEventArgs`.

{% tabs %}
{% highlight c# %}
treeviewnode.PropertyChanged += Treeviewnode_PropertyChanged;

private void Treeviewnode_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    if (e.PropertyName == "IsExpanded")
    {
        if (treeviewnode.IsExpanded)
            DisplayAlert("treeview", "nodeexpanded", "ok");
        else
            DisplayAlert("treeview", "nodecollapsed", "ok");
    }
}
{% endhighlight %}
{% endtabs %}

### Refresh layout

You can refresh the TreeViewNode from the root node and update all layout by using the [SetDirty](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_SetDirty) method that notifies the tree view layout mechanism to invalidate nodes.

{% tabs %}
{% highlight c# %}
node.SetDirty();
{% endhighlight %}
{% endtabs %}

