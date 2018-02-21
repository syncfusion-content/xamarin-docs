---
layout: post
title: Tab Items
description: About Tab items in TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Tab Items

Tab items can be configured in tab view through the Items property of `SfTabView`, where it holds collection of `SfTabItem` through `TabItemsCollection`


{% tabs %}

{% highlight xaml %}

<tabView:SfTabView >
    <tabView:SfTabItem Title="Call">
        <tabView:SfTabItem.Content>
            <Grid BackgroundColor="Red" x:Name="AllContactsGrid" />
        </tabView:SfTabItem.Content>
    </tabView:SfTabItem>
    <tabView:SfTabItem Title="Favorites">
        <tabView:SfTabItem.Content>
            <Grid BackgroundColor="Green" x:Name="FavoritesGrid" />
        </tabView:SfTabItem.Content>
    </tabView:SfTabItem>
    <tabView:SfTabItem Title="Contacts">
        <tabView:SfTabItem.Content>
            <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
        </tabView:SfTabItem.Content>
    </tabView:SfTabItem>
</tabView:SfTabView>

{% endhighlight %}

{% highlight C# %}

var tabView = new SfTabView();
var allContactsGrid = new Grid {BackgroundColor = Color.Red};
var favoritesGrid = new Grid {BackgroundColor = Color.Green};
var contactsGrid = new Grid {BackgroundColor = Color.Blue};
var tabItems = new TabItemCollection
{
	new SfTabItem()
	{
    Title = "Calls",
    Content = allContactsGrid
	},
	new SfTabItem()
	{
    Title = "Favorites",
    Content = favoritesGrid
	},
	new SfTabItem()
	{
    Title = "Contacts",
    Content = contactsGrid
	}
};

tabView.Items = tabItems;
this.Content = tabView;

{% endhighlight %}

{% endtabs %}

## Share the header space equally

In order to share the header space equally for the , we can set the number of tabs which can be distributed in the available space though `VisibleHeaderCount` of SfTabView.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView VisibleHeaderCount="3" >
	
{% endhighlight %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}


