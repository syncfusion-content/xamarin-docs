---
layout: post
title: View Appearance in SfListView
description: Describes about view appearance and different functionalities in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# View Appearance

SfListView lets you customize the appearance of the underlying data and provides different functionalities to the end-user.

## Defining the Item Template

A template can be used to present the data in a way that makes sense for your application by using different controls. SfListView lets you customize the appearance of view by setting the [ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html) property. In SfListView, by default a [SfLabel](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfLabel.html) is used to present the list of data.

## Defining the Item Size

SfListView allows you to customize the size of the items by setting the [ItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemSize.html) property. The default value of this property is 40. This property responds to runtime changes and hence you can customize it based on your requirement.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.ItemSize = 60;
{% endhighlight %}
{% endtabs %}

N> For Vertical orientation, the item size is considered as height and for Horizontal orientation, it will be considered as width.

## Set Spacing between Items

SfListView allows you to specify the spacing between each item in the list by setting the [ItemSpacing](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemSpacing.html) property. You can generate the space around the item. The default value of this property is 0. This property responds to runtime changes and hence you can customize it based on your requirement.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemSpacing="5,0,0,0" />
{% endhighlight %}
{% highlight c# %}
listView.ItemSpacing = new Thickness(5, 0, 0, 0)
{% endhighlight %}
{% endtabs %}

## Orientation

SfListView allows you to layout every item in the [SfListView.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemsSource.html) property in either vertical or horizontal orientation by setting [SfListView.Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Orientation.html). The default orientation is `Vertical`.

{% tabs %}
{% highlight xaml %}
<xmlns:sync="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">

<sync:SfListView x:Name="listView" Orientation="Horizontal" />
{% endhighlight %}
{% highlight c# %}
listView.Orientation = Orientation.Horizontal;
{% endhighlight %}
{% endtabs %}

![](SfListView_images/SfListView-Orientation.png)

## Events

### Loaded Event

The [Loaded Event](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Loaded_EV.html) event is raised when the SfListView is loaded in view for the first time.

{% highlight c# %}
listView.Loaded += ListView_Loaded;

private void ListView_Loaded(object sender, ListViewLoadedEventArgs e)
{
   listView.SelectedItems.Add(viewModel.Customers[2]);
}
{% endhighlight %}

### Tapped Event

The [ItemTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTapped_EV.html) event will be triggered whenever you tapped on the item. [ItemTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemTappedEventArgs.html) has the following members which provides the information for `ItemTapped` event.

* **ItemType** - Gets the type of the item on which you have tapped
* **ItemData** - The underlying data associated with the tapped item as its arguments
 
{% highlight c# %}
listView.ItemTapped += ListView_ItemTapped;

private void ListView_ItemTapped(object sender, Syncfusion.ListView.XForms.ItemTappedEventArgs e)
{
    if (e.ItemData == viewModel.InboxInfo[0])
      viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo);  
}
{% endhighlight %}

### ItemDoubleTapped Event

TThe [ItemDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDoubleTapped_EV.html) event will be triggered whenever you have double tapped on the item. [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDoubleTappedEventArgs.html) has the following members which provides the information for `ItemDoubleTapped` event.

* **ItemType** - Gets the type of the item on which you have double tapped
* **ItemData** - The underlying data associated with the double tapped item as its arguments

{% highlight c# %}
listView.ItemDoubleTapped += ListView_ItemDoubleTapped;

private void ListView_ItemDoubleTapped(object sender, ItemDoubleTappedEventArgs e)
{
    var listviewinboxinfo = new ListViewInboxInfo();
    listviewinboxinfo.Title = "Bryce Thomas";
    listviewinboxinfo.Subject = "Congratulations on the move!";
    viewModel.InboxInfo.Add(listviewinboxinfo);
}
{% endhighlight %}

### ItemHolding Event

The [ItemHolding](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemHolding_EV.html) event will be triggered whenever you have long pressed on the item. [ItemHoldingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemHoldingEventArgs.html) has the following members which provides the information for `ItemHolding` event.

* **ItemType** - Gets the type of the item on which you have long pressed.
* **ItemData** - The underlying data associated with the holding item as its arguments
 
{% highlight c# %}
listView.ItemHolding += ListView_ItemHolding;

private void ListView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
   if (e.ItemData == viewModel.InboxInfo[3])
      viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo);         
}
{% endhighlight %}