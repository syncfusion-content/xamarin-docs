---
layout: post
title: Node Checkbox | TreeView for Xamarin.Forms | Syncfusion
description: Describes CheckBox features of TreeView.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Checkbox

SfTreeView provides support for loading [CheckBox](https://help.syncfusion.com/xamarin/sfcheckbox/getting-started) in each node, and allows users check/uncheck the corresponding node. There is no built-in support to enable or disable the check box. So, you should add checkbox in the `ItemTemplate` of the `SfTreeView` and bind the `IsChecked` property of the node.

## Checkbox in BoundMode

Set `ItemTemplateContextType` to Node for bound mode to use check box in SfTreeView.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:BoundMode_CheckBox"
             x:Class="BoundMode_CheckBox.MainPage"
             xmlns:TreeView="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:SfButtons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             xmlns:TreeViewEngine="clr-namespace:Syncfusion.TreeView.Engine;assembly=Syncfusion.SfTreeView.XForms">

    <ContentPage.BindingContext>
        <local:FileManagerViewModel />
    </ContentPage.BindingContext>

    <TreeView:SfTreeView x:Name="SfTreeView"
                         ItemsSource="{Binding Folders}"
                         ItemTemplateContextType="Node"
                         CheckBoxMode="Recursive"
                         CheckedItems="{Binding CheckedItems}">
        
        <TreeView:SfTreeView.HierarchyPropertyDescriptors>
            <TreeViewEngine:HierarchyPropertyDescriptor TargetType="{x:Type local:Folder}" ChildPropertyName="Files"/>
            <TreeViewEngine:HierarchyPropertyDescriptor TargetType="{x:Type local:File}" ChildPropertyName="SubFiles"/>
        </TreeView:SfTreeView.HierarchyPropertyDescriptors>
        
        <TreeView:SfTreeView.ItemTemplate>
            <DataTemplate>
                <ViewCell>
                    <ViewCell.View>
                        <Grid Padding="5">
                            <SfButtons:SfCheckBox 
                            x:Name="CheckBox"
                            Text="{Binding Content.FileName}"
                            IsChecked="{Binding IsChecked, Mode=TwoWay}"/>
                        </Grid>
                    </ViewCell.View>
                </ViewCell>
            </DataTemplate>
        </TreeView:SfTreeView.ItemTemplate>
    </TreeView:SfTreeView>
</ContentPage>
{% endhighlight %}
{% endtabs %}

You can download the entire source of this demo [here](https://github.com/SyncfusionExamples/checkbox_bound_mode)

## Checkbox in UnBoundMode

you can directly set the IsChecked property when creating nodes.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:UnBoundMode_CheckBox"
             x:Class="UnBoundMode_CheckBox.MainPage"
             xmlns:treeviewengine="clr-namespace:Syncfusion.TreeView.Engine;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:SfCheckBox="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms">

    <ContentPage.Content>
            <syncfusion:SfTreeView CheckBoxMode="Recursive">
            <syncfusion:SfTreeView.Nodes>
                <treeviewengine:TreeViewNode Content="United Arab Emirates" IsChecked="True" IsExpanded="True">
                    <treeviewengine:TreeViewNode.ChildNodes>
                        <treeviewengine:TreeViewNode Content="Abu Dhabi"/>
                        <treeviewengine:TreeViewNode Content="Dubai">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="Burj Khalifa"/>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                    </treeviewengine:TreeViewNode.ChildNodes>
                </treeviewengine:TreeViewNode>
            </syncfusion:SfTreeView.Nodes>
                
            <syncfusion:SfTreeView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                        <ViewCell.View>
                            <Grid Padding="5">
                                <SfCheckBox:SfCheckBox 
                                    Text="{Binding Content}"
                                    IsChecked="{Binding IsChecked, Mode=TwoWay}" />
                            </Grid>
                        </ViewCell.View>
                        </ViewCell>
                    </DataTemplate>
                </syncfusion:SfTreeView.ItemTemplate>
            </syncfusion:SfTreeView>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% endtabs %}

You can download the entire source of this demo [here](https://github.com/SyncfusionExamples/checkbox_unbound_mode)

![Xamarin Forms TreeView with CheckBox](TreeView_images/checkbox.png)

## CheckBox state

SfTreeView also provides support to process the selection state of the checkbox based on the [CheckBoxMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~CheckBoxMode.html) property. By default, its value is `None`.
Check box contains the following three states:

* `None`: Check and uncheck are updated in view, but it will not affect the CheckedItems collection.
* `Individual`: CheckBox state affects individual node only, and it does not affect the parent node property value.
* `Recursive`: CheckBox state of the child nodes affect the parent node property value. If all the child nodes are checked within the parent node, then parent node will be checked. If all the child nodes are not checked, then the parent node will not be checked. If any of the child node is checked, then the parent node will be in intermediate state.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="TreeView" CheckBoxMode="Recursive"/>
{% endhighlight %}
{% highlight c# %}
TreeView.CheckBoxMode = CheckBoxMode.Recursive;
{% endhighlight %}
{% endtabs %}

N> In recursive mode, the parent nodes checked property is updated only in UI interaction.

## Events

### NodeChecked event

The [NodeChecked](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeChecked_EV.html) event raised when checking and unchecking the check box at run time. The [NodeCheckedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.NodeCheckedEventArgs.html) has the following members, which provide information for the `NodeChecked` event.

* `Node`: Gets the `TreeViewNode` and data associated with the checked item as its arguments.

{% tabs %}
{% highlight c# %}
treeView.NodeChecked += TreeView_NodeChecked;

private void TreeView_NodeChecked(object sender, Syncfusion.XForms.TreeView.NodeCheckedEventArgs e)
{
     
}
{% endhighlight %}
{% endtabs %}

N> `NodeChecked` event occurs only in UI interactions.

## Method

### GetCheckedNodes

Gets all the checked nodes in tree view. When binding `ItemsSource`, you can get the checked nodes list using [CheckedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~CheckedItems.html).

{% tabs %}
{% highlight c# %}
treeView.GetCheckedNodes();
{% endhighlight %}
{% endtabs %}