---
layout: post
title: OnDemandLoading | TreeView for Xamarin.Forms | Syncfusion
description: Describes about loading nodes on demand for TreeView.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Load on demand

Load on demand is a technique (Lazy load) that is used to reduce the bandwidth size of consuming huge data. You can load data on demand in `TreeView` by using `LoadOnDemandCommand` when you’re going to use huge data.

TreeView loads root level [Nodes](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~Nodes.html)  initially, and when parent node is expanded, loads the child nodes from the data source. It reduces the time to render TreeView with huge data.

To enable the load on demand feature, you would need to use the `LoadOnDemandCommand`  of `TreeView` as demonstrated in the example below:

Create a ViewModel which contains the root items of the TreeView. You would also need to create a `Command` for handling the load on command and bind to `LoadOnDemandCommand`.

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

    private void ExecuteOnDemandLoading(object obj)
    {
        var node = obj as TreeViewNode;
        node.ShowExpanderAnimation = true;
        MusicInfo musicInfo = node.Content as MusicInfo;
        Device.BeginInvokeOnMainThread(async () =>
        {
            await Task.Delay(2000);
            var items = GetSubMenu(musicInfo.ID);
            node.PopulateChildNodes(items);
            if (items.Count() > 0)
                node.IsExpanded = true;
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

CanExecuteOnDemandLoading method is called when each item is initialized and defines whether a load-on-demand feature is enabled for this item.

{% tabs %}
{% highlight xaml %}
<sfTreeView:SfTreeView x:Name="treeView"
                       LoadOnDemandCommand="{Binding TreeViewOnDemandCommand}"
                       ExpandActionTarget="Node"
                       ItemsSource="{Binding Menu}" />
{% endhighlight %}
{% endtabs %}

You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/OnDemandLoading583866000).

![Xamarin Forms TreeView with OnDemandLoading](TreeView_images/TreeView_OnDemmadn.gif)