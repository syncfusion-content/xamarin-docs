---
layout: post
title: Working with SfListView
description: Describes about different functionalities and events in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

## Launching the SfListView inside the StackLayout

When you load SfListView inside the StackLayout, you should set the HorizontalOptions and VerticalOptions to the StackLayout as “LayoutOptions.FillAndExpand” because, the StackLayout positions the child element one after the other, either horizontally or vertically based on the orientation of StackLayout. The size of the StackLayout depends on how the HorizontalOptions and VerticalOptions properties are set, but by default the StackLayout will try to use the entire screen. 

{% highlight xaml %}
<StackLayout VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">
    <sync:SfListView x:Name="listView" ItemsSource="{Binding BookInfo}" /> 
</StackLayout>
{% endhighlight %}

### Load the SfListView inside a ScrollView in the StackLayout

When the SfListView is loaded inside a ScrollView or any layout such as Grid, StackLayout etc., into the StackLayout. You should set the “VerticalOptions” and “HorizontalOptions” of the SfListView's immediate parent as “LayoutOptions.FillAndExpand”.

{% highlight xaml %}
<StackLayout>
  <ScrollView VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">
    <sync:SfListView x:Name="listView" ItemsSource="{Binding BookInfo}" /> 
  </ScrollView> 
</StackLayout>
{% endhighlight %}

## Programmatic Scrolling

### Scroll to Row Index

SfListView allows you to scroll programmatically to a row based on index by using [ScrollToRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LinearLayout~ScrollToRowIndex.html) method.

{% highlight c# %}

(listView.LayoutManager as LinearLayout).ScrollToRowIndex(50);   

{% endhighlight %}

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

The [ItemTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTapped_EV.html) event will be triggered whenever you have tapped on the item. [ItemTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemTappedEventArgs.html) has the following members which provides the information for `ItemTapped` event.

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