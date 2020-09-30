---
layout: post
title: TreeView Checkbox | TreeNode Checkbox | Xamarin.Forms | Syncfusion
description: The Xamarin.Forms TreeView provides support for loading Checkbox in each node and allows users to check/uncheck the corresponding node.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Checkbox in Xamarin TreeView (SfTreeView)

SfTreeView provides support for loading [CheckBox](https://help.syncfusion.com/xamarin/checkbox/getting-started) in each node, and allows users to check/uncheck the corresponding node. So, you should add checkbox in the [ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ItemTemplate) of the `SfTreeView` and bind the [IsChecked](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsChecked) property of the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html).

## Working with Checkbox in BoundMode

When you are populating treeview nodes from [ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ItemsSource), then you can get or set the checked items by using [CheckedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CheckedItems) property.

SfTreeView supports to check multiple items through binding the [CheckedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CheckedItems) property from view model with `ObservableCollection<object>` type.

N> Set [ItemTemplateContextType](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ItemTemplateContextType) as `Node` to bind the `TreeViewNode.IsChecked` property to `CheckBox` in `ItemTemplate`. To know more about `ItemTemplateContextType` click [here](https://help.syncfusion.com/xamarin/treeview/appearance#bindingcontext-for-itemtemplate). 

N> TreeView process and sets [TreeViewNode.IsChecked]((https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsChecked)) based on `CheckedItems` only when you are binding `ItemsSource`.

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
                         AutoExpandMode="RootNodesExpanded"
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
{% highlight c# %}
public class FileManagerViewModel
{
    private ObservableCollection<object> checkedItems;

    public ObservableCollection<object> CheckedItems
    {
        get { return checkedItems; }
        set { this.checkedItems = value; }
    }

    public ObservableCollection<Folder> Folders { get; set; }

    public FileManagerViewModel()
    {
        this.Folders = GetFiles();
    }

    private ObservableCollection<Folder> GetFiles()
    {
        var nodeImageInfo = new ObservableCollection<Folder>();
        Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly;

        var doc = new Folder() { FileName = "Documents"};
        var download = new Folder() { FileName = "Downloads",};
        var mp3 = new Folder() { FileName = "Music"};
        var pictures = new Folder() { FileName = "Pictures"};
        var video = new Folder() { FileName = "Videos"};

        var pollution = new File() { FileName = "Environmental Pollution.docx"};
        var globalWarming = new File() { FileName = "Global Warming.ppt"};

        var games = new File() { FileName = "Game.exe"};
        var tutorials = new File() { FileName = "Tutorials.zip"};
        var TypeScript = new File() { FileName = "TypeScript.7z"};
        var uiGuide = new File() { FileName = "UI-Guide.pdf"};

        var song = new File() { FileName = "Gouts"};

        var camera = new File() { FileName = "Camera Roll"};
        var stone = new File() { FileName = "Stone.jpg"};
        var wind = new File() { FileName = "Wind.jpg"};

        var img0 = new SubFile() { FileName = "WIN_20160726_094117.JPG"};
        var img1 = new SubFile() { FileName = "WIN_20160726_094118.JPG"};

        var video1 = new File() { FileName = "Naturals.mp4"};
        var video2 = new File() { FileName = "Wild.mpg"};

        doc.Files = new ObservableCollection<File>
            {
                pollution,
                globalWarming
            };

        download.Files = new ObservableCollection<File>
            {
                games,
                tutorials,
                TypeScript,
                uiGuide
            };

        mp3.Files = new ObservableCollection<File>
            {
                song
            };

        pictures.Files = new ObservableCollection<File>
            {
                camera,
                stone,
                wind
            };
        camera.SubFiles = new ObservableCollection<SubFile>
            {
                img0,
                img1
            };

        video.Files = new ObservableCollection<File>
            {
                video1,
                video2
            };

        nodeImageInfo.Add(doc);
        nodeImageInfo.Add(download);
        nodeImageInfo.Add(mp3);
        nodeImageInfo.Add(pictures);
        nodeImageInfo.Add(video);

        checkedItems = new ObservableCollection<object>();
        checkedItems.Add(doc);
        checkedItems.Add(TypeScript);
        checkedItems.Add(uiGuide);
        checkedItems.Add(stone);
        checkedItems.Add(wind);
        checkedItems.Add(song);

        return nodeImageInfo;
    }
}
{% endhighlight %}
{% endtabs %}

![Xamarin Forms BoundMode TreeView with CheckBox](TreeView_images/BoundMode_CheckBox.png)

You can download the entire source of this demo from [here](https://github.com/SyncfusionExamples/checkbox_bound_mode)

## Working with Checkbox in UnboundMode

You can directly set the checkbox state by setting the [TreeViewNode.IsChecked](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsChecked) property value while creating nodes.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:UnboundMode_Checkbox"
             x:Class="UnboundMode_Checkbox.MainPage"
             xmlns:treeviewengine="clr-namespace:Syncfusion.TreeView.Engine;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:SfCheckBox="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms">

    <ContentPage.Content>
        <syncfusion:SfTreeView CheckBoxMode="Recursive">
            <syncfusion:SfTreeView.Nodes>
                <treeviewengine:TreeViewNode Content="Australia" IsChecked="True" IsExpanded="True">
                    <treeviewengine:TreeViewNode.ChildNodes>
                        <treeviewengine:TreeViewNode x:Name="newSouthWales" Content="New South Wales">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="Sydney"/>
                                <treeviewengine:TreeViewNode Content="New York">
                                    <treeviewengine:TreeViewNode.ChildNodes>
                                        <treeviewengine:TreeViewNode Content="San Francisco"/>
                                    </treeviewengine:TreeViewNode.ChildNodes>
                                </treeviewengine:TreeViewNode>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                        <treeviewengine:TreeViewNode Content="United States of America">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="New York">
                                    <treeviewengine:TreeViewNode.ChildNodes>
                                        <treeviewengine:TreeViewNode Content="San Francisco"/>
                                    </treeviewengine:TreeViewNode.ChildNodes>
                                </treeviewengine:TreeViewNode>
                                <treeviewengine:TreeViewNode Content="California">
                                    <treeviewengine:TreeViewNode.ChildNodes>
                                        <treeviewengine:TreeViewNode Content="San Francisco"/>
                                    </treeviewengine:TreeViewNode.ChildNodes>
                                </treeviewengine:TreeViewNode>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                        <treeviewengine:TreeViewNode Content="New South Wales" IsChecked="True">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="Sydney"/>
                                <treeviewengine:TreeViewNode Content="New York">
                                    <treeviewengine:TreeViewNode.ChildNodes>
                                        <treeviewengine:TreeViewNode Content="San Francisco"/>
                                    </treeviewengine:TreeViewNode.ChildNodes>
                                </treeviewengine:TreeViewNode>

                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                        <treeviewengine:TreeViewNode Content="United States of America" IsChecked="True">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="New York">
                                    <treeviewengine:TreeViewNode.ChildNodes>
                                        <treeviewengine:TreeViewNode Content="San Francisco"/>
                                    </treeviewengine:TreeViewNode.ChildNodes>
                                </treeviewengine:TreeViewNode>
                                <treeviewengine:TreeViewNode Content="California">
                                    <treeviewengine:TreeViewNode.ChildNodes>
                                        <treeviewengine:TreeViewNode Content="San Francisco"/>
                                    </treeviewengine:TreeViewNode.ChildNodes>
                                </treeviewengine:TreeViewNode>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                    </treeviewengine:TreeViewNode.ChildNodes>
                </treeviewengine:TreeViewNode>
                <treeviewengine:TreeViewNode x:Name="America" Content="United States of America">
                    <treeviewengine:TreeViewNode.ChildNodes>
                        <treeviewengine:TreeViewNode Content="New York"/>
                        <treeviewengine:TreeViewNode Content="California">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="San Francisco"/>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                    </treeviewengine:TreeViewNode.ChildNodes>
                </treeviewengine:TreeViewNode>
                <treeviewengine:TreeViewNode x:Name="India" Content="India">
                    <treeviewengine:TreeViewNode.ChildNodes>
                        <treeviewengine:TreeViewNode Content="TamilNadu">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="Chennai"/>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                    </treeviewengine:TreeViewNode.ChildNodes>
                </treeviewengine:TreeViewNode>
                <treeviewengine:TreeViewNode Content="United Arab Emirates">
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

![Xamarin Forms UnboundMode TreeView with CheckBox](TreeView_images/UnboundMode_CheckBox.png)

You can download the entire source of this demo [here](https://github.com/SyncfusionExamples/checkbox_unbound_mode)

## CheckBox State

SfTreeView process [IsChecked]((https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsChecked)) property (checkbox state) of `TreeViewNode` based on [CheckBoxMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CheckBoxMode) property. `CheckBoxMode` defines how parent and child node's checkbox state updates when user check or un-check the node. By default, its value is `None`. Checkbox contains the following three states:

* `None`: Check and uncheck are updates only in the view, but it will not affect the CheckedItems collection.
* `Individual`: Checkbox state affect individual node only, and it does not affect the parent node or child nodes checkbox state or `IsChecked` property value.
* `Recursive`: Check and uncheck the node value affects the parent and child nodes checkbox state. For example, If parent nodes checkbox state is check/uncheck then the all of its child nodes checkbox state is check/uncheck. If all the child nodes are check/uncheck within the parent node, then parent node will be check/uncheck. If any of the child node is check, then the parent node will be in intermediate state.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="TreeView" CheckBoxMode="Recursive"/>
{% endhighlight %}
{% highlight c# %}
TreeView.CheckBoxMode = CheckBoxMode.Recursive;
{% endhighlight %}
{% endtabs %}

N> In recursive mode, the parent nodes checkbox state or `IsChecked` property value is updated only in UI interaction.

N> When the `CheckBoxMode` is enabled, the `ItemTapped` and `ItemDoubleTapped` event will not be triggered in `SfTreeView` since the `CheckBox` will handle the touch interaction, only the `NodeChecked` event is triggered

## Get or Set Checked Items

### Get or Set Checked Items in Bound Mode

You can get or set list of items to be checked or un-checked by using [CheckedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CheckedItems) property.

When the [CheckBoxMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CheckBoxMode) is other than `None`, the individual `TreeViewNode` or collection of `TreeViewNode` can be checked from the code by setting the  `CheckedItems`, or adding items to the `CheckedItems` property based on the `CheckBoxMode`.

N> Programmatically adding or removing the node value not affects their parent and child nodes checkbox state.

{% tabs %}
{% highlight c# %}

treeView.CheckedItems.Add(viewModel.Folders[2]);
treeView.CheckedItems.Add(viewModel.Folders[3]);

{% endhighlight %}
{% endtabs %}

### Get or Set Checked Nodes in Unbound Mode

You can get the list of checked nodes by using [GetCheckedNodes](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_GetCheckedNodes) method. You can set checkbox state by setting [TreeViewNode.IsChecked](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsChecked) property.

{% tabs %}
{% highlight c# %}
treeView.GetCheckedNodes();
{% endhighlight %}
{% endtabs %}

## Events

### NodeChecked event

The [NodeChecked](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html) event raised when checking and unchecking the checkbox at run time. The [NodeCheckedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.NodeCheckedEventArgs.html) has the following members, which provide information for the `NodeChecked` event.

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
