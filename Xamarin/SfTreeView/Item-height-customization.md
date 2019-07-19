---
layout: post
title: TreeView ItemHeight customization | Xamarin.Forms | Syncfusion
description: Describes the Item Height Customization in SfTreeView.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Item height customization.

The SfTreeView allows customizing the height of the items by the [QueryNodeSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~QueryNodeSize_EV.html) event. This event is raised whenever items come to view and triggered with [QueryNodeSizeEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html).

The `SfTreeView.QueryNodeSize` event provides the following parameters in their arguments:
 
 * [Node](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs~Node.html): Identifies the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with it item as its arguments.
 * [Height](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs~Height.html): Identifies item height of the queried item.
 * [Handled](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs~Handled.html): Decides whether the specified or measured height can be set to the item or not. The default value is false. When this property is not set, the decided height will not set to the item.
 * [GetActualNodeHeight](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs~GetActualNodeHeight.html): Method which returns the measured height of the node item based on content loaded in it.

## Customize item height of a particular item on-demand

TreeView allows to customizing the height of the particular item on-demand by using [QueryNodeSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~QueryNodeSize_EV.html) event.

## AutoFit the items based on the content

TreeView allows adjusting height of items based on the content loaded by using [QueryNodeSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~QueryNodeSize_EV.html) event and [QueryNodeSizeEventArgs.GetActualNodeHeight](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs~GetActualNodeHeight.html) method.
                                             
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">
    <ContentPage.BindingContext>
       <local:FileManagerViewModel x:Name="viewModel"></local:FileManagerViewModel>
    </ContentPage.BindingContext>
    <ContentPage.Content>
       <syncfusion:SfTreeView x:Name="treeView"
                              QueryNodeSize="TreeView_QueryNodeSize"
                              ChildPropertyName="SubFiles"
                              ItemsSource="{Binding ImageNodeInfo}"/>
       </syncfusion:SfTreeView>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public class MainPage : ContentPage
{
    public MainPage()
    {
      InitializeComponent();
      this.treeView.QueryNodeSize += TreeView_QueryNodeSize;
    }
    
    private void TreeView_QueryNodeSize(object sender, QueryNodeSizeEventArgs e)
    {
        if (e.Node.Level == 0)
        {
            //Returns speified item height for items.
            e.Height = 200;
            e.Handled = true;
        }
        else
        {
            // Returns item height based on the content loaded.
            e.Height = e.GetActualNodeHeight();
            e.Handled = true;
        }
    }
}
{% endhighlight %}
{% endtabs %}

 N> If you define any size manually to the view loaded in [ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemTemplate.html), the `SfTreeView` will return that size as the item size for each item.

## Customize item height on dynamic changes


TreeView supports, TreeViewItems to respond for dynamic changes. It is enabled by setting `NodeSizeMode` property to `Dynamic`. The control has two different modes to perform NodeSize calculations during auto fit.

* `None`: TreeViewItem height does not changes for dynamic changes. By default `NodeSizeMode` is `NodeSizeMode.None`
* `Dynamic`: TreeViewItem height responds for dynamic changes and the size is recalculated.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">
    <ContentPage.BindingContext>
       <local:FileManagerViewModel x:Name="viewModel"></local:FileManagerViewModel>
    </ContentPage.BindingContext>
    <ContentPage.Content>
       <syncfusion:SfTreeView x:Name="treeView"
                              QueryNodeSize="TreeView_QueryNodeSize"
                              NodeSizeMode="Dynamic"
                              ChildPropertyName="SubFiles"
                              ItemsSource="{Binding ImageNodeInfo}"/>
       </syncfusion:SfTreeView>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public class MainPage : ContentPage
{
    public MainPage()
    {
      InitializeComponent();
      this.treeView.QueryNodeSize += TreeView_QueryNodeSize;
      this.treeView.NodeSizeMode = NodeSizeMode.Dynamic; 
    }
    
    private void TreeView_QueryNodeSize(object sender, QueryNodeSizeEventArgs e)
    {
        if (e.Node.Level == 0)
        {
            //Returns speified item height for items.
            e.Height = 200;
            e.Handled = true;
        }
        else
        {
            // Returns item height based on the content loaded.
            e.Height = e.GetActualNodeHeight();
            e.Handled = true;
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo [here]().

![AutoFit items](TreeView_images/TreeView_AutoFit_Items.png)


## Limitations

 * Defines the size of the image when loading image in the [SfTreeView.ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemTemplate.html). Because, it does not return actual measured size when measuring before layout the item.