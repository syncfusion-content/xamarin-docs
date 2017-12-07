---
layout: post
title: Working with SfListView
description: Describes about different functionalities and events in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

## Launching the SfListView inside the StackLayout

When you load SfListView inside the StackLayout, you should set the `HorizontalOptions` and `VerticalOptions` of the StackLayout as `LayoutOptions.FillAndExpand`.
Because, the StackLayout positions the child element one after the other, either horizontally or vertically based on the orientation of StackLayout. The size of the StackLayout depends on how the HorizontalOptions and VerticalOptions properties are set, but by default, the StackLayout will try to use the entire screen. 

{% highlight xaml %}
<StackLayout VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">
  <syncfusion:SfListView x:Name="listView" ItemsSource="{Binding BookInfo}" />
</StackLayout>
{% endhighlight %}

### Load the SfListView inside a ScrollView within StackLayout

When the SfListView is loaded inside a ScrollView or any layout such as Grid, StackLayout etc., into the StackLayout. You should set the `VerticalOptions` and `HorizontalOptions` of the SfListView's immediate parent as `LayoutOptions.FillAndExpand`.

{% highlight xaml %}
<StackLayout>
  <ScrollView VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">
    <syncfusion:SfListView x:Name="listView" ItemsSource="{Binding BookInfo}" />
  </ScrollView>
</StackLayout>
{% endhighlight %}

## Load the SfListView inside a SfPullToRefresh
SfPullToRefresh is a refresh control that allows you to interact and refresh the view loaded in it. When the SfListView is loaded inside the SfPullToRefresh, it is used to refresh the item while performing the pull to refresh action. The steps to be followed to load the SfListView inside SfPullToRefresh is explained in SfPullToRefresh Property Customization tab.

The final output will look like on iOS, Android and Windows Phone devices as shown below.

![](SfListView_images/SfListView_SlideOnTop-Xamarin.forms.gif)

## Load the SfListView in CarouselView

When the SfListView is loaded in CarouselView with [SfListView.AllowSwiping](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AllowSwiping.html) as false, SfListView will behave like below in UWP platform. 
 
* While performing first swipe on the view, it will handled by SfListView’s ScrollView itself to ensure whether scrolling is happened or not. If not, we are unable to pass manipulation to parent immediately due to UWP platform behavior and on second swipe will be listened by CarouselView and the view gets swiped. This is the behavior of SfListView. 
  
When SfListView is loaded in CarouselView with `SfListView.AllowSwiping` as true, SfListView will behave like below.  
 
* In iOS, when swipe suddenly carousel swipe is happened. If want to swipe ListViewItem, touch and hold on a item for some fraction of second (0.25 - 0.5 seconds) and then swipe. 
* When swipe on any Item, SfListView handles the touch and swipe the ListViewItem.  
* After swiped on ListViewItem, SwipeView is loaded along with ListViewItem. Then, if swipe on SwipeView element, Carousel view is swiped. Else, swipe on ListViewItem, SfListView handles touch and swipe the item as usual. 
* If swipe on Header, Footer or Group Header elements, Carousel view is swiped in Android platform. But in UWP, first swipe on those elements will handled by SfListView itself, since unable to pass Manipulation to parent immediately and then second swipe will be listened by CarouselView.

## Programmatic Scrolling

### Scroll to Row Index

SfListView allows you to scroll programmatically to a row based on index by using [ScrollToRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LayoutBase~ScrollToRowIndex.html) method for both linear and grid layouts. Also, provided support to enable and disable the scrolling animation while changing the view. By default, the scrolling will be animated.

N> If grouping is enabled, you can get the desired row index by passing the underlying data in [DisplayItems.IndexOf](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DisplayItems~IndexOf.html) method.

{% highlight c# %}

int index = listView.DataSource.DisplayItems.IndexOf(viewModel.Customers[2]); 
listView.LayoutManager.ScrollToRowIndex(index, true); 

{% endhighlight %}

#### Limitation in Scroll to Row Index

* When [AutoFitMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AutoFitMode.html) is `Height` or grouping is enabled, scroll animation will be disabled by default in android and iOS platforms. 
* If [ScrollToRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LayoutBase~ScrollToRowIndex.html) method is called while loading the `SfListView`, then set `disableAnimation` as `true` to scroll to appropriate row index, else view doesn't scrolled in android.

## Identifying the Scroll state changes

SfListView will notify the scrolling state changes by using [ScrollStateChanged](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ScrollStateChanged_EV.html) event.

Following states will be notified via [ScrollState](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ScrollState.html) property in the event argument.

* **Dragging** - Specifies that `SfListView` is currently being dragged in the view.
* **Fling** - Specifies that fling action is performed on `SfListView`.
* **Idle** - Specifies that `SfListView` is not currently scrolling.
* **Programmatic** - Specifies that scrolling is performed by using [ScrollTo](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ScrollTo.html) or [ScrollToRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LayoutBase~ScrollToRowIndex.html) method.

{% highlight c# %}

listView.ScrollStateChanged += ListView_ScrollStateChanged;
private void ListView_ScrollStateChanged(object sender, ScrollStateChangedEventArgs e)
{
   if (e.ScrollState == ScrollState.Idle)
   {
      DisplayAlert("ScrollState", "Scrolling has stopped", "OK");
   }
}

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
    var listViewInboxInfo = new ListViewInboxInfo();
    listViewInboxInfo.Title = "Bryce Thomas";
    listViewInboxInfo.Subject = "Congratulations on the move!";
    viewModel.InboxInfo.Add(listViewInboxInfo);
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

N> In SfListView, unable to perform ItemHolding operations by using Mouse in Windows Desktop platform. Since, there is no any long pressed events (like Holding event in touch) for the mouse in Framework itself.

## Improving ListView Performance

SfListView has been built from the ground up with an optimized view reuse strategy to achieve the best possible performance on the Xamarin platform, even when loading large data sets. Below some techniques to Improving performance of a SfListView,

* Bind the ItemsSource property to an IList<T> collection instead of an IEnumerable<T> collection, because IEnumerable<T> collections don't support random access.
* Avoid loading complex layout in the template that contains large size of images or nested containers which cause some performance degradation on scrolling. So, recommended to use fewer elements and images with less size and resolution to achieve the maximum performance.
* Avoid placing a SfListView inside a ScrollView for the following reasons:
  * The SfListView implements its own scrolling.
  * The SfListView will not receive any gestures, as they will be handled by the parent ScrollView.
  * Should define the size to SfListView if load it inside ScrollView.
* Avoid changing the cell layout based on the BindingContext. This incurs large layout and initialization costs.