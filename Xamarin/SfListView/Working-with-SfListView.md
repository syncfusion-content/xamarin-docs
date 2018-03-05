---
layout: post
title: Working with SfListView
description: Describes about different functionalities and events in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Working With The SfListView

## Launching the SfListView inside StackLayout

When the SfListView is loaded inside StackLayout, set the `HorizontalOptions` and `VerticalOptions` as `LayoutOptions.FillAndExpand`. Because StackLayout positions the child element one after other either horizontally or vertically based on the orientation of StackLayout. The size of StackLayout depends on how the HorizontalOptions and VerticalOptions properties are set. By default, StackLayout use the entire screen. 

{% highlight xaml %}
<StackLayout VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">
  <syncfusion:SfListView x:Name="listView" ItemsSource="{Binding BookInfo}" />
</StackLayout>
{% endhighlight %}

### Load SfListView inside ScrollView within StackLayout

When the SfListView is loaded inside ScrollView or any layout such as Grid, StackLayout etc. into the StackLayout, set the `VerticalOptions` and `HorizontalOptions` of immediate parent as `LayoutOptions.FillAndExpand`.

{% highlight xaml %}
<local:ExtScrollView x:Name="scrollView" >
   <sync:SfListView x:Name="listView" ItemsSource="{Binding BookInfo}"/>
</local:ExtScrollView>
{% endhighlight %}
{% highlight C# %}
 public class ExtScrollView: ScrollView
 {    
     protected override void LayoutChildren(double x, double y, double width, double height)
     {
         this.Content.HeightRequest = height;
         base.LayoutChildren(x, y, width, height);
     }
}
{% endhighlight %}

You can download the entire source code from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfListViewSample197024233.zip).

## Load SfListView inside SfPullToRefresh

The SfPullToRefresh is a refresh control allows you to interact and refresh the view loaded in it. When the SfListView is loaded inside the SfPullToRefresh, it refreshes the item while performing the pull to refresh action. The steps to be followed to load the SfListView inside SfPullToRefresh is explained in SfPullToRefresh property Customization tab.

The final output of iOS, Android, and Windows Phone devices look likes as follows:

![](SfListView_images/SfListView_SlideOnTop-Xamarin.forms.gif)

## Load the SfListView in CarouselView

When the SfListView is loaded in CarouselView with [SfListView.AllowSwiping](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AllowSwiping.html) as false, it behaves in UWP platform as follows:
 
 * While performing first swipe on the view, it will be handled by ScrollView to ensure whether scrolling is happened or not. If not means the manipulation to parent cannot be passed immediately due to UWP platform behavior. The second swipe will be listened by CarouselView, and the view gets swiped. This is the behavior of the SfListView. 

When SfListView is loaded in CarouselView with `SfListView.AllowSwiping` as true, it behaves as follows:  
 
 * When swiping in iOS, suddenly carousel swipe happened. To swipe ListViewItem, touch and hold the item for some fraction of seconds (0.25 - 0.5 seconds) and then swipe. 
 * When swiping any Item, the SfListView handles the touch and swipe the ListViewItem.  
 * After swiping on ListViewItem, SwipeView will load along with it. If you swipe SwipeView element, Carousel view is swiped. Or else swipe on ListViewItem, control handles touching and swiping the item as usual. 
 * If you swipe header, footer or group header elements, Carousel view will swipe in Android platform. But in UWP, first swipe on those elements will be handled by SfListView itself, because manipulation to parent cannot be passed immediately. The second swipe will be listened by CarouselView.

## Programmatic scrolling

### Scroll to row index

The SfListView allows programmatically scrolling a row, based on the index by using the [ScrollToRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LayoutBase~ScrollToRowIndex.html) method for both linear and grid layouts. It also supports to enable and disable the scrolling animation while changing the view. By default, the scrolling will be animated.

N> If grouping is enabled, get the desired row index by passing the underlying data in the [DisplayItems.IndexOf](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DisplayItems~IndexOf.html) method.

{% highlight c# %}

int index = listView.DataSource.DisplayItems.IndexOf(viewModel.Customers[2]); 
listView.LayoutManager.ScrollToRowIndex(index, true); 

{% endhighlight %}

#### Limitations in scrolling to row index

 * When [AutoFitMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AutoFitMode.html) is `Height` or grouping is enabled, scroll animation will be disabled by default in Android and iOS platforms. 
 * If [ScrollToRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LayoutBase~ScrollToRowIndex.html) method is called while loading the `SfListView`, set `disableAnimation` to `true` to scroll to appropriate row index or else view does not scrolled in Android.

## Identifying scroll state changes

The SfListView will notify the scrolling state changes by using the [ScrollStateChanged](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ScrollStateChanged_EV.html) event.

Following states will be notified via [ScrollState](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ScrollState.html) property in the event argument:

 * Dragging: Specifies that `SfListView` is currently being dragged in the view.
 * Fling: Specifies that fling action is performed on `SfListView`.
 * Idle: Specifies that `SfListView` is not currently scrolling.
 * Programmatic: Specifies that scrolling is performed by using [ScrollTo](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ScrollTo.html) or [ScrollToRowIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LayoutBase~ScrollToRowIndex.html) method.

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

### Loaded event

The [Loaded Event](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Loaded_EV.html) is raised when the SfListView is loaded in view for the first time.

{% highlight c# %}
listView.Loaded += ListView_Loaded;

private void ListView_Loaded(object sender, ListViewLoadedEventArgs e)
{
   listView.SelectedItems.Add(viewModel.Customers[2]);
}
{% endhighlight %}

### Tapped event

The [ItemTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTapped_EV.html) event will be triggered whenever tapping the item. [ItemTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemTappedEventArgs.html) has the following members which the information for the `ItemTapped` event:

 * ItemType: It gets the type of the tapped item.
 * ItemData: The underlying data associated with the tapped item as its arguments.

{% highlight c# %}
listView.ItemTapped += ListView_ItemTapped;

private void ListView_ItemTapped(object sender, Syncfusion.ListView.XForms.ItemTappedEventArgs e)
{
    if (e.ItemData == viewModel.InboxInfo[0])
      viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo);  
}
{% endhighlight %}

### ItemDoubleTapped event

The [ItemDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDoubleTapped_EV.html) event will be triggered whenever double tapping the item. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDoubleTappedEventArgs.html) has the following members providing information for the `ItemDoubleTapped` event:

 * ItemType: It gets the type of double tapped item.
 * ItemData: The underlying data associated with the double tapped item as its arguments.

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

### ItemHolding event

The [ItemHolding](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemHolding_EV.html) event will be triggered whenever long pressing the item. The [ItemHoldingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemHoldingEventArgs.html) has the following members providing information for the `ItemHolding` event:

 * ItemType: It gets the type of the long pressed item.
 * ItemData: The underlying data associated with the holding item as its arguments.

{% highlight c# %}
listView.ItemHolding += ListView_ItemHolding;

private void ListView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
   if (e.ItemData == viewModel.InboxInfo[3])
      viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo);         
}
{% endhighlight %}

N> In SfListView, ItemHolding operations cannot be performed using mouse in windows desktop platform. Because there is no long pressed events (like Holding event in touch) for the mouse in Framework.

## Improving ListView performance

The SfListView has been built from the ground up with an optimized view reuse strategy, to achieve the best possible performance on the Xamarin platform even when loading large data sets. Following techniques are used to improve performance of the SfListView:

 * Bind the ItemsSource property to an IList<T> collection instead of an IEnumerable<T> collection because IEnumerable<T> collection do not support random access.
 * Avoid loading complex layout in the template contains large size of images or nested containers, which cause some performance degradation on scrolling. So recommended to use fewer elements and images with less size and resolution to achieve the maximum performance.
 * Avoid placing the SfListView inside ScrollView for the following reasons:
  * The SfListView implements its own scrolling.
  * The SfListView will not receive any gestures as it will be handled by the parent ScrollView.
  * Should define size to the SfListView if it loads inside ScrollView.
 * Avoid changing the cell layout based on the BindingContext. This incurs large layout and initialization costs.
