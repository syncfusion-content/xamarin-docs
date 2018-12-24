---
layout: post
title: On-Demand Loading | TreeView for Xamarin.Forms | Syncfusion
description: Describes about loading nodes on demand for TreeView.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Load on demand

TreeView allows you load [Nodes](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~Nodes.html) only when they are requested using Load on Demand(Lazy load). It helps to load the data in on-demand when end-user expands the node where user can load the child items from services.

## LoadOnDemandCommand

TreeView loads root level `Nodes` initially. When parent node is expanded, it requests to load the child nodes from the data source based on [LoadOnDemandCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~LoadOnDemandCommand.html).

While implementing `LoadOnDemandCommand`, implement these methods to handle it:
* [CanExecute](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand.canexecute?view=netframework-4.7.2) - Called when each item is initialized and defines whether load-on-demand feature is enabled for an item.
* [Execute](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand.execute?view=netframework-4.7.2) - Called when any item is requested for load-on-demand items.

N> Return true in `CanExecute` method of this command to enable expander icon and also to execute on demand loading for that node, else return false.

N> Load on demand is applicable for bound mode only.

## ShowExpanderAnimation

`TreeViewNode` exposes a [ShowExpanderAnimation](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode~ShowExpanderAnimation.html) to enable animation for expander while progressing On-demand loading by setting `true` when an item is requested for On-demand loading and return `false` when child items are loaded for the item.

## PopulateChildNodes

TreeView exposes [PopulateChildNodes](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode~PopulateChildNodes.html) method to load child nodes when we populate the child items using async and await.

{% endhighlight %}
{% highlight c# %}
//Execute method is called when each item is requested for load-on-demand items.
private void ExecuteOnDemandLoading(object obj)
{
    var node = obj as TreeViewNode;

    //Indicator enabled
    node.ShowExpanderAnimation = true;
       
    MusicInfo musicInfo = node.Content as MusicInfo;
    Device.BeginInvokeOnMainThread(async () =>
    {
        await Task.Delay(2000);
        var items = GetSubMenu(musicInfo.ID);

        // Populating nodes
        node.PopulateChildNodes(items);
        if (items.Count() > 0)
            node.IsExpanded = true;
            
        //Indicator disabled
        node.ShowExpanderAnimation = false;
    });
}
{% endhighlight %}
{% endtabs %}

Define a ViewModel class that implements [ICommand](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.7.2) and handle it by `CanExecute` and  `Execute` methods to check and execute on-demand loading.

{% endhighlight %}
{% highlight c# %} 

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

    // CanExecute method is called when each item is initialized and defines whether a load-on-demand feature is enabled for this item.
    private bool CanExecuteOnDemandLoading(object sender)
    {
        var hasChildNodes = ((sender as TreeViewNode).Content as MusicInfo).HasChildNodes;
        if (hasChildNodes)
        {
            if ((sender as TreeViewNode).ChildNodes.Count > 0)
                return false;
            else
                return true;
        }
        else
            return false;
    }

    //Execute method is called when each item is requested for load-on-demand items.
    private void ExecuteOnDemandLoading(object obj)
    {
        var node = obj as TreeViewNode;

        //Indicator enabled
        node.ShowExpanderAnimation = true;
        MusicInfo musicInfo = node.Content as MusicInfo;
        Device.BeginInvokeOnMainThread(async () =>
        {
            await Task.Delay(2000);
            var items = GetSubMenu(musicInfo.ID);

            // Populating nodes
            node.PopulateChildNodes(items);
            if (items.Count() > 0)
                node.IsExpanded = true;
            
            //Indicator disabled
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
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<ContentPage  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
              xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms">
    <ContentPage.Content>
        <sfTreeView:SfTreeView x:Name="treeView"
                               LoadOnDemandCommand="{Binding TreeViewOnDemandCommand}"
                               ItemsSource="{Binding Menu}" /> 
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% endtabs %}

You can download the entire [source code](https://github.com/SyncfusionExamples/How-to-load-data-on-demand-in-Xamarin.Forms-TreeView) here.

![Xamarin Forms TreeView with Load On-Demand](TreeView_images/LoadOnDemand-Xamarin-Forms-TreeView.gif)