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

### To update the Runtime changes

The [PropertyChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_PropertyChanged) event will be triggered whenever a properties in TreeViewNode is changed. You can get the name of the property that changed by using the `PropertyName` property of the `PropertyChangedEventArgs`.

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

## Refresh layout

You can refresh the TreeViewNode from the root node and update all layout by using the [SetDirty](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_SetDirty) method which notifies the tree view layout mechanism to invalidate nodes.

{% endhighlight %}
{% highlight c# %}
node.SetDirty();
{% endhighlight %}
{% endtabs %}

