---
layout: post
title: Scrolling | TreeView | Xamarin.Forms | Syncfusion
description: Describes how to achieve programmatic scrolling in treeview.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Scrolling
The TreeView provides various options to achieve programmatic scrolling. Please walkthrough the below section in detail to achieve the same.

## Bring Into View

The TreeView allows programmatic scrolling based on the data model and [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_BringIntoView_Syncfusion_TreeView_Engine_TreeViewNode_System_Boolean_System_Boolean_Syncfusion_XForms_TreeView_ScrollToPosition_) method.

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

You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Scrolling-37722442).

The `BringIntoView` method comprises of other optional parameters to decide on the way in which the child item should come into view. 

### Scroll to the child item with animation

The second optional parameter `disableAnimation` in `BringIntoView` method decides whether the scrolling animation should be enabled or disabled when the child item comes into view. By default, the scrolling will be animated.

* If the parameter value is `true`, scrolling animation will be disabled.
* If the parameter value is `false`, scrolling animation will be enabled.

{% tabs %}
{% highlight c# %}
private void BringIntoView_Clicked(object sender, EventArgs e)
{
    var count= viewModel.ImageNodeInfo.Count;
    var data = viewModel.ImageNodeInfo[count-1];
    // Here, the second optional parameter has been passed as true hence it will disable the animation
    TreeView.BringIntoView(data, true);
}
{% endhighlight %}
{% endtabs %}

### Scroll to the collapsed child item

 The third optional parameter `canExpand` in `BringIntoView` method decides whether we need to expand and show the collapsed node or not when item passed for `BringIntoView` method which is in collapsed state. By default, this parameter value will be `false`.
 
 * If the parameter value is `true`, TreeView expands the collapsed node if it is collapsed and scroll to the specified item.
 * If the parameter value is `false`, TreeView does not expand the collapsed node and only scroll for item which is not in collapsed state.

{% tabs %}
{% highlight c# %}
private void BringIntoView_Clicked(object sender, EventArgs e)
{
    var count= viewModel.ImageNodeInfo.Count;
    var data = viewModel.ImageNodeInfo[count-1];
    TreeView.BringIntoView(data, false, true);
}
{% endhighlight %}
{% endtabs %}

N> We need to set the [NodePopulationMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_NodePopulationMode) API value as `PopulationMode.Instant` for scrolling to the collapsed item in addition to the additional parameter passed to the `BringIntoView` method.

### Scroll the item into specified position

The fourth optional parameter `scrollToPosition` in `BringIntoView` method allows to position the scrolled item in the view. The scrolled item can take either of the four positions as explained below. The default position is `Start`.

* `Start`: Scroll to make the node positioned at the start of the view.
* `MakeVisible`: Scroll to make a specified node visible in the view. If the specified node is already in view, scrolling will not occur.
* `Center`: Scroll to make the node positioned at the center of the view.
* `End`: Scroll to make the node positioned at the end of the view.

{% tabs %}
{% highlight c# %}
private void BringIntoView_Clicked(object sender, EventArgs e)
{
    var count= viewModel.ImageNodeInfo.Count;
    var data = viewModel.ImageNodeInfo[count-1];
    // Scrolls to the data item to make visible in the view.
    treeView.BringIntoView(data, false, false, ScrollToPosition.MakeVisible);
}
{% endhighlight %}
{% endtabs %}

## Scrollbar Visibility

The TreeView provides an option to enable or disable the `Scrollbar` visibility by using the [IsScrollBarVisible](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_IsScrollBarVisible) property. By default, the value will be true.

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