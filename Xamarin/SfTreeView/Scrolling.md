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

The TreeView allows programmatically scrolling based on the data model and [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~BringIntoView.html) method. It also enables and disables the scrolling animation when changing the view. By default, the scrolling will be animated.

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