---
layout: post
title: Scrolling | TreeView for Xamarin.Forms | Syncfusion
description: Describes about programmatic scrolling of treeview.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Scrolling

## Programmatic scrolling

### Bring InTo View

The TreeView allows programmatically scrolling based on the data model and [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~BringIntoView.html) method.

It also enables and disables the scrolling animation when changing the view. By default, the scrolling will be animated.

{% tabs %}
{% highlight c# %}
private void BringIntoView_Clicked(object sender, EventArgs e)
{
    var count= viewModel.ImageNodeInfo.Count;
    var data = viewModel.ImageNodeInfo[count-1];
    TreeView.BringIntoView(data);
}
{% endhighlight %}
{% endtabs %}

Now, run the application to render the below output:

You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Scrolling-37722442).

#### Scrolls to the child item of the collapsed node

 When scroll to the item which is in collapsed state, TreeView expands the particular node and scroll to the specified item by setting the `canExpand` parameter of `BringIntoView` method to `true`.

#### Scrolls the item into spcified position

The SfTreeView allows to position the scrolled item in the view by passing `ScrollToPosition` as parameter to the [BringIntoView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~BringIntoView.html) methods. The scrolled item can take either of the four positions as explained below. The default position is Start.

* `Start`: Scroll to make the node positioned at the start of the view.
* `MakeVisible`: Scroll to make a specified node visible in the view. If the specified node is already in view, scrolling will not occur.
* `Center`: Scroll to make the node positioned at the center of the view.
* `End`: Scroll to make the node positioned at the end of the view.
Refer the below code snippet to scroll a item to a specific position.

{% tabs %}
{% highlight c# %}
// Scroll to the data after expanding its parent node if it is in collapsed state.
treeView.BringIntoView(data, false, true, ScrollToPosition.MakeVisible);

// Scrolls to the data item to make visible in the view.
treeView.BringIntoView(data, false, false, ScrollToPosition.MakeVisible);
{% endhighlight %}
{% endtabs %}

## Scrollbar Visibility

The TreeView provides an option to enable or disable the `Scrollbar` visibility by using the [IsScrollBarVisible](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~IsScrollBarVisible.html) property. By default, the value will be true.

N> Due to some restrictions in native ScrollView renderer in Xamarin.Forms, you cannot change the `IsScrollBarVisible` value at runtime. It can be defined only when initializing the TreeView.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView" IsScrollBarVisible="False" />
{% endhighlight %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.IsScrollBarVisible=false;
{% endhighlight %}
{% endtabs %}