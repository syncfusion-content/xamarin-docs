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

### PropertyChanged

The [PropertyChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode~PropertyChanged_EV.html) event will be triggered whenever a properties in TreeViewNode is changed. You can get the name of the property that changed by using the `PropertyName` property of the `PropertyChangedEventArgs`. [RaisedOnPropertyChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode~RaisedOnPropertyChanged.html) is a helper method used to raise the `PropertyChanged` event in TreeViewNode.

{% tabs %}
{% highlight c# %}
treeviewnode.PropertyChanged += Treeviewnode_PropertyChanged;
private void Treeviewnode_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    var name = e.PropertyName;
    DisplayAlert("Name", name , "ok");
}
{% endhighlight %}
{% endtabs %}

## SetDirty

Using this [SetDirty](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode~SetDirty.html) method, you can recomputed the amount of cache for the whole node.

{% endhighlight %}
{% highlight c# %}
node.SetDirty();
{% endhighlight %}
{% endtabs %}

