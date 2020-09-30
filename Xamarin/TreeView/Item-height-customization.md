---
layout: post
title: Item Height Customization in Xamarin TreeView | Syncfusion
description: Customize the height of the items in a Xamarin.Forms TreeView. Autofit the items based on node content.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Item Height Customization in Xamarin TreeView (SfTreeView)

The TreeView provides various options to customize the height of items. To achieve this customization, please walkthrough the below sections:

## Customize Item Height

The TreeView allows customizing the height of items by setting the [ItemHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ItemHeight) property. The default value of this property is `40`. This property can be customized at runtime.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView" ItemHeight="40">
{% endhighlight %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.ItemHeight = 40; 
{% endhighlight %}
{% endtabs %}

## Customize Item height using `QueryNodeSize` event
 The TreeView allows customizing the height of the items using [QueryNodeSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) event. This event is raised whenever the item comes into view and triggered with [QueryNodeSizeEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html).

The `SfTreeView.QueryNodeSize` event provides the following arguments:
 
 * [Node](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_XForms_TreeView_QueryNodeSizeEventArgs_Node): This argument contains the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) and data associated with it.
 * [Height](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_XForms_TreeView_QueryNodeSizeEventArgs_Height): This argument contains the default item height of the queried item and can be set with desired size.
 * [Handled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_XForms_TreeView_QueryNodeSizeEventArgs_Handled): Decides whether the specified or measured height can be set to the item or not. The default value is `false`. When this property is not set, the decided height will not set to the item.
 * [GetActualNodeHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_XForms_TreeView_QueryNodeSizeEventArgs_GetActualNodeHeight): This method will return the measured height of the node item based on content loaded in it.

### Customize specific item height using custom value

The TreeView allows customizing the height of the specific item by setting the custom value directly to the [Height](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_XForms_TreeView_QueryNodeSizeEventArgs_Height) argument which is available in [QueryNodeSizeEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html).

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
    }
}
{% endhighlight %}
{% endtabs %}

### Customize specific item height based on the content size

The TreeView allows adjusting height of items based on the content measured size while loaded by setting the `Height` argument with value returned from [QueryNodeSizeEventArgs.GetActualNodeHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_XForms_TreeView_QueryNodeSizeEventArgs_GetActualNodeHeight) method.
                                             
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
        if (e.Node.Level != 0)
        {
            // Returns item height based on the content loaded.
            e.Height = e.GetActualNodeHeight();
            e.Handled = true;
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Autofit item height on dynamic changes

The Treeview supports autofit the item based on dynamic change in item size. It is enabled by setting [NodeSizeMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_NodeSizeMode) property to `NodeSizeMode.Dynamic`. The default value is `NodeSizeMode.None`.

* `None`: The item height does not autofit for dynamic changes.
* `Dynamic`: The item height responds for dynamic changes and the size is recalculated.

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

You can download the entire source code of this demo [here](https://github.com/SyncfusionExamples/Xamarin-TreeView-Item-Height-Customization).

![AutoFit items](TreeView_images/TreeView_AutoFit_Items.png)


## Limitations

 * Define the size of the image when loading image in the [SfTreeView.ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ItemTemplate). Because, it does not return actual measured size when measuring before item layout.
 
## See also

[How to AutoFit the nodes based on the content in Xamarin.Forms TreeView (SfTreeView)](https://www.syncfusion.com/kb/11418/)