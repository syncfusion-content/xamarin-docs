---
layout: post
title: Load On-demand | TreeView for Xamarin.Forms | Syncfusion
description: This topic explains about how to load the child nodes on demand for treeview in SfTreeView Xamarin.Forms
platform: xamarin
control: SfTreeView
documentation: ug
---

# Load on demand in Xamarin TreeView (SfTreeView)

TreeView allows you to load child items only when they are requested using Load on-demand(Lazy load). It helps to load the child items from services when end-user expands the node. Initially populate the root [Nodes](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_Nodes) by assigning [ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_ItemsSource) and then when any node is expanded, child items can be loaded using [LoadOnDemandCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_LoadOnDemandCommand). Load on-demand is applicable for bound mode only.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TreeView"
             xmlns:sfTreeView="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             x:Class="TreeView.MainPage">
    <ContentPage.BindingContext>
        <local:MusicInfoRepository x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <sfTreeView:SfTreeView x:Name="treeView"
                               LoadOnDemandCommand="{Binding TreeViewOnDemandCommand}"
                               ItemsSource="{Binding Menu}" /> 
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
/// <summary>
/// ViewModel class with <see cref="Command"/> for load on demand. 
/// </summary>
public class MusicInfoRepository
{
    private ObservableCollection<MusicInfo> menu;

    public ObservableCollection<MusicInfo> Menu
    {
        get { return menu; }
        set { menu = value; }
    }

    public ICommand TreeViewOnDemandCommand
    {
        get; set;
    }

    public MusicInfoRepository()
    {
        this.Menu = this.GetMenuItems();
        TreeViewOnDemandCommand = new Command(ExecuteOnDemandLoading, CanExecuteOnDemandLoading);
    }

    /// <summary>
    /// CanExecute method is called before expanding and initialization of node. Returns whether the node has child nodes or not.
    /// Based on return value, expander visibility of the node is handled.  
    /// </summary>
    /// <param name="sender">TreeViewNode is passed as default parameter </param>
    /// <returns>Returns true, if the specified node has child items to load and expander icon is displayed for that node, else returns false and icon is not displayed.</returns>
    private bool CanExecuteOnDemandLoading(object sender)
    {
        var hasChildNodes = ((sender as TreeViewNode).Content as MusicInfo).HasChildNodes;
        if (hasChildNodes)
            return true;
        else
            return false;
    }

    /// <summary>
    /// Execute method is called when any item is requested for load-on-demand items.
    /// </summary>
    /// <param name="obj">TreeViewNode is passed as default parameter </param>
    private void ExecuteOnDemandLoading(object obj)
    {
        var node = obj as TreeViewNode;
        
        // Skip the repeated population of child items when every time the node expands.
        if (node.ChildNodes.Count > 0)
        {
            node.IsExpanded = true;
            return;
        }

        //Animation starts for expander to show progressing of load on demand
        node.ShowExpanderAnimation = true;
        MusicInfo musicInfo = node.Content as MusicInfo;
        Device.BeginInvokeOnMainThread(async () =>
        {
            await Task.Delay(2000);
            
            //Fetching child items to add
            var items = GetSubMenu(musicInfo.ID);
            
            // Populating child items for the node in on-demand
            node.PopulateChildNodes(items);
            if (items.Count() > 0)
                //Expand the node after child items are added.
                node.IsExpanded = true;

            //Stop the animation after load on demand is executed, if animation not stopped, it remains still after execution of load on demand.
            node.ShowExpanderAnimation = false;
        });
    }

    private ObservableCollection<MusicInfo> GetMenuItems()
    {
        ObservableCollection<MusicInfo> menuItems = new ObservableCollection<MusicInfo>();
        menuItems.Add(new MusicInfo() { ItemName = "Discover Music", HasChildNodes = true, ID = 1 });
        menuItems.Add(new MusicInfo() { ItemName = "Sales and Events", HasChildNodes = true, ID = 2 });
        menuItems.Add(new MusicInfo() { ItemName = "Categories", HasChildNodes = true, ID = 3 });
        menuItems.Add(new MusicInfo() { ItemName = "MP3 Albums", HasChildNodes = true, ID = 4 });
        menuItems.Add(new MusicInfo() { ItemName = "Fiction Book Lists", HasChildNodes = true, ID = 5 });
        return menuItems;
    }

    public IEnumerable<MusicInfo> GetSubMenu(int iD)
    {
        ObservableCollection<MusicInfo> menuItems = new ObservableCollection<MusicInfo>();
        if (iD == 1)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Hot Singles", HasChildNodes = false, ID = 11 });
            menuItems.Add(new MusicInfo() { ItemName = "Rising Artists", HasChildNodes = false, ID = 12 });
            menuItems.Add(new MusicInfo() { ItemName = "Live Music", HasChildNodes = false, ID = 13 });
            menuItems.Add(new MusicInfo() { ItemName = "More in Music", HasChildNodes = true, ID = 14 });
        }
        else if (iD == 2)
        {
            menuItems.Add(new MusicInfo() { ItemName = "100 Albums - $10 Each", HasChildNodes = false, ID = 21 });
            menuItems.Add(new MusicInfo() { ItemName = "Hip-Hop and R&B Sale", HasChildNodes = false, ID = 22 });
            menuItems.Add(new MusicInfo() { ItemName = "CD Deals", HasChildNodes = false, ID = 23 });
        }
        else if (iD == 3)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Songs", HasChildNodes = false, ID = 31 });
            menuItems.Add(new MusicInfo() { ItemName = "Bestselling Albums", HasChildNodes = false, ID = 32 });
            menuItems.Add(new MusicInfo() { ItemName = "New Releases", HasChildNodes = false, ID = 33 });
            menuItems.Add(new MusicInfo() { ItemName = "MP3 Albums", HasChildNodes = false, ID = 34 });
        }
        else if (iD == 4)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Rock Music", HasChildNodes = false, ID = 41 });
            menuItems.Add(new MusicInfo() { ItemName = "Gospel", HasChildNodes = false, ID = 42 });
            menuItems.Add(new MusicInfo() { ItemName = "Latin Music", HasChildNodes = false, ID = 43 });
            menuItems.Add(new MusicInfo() { ItemName = "Jazz", HasChildNodes = false, ID = 44 });
        }
        else if (iD == 5)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Hunger Games", HasChildNodes = false, ID = 51 });
            menuItems.Add(new MusicInfo() { ItemName = "Pride and Prejudice", HasChildNodes = false, ID = 52 });
            menuItems.Add(new MusicInfo() { ItemName = "Harry Potter", HasChildNodes = false, ID = 53 });
            menuItems.Add(new MusicInfo() { ItemName = "Game Of Thrones", HasChildNodes = false, ID = 54 });
        }
        else if (iD == 14)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Music Trade-In", HasChildNodes = false, ID = 141 });
            menuItems.Add(new MusicInfo() { ItemName = "Redeem a Gift card", HasChildNodes = false, ID = 142 });
            menuItems.Add(new MusicInfo() { ItemName = "Band T-Shirts", HasChildNodes = false, ID = 143 });
        }
        return menuItems;
    }
}
{% endhighlight %}
{% highlight c# %}
/// <summary>
/// Model
/// </summary>
public class MusicInfo : INotifyPropertyChanged
{
    public string itemName;
    public int id;
    public bool hasChildNodes;

    public string ItemName
    {
        get { return itemName; }
        set
        {
            itemName = value;
            OnPropertyChanged("ItemName");
        }
    }

    public int ID
    {
        get { return id; }
        set
        {
            id = value;
            OnPropertyChanged("ID");
        }
    }

    public bool HasChildNodes
    {
        get { return hasChildNodes; }
        set
        {
            hasChildNodes = value;
            OnPropertyChanged("HasChildNodes");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    private void OnPropertyChanged(string propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
}

{% endhighlight %}
{% endtabs %}

N> `LoadOnDemandCommand` receives [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) as command parameter by default. 

## Handling expander visibility

TreeView shows the expander for a particular node based on return value of [CanExecute](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.command.canexecute?view=xamarin-forms#Xamarin_Forms_Command_CanExecute_System_Object_) method of [LoadOnDemandCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_LoadOnDemandCommand). If `CanExecute` returns `true`, then expander icon is displayed for that node. If `CanExecute` returns `false`, then expander icon will not displayed for that node. `CanExecute` method gets called to decide the visibility of expander icon and before executing `LoadOnDemandCommand`. 

{% tabs %}
{% highlight c# %}

/// <summary>
/// CanExecute method is called before expanding and initialization of node. Returns whether the node has child nodes or not.
/// Based on return value of expander visibility of the node is handled.  
/// </summary>
/// <param name="sender">TreeViewNode is passed as default parameter </param>
/// <returns>Returns true, if the specified node has child items to load and expander icon is displayed for that node, else returns false and icon is not displayed.</returns>
private bool CanExecuteOnDemandLoading(object sender)
{
    var hasChildNodes = ((sender as TreeViewNode).Content as MusicInfo).HasChildNodes;
    if (hasChildNodes)
        return true;
    else
        return false;
}
{% endhighlight %}
{% endtabs %}

## On-demand loading of child items

You can load child items for the node in [Execute](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.command.execute?view=xamarin-forms#Xamarin_Forms_Command_Execute_System_Object_) method of `LoadOnDemandCommand`. Execute method will get called when user expands the tree node. In `LoadOnDemand.Execute` method, you have can perform following operations,

* Show or hide busy indicator in the place of expander by setting [TreeViewNode.ShowExpanderAnimation](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_ShowExpanderAnimation) until the data fetched.
* Once data fetched, you can populate the child nodes by calling [TreeViewNode.PopulateChildNodes](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_PopulateChildNodes_System_Collections_IEnumerable_) method by passing the child items collection. 
* When load on-demand command executes expanding operation will not be handled by `TreeView`. So, you have to set [TreeViewNode.IsExpanded](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsExpanded) property to `true` to expand the tree node after populating child nodes.
* You can skip population of child items again and again when every time the node expands, based on [TreeViewNode.ChildNodes](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_ChildNodes) count. 
* You can get the number of child nodes displayed in the view by using the [TreeViewNode.VisibleNodesCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_VisibleNodesCount) property.
* The child nodes of the TreeView node can be notified based upon the return value of the [HasChildNodes](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_HasChildNodes) property. If the node has any child nodes, it returns as `true` or it returns as `false`.

{% tabs %}
{% highlight c# %}

/// <summary>
/// Execute method is called when any item is requested for load-on-demand items.
/// </summary>
/// <param name="obj">TreeViewNode is passed as default parameter </param>
private void ExecuteOnDemandLoading(object obj)
{
    var node = obj as TreeViewNode;
        
    // Skip the repeated population of child items when every time the node expands.
    if (node.ChildNodes.Count > 0)
    {
        node.IsExpanded = true;
        return;
    }

    /// <summary>
    /// CanExecute method is called before expanding and initialization of node. Returns whether the node has child nodes or not.
    /// Based on return value, expander visibility of the node is handled.  
    /// </summary>
    /// <param name="sender">TreeViewNode is passed as default parameter </param>
    /// <returns>Returns true, if the specified node has child items to load on demand and expander icon is displayed for that node, else returns false and icon is not displayed.</returns>
    private bool CanExecuteOnDemandLoading(object sender)
    {
        var hasChildNodes = ((sender as TreeViewNode).Content as MusicInfo).HasChildNodes;
        if (hasChildNodes)
            return true;
        else
            return false;
    }

    //Animation starts for expander to show progressing of load on demand
    node.ShowExpanderAnimation = true;
    MusicInfo musicInfo = node.Content as MusicInfo;
    Device.BeginInvokeOnMainThread(async () =>
    {
        await Task.Delay(2000);
        
        //Fetching child items to add
        var items = GetSubMenu(musicInfo.ID);
        
        // Populating child items for the node in on-demand
        node.PopulateChildNodes(items);
        if (items.Count() > 0)
            //Expand the node after child items are added.
            node.IsExpanded = true;
			
            //Get the VisibleNodesCount
			var count = node.VisibleNodesCount;

        //Stop the animation after load on demand is executed, if animation not stopped, it remains still after execution of load on demand.
        node.ShowExpanderAnimation = false;
    });   
}
{% endhighlight %}
{% endtabs %}

You can download the entire [source code](https://github.com/SyncfusionExamples/How-to-load-data-on-demand-in-Xamarin.Forms-TreeView) here.

![Xamarin Forms TreeView with Load On-Demand](TreeView_images/LoadOnDemand-Xamarin-Forms-TreeView.gif)