---
layout: post
title: Interacting with TreeView for Xamarin.Forms | Syncfusion
description: Describes about the different interactions on TreeView.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Interactivity

 This section explains about how to interact with `TreeView` and its items.

## Interacting with TreeView items

### Loaded event

The [Loaded](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~Loaded_EV.html) event is raised when the TreeView is loading in view for the first time.

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

* To scroll the desired item by using the [BringIntoView](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeCollapsed_EV.html).

### Tapped event

The [ItemTapped](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemTapped_EV.html) event will be triggered whenever tapping the item.  [ItemTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.ItemTappedEventArgs.html) has the following members which provides the information for `ItemTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the tapped item as its arguments.
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

The `ItemTapped` event is used for the following use cases:

* To show the context menu.
* To navigate to another page.
* To delete the item in the treeview at runtime.
* To display the item details into another view.
* To change the underlying bound data.
* To skip other events like selection events if the Handled property set to true.

### ItemDoubleTapped event

The [ItemDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemDoubleTapped_EV.html) event will be triggered whenever double tapping the item. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.ItemDoubleTappedEventArgs.html) has the following members providing information for the `ItemDoubleTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the double tapped item as its arguments.
 * `Position`: Gets the touch position in the double tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemDoubleTapped += TreeView_ItemDoubleTapped;

private void TreeView_ItemDoubleTapped(object sender, ItemDoubleTappedEventArgs e)
{
    DisplayAlert("Item DoubleTapped", "TreeView item double tapped", "Close");
}

{% endhighlight %}
{% endtabs %}

### ItemHolding event

The [ItemHolding](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemHolding_EV.html) event will be triggered whenever the item is long pressed.
 [ItemHoldingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.ItemHoldingEventArgs.html) has the following members which provides the information for `ItemHolding` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with the hold item as its arguments.
 * `Position`: Gets the touch position in the hold item.
 * `Handled`: Gets or sets whether the event is handled or not.

{% tabs %}
{% highlight c# %}

treeView.ItemHolding += TreeView_ItemHolding;
private void TreeView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
    DisplayAlert("Item Hold", "TreeView item is holding","Close");   
}

{% endhighlight %}
{% endtabs %}