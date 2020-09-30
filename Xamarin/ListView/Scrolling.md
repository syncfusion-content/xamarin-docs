---
layout: post
title: Handling Syncfusion ListView Scrolling
description: This section describes about the scrolling behavior of SfListView control and how it can be handled and customized.
platform: xamarin
control: SfListView
documentation: ug
---
# Scrolling in Xamarin ListView (SfListView)

## Programmatic scrolling

### Scrolling to row index

The SfListView allows programmatically scrolling based on the index by using the [ScrollToRowIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LayoutBase.html#Syncfusion_ListView_XForms_LayoutBase_ScrollToRowIndex_System_Int32_Syncfusion_ListView_XForms_ScrollToPosition_System_Boolean_) method for both linear and grid layouts. It also enables and disables the scrolling animation when changing the view. By default, the scrolling will be animated.

You can set position of item in view while scrolling by passing [ScrollToPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ScrollToPosition.html) to `ScrollToRowIndex` method. Below are four different types of positions:

* MakeVisible: Scrolls a specific item to make visible in the view. If the item is already in view, scrolling will not occur.
* Start: Scrolls a specific item to be positioned at the begin of the view.
* End: Scrolls a specific item to be positioned at the end of the view.
* Center: Scrolls a specific item to be positioned at the center of the view.

You can also scroll to specified data in `SfListView` using the [ScrollTo](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ScrollTo_System_Double_System_Boolean_) method.

{% tabs %}
{% highlight c# %}

int index = listView.DataSource.DisplayItems.IndexOf(viewModel.Customers[2]); 
// Programmatic scrolling based on the item index.
listView.LayoutManager.ScrollToRowIndex(index, Syncfusion.ListView.XForms.ScrollToPosition.Center, true); 
// Programmatic scrolling based on the item data.
listView.ScrollTo(ViewModel.Customers[index], Syncfusion.ListView.XForms.ScrollToPosition.Center, true);

{% endhighlight %}
{% endtabs %}

N> If grouping is enabled, get the desired row index by passing the underlying data in the [DisplayItems.IndexOf](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DisplayItems.html#Syncfusion_DataSource_DisplayItems_IndexOf_System_Object_) method.

{% tabs %}
{% highlight c# %}

int index = listView.DataSource.DisplayItems.IndexOf(viewModel.Customers[2]); 
listView.LayoutManager.ScrollToRowIndex(index, true); 

{% endhighlight %}
{% endtabs %}

### Limitations

 * When [AutoFitMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_AutoFitMode) is `Height` or grouping is enabled, the scroll animation will be disabled by default in Android and iOS platforms. 
 * If the [ScrollToRowIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LayoutBase.html#Syncfusion_ListView_XForms_LayoutBase_ScrollToRowIndex_System_Int32_Syncfusion_ListView_XForms_ScrollToPosition_System_Boolean_) method is called when loading the `SfListView`, set `disableAnimation` to `true` to scroll to the appropriate row index, or else view does not scrolled in Android.
 * If the `ScrollToRowIndex` method is applied to a particular item index while the item is in Grouping or AutoFit mode, the particular item will get displayed in view but not in the exact position when the [ScrollToPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ScrollToPosition.html) property is set as `MakeVisible` or `Center` for first time.
* In UWP platform, when you hover and scroll the inner listview, the outer listview will not be scrolled by default. To overcome this, set the `InputTransparent` to `True` for the parent element loaded in the `ItemTemplate`. If you set InputTransparent, then the inner listview scroll will not work. This is the default behavior of the listview.
* The programmatic scrolling is not supported when the `QueryItemSize` event is handled.

## Scrollbar visibility

The SfListView provides an option to enable or disable the `Scrollbar` visibility by using the [IsScrollBarVisible](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_IsScrollBarVisible) property. By default, the value will be `true`.  

N> Due to some restrictions in native ScrollView renderer in Xamarin.Forms, you cannot change the `IsScrollBarVisible` value at runtime. It can be defined only when initializing the SfListView. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" IsScrollBarVisible="False" />
{% endhighlight %}
{% highlight c# %}
listView.IsScrollBarVisible = false; 
{% endhighlight %}
{% endtabs %}

## ListView with full height

The `SfListView` will load all of its items by setting the [IsScrollingEnabled](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_IsScrollingEnabled) property to `false`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" IsScrollingEnabled="False" />
{% endhighlight %}
{% highlight c# %}
listView.IsScrollingEnabled = false; 
{% endhighlight %}
{% endtabs %}

N> ListView's scrolling will not be enabled when `IsScrollingEnabled` is `false`. To enable scrolling, load ListView inside `ScrollView`.

## Identifying scroll state changes

The SfListView will notify the scrolling state changes by using the [ScrollStateChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event.

The following states will be notified using the [ScrollState](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ScrollState.html) property in the event argument.

 * Dragging: Specifies that `SfListView` is currently being dragged in the view.
 * Fling: Specifies that fling action is performed on the `SfListView`.
 * Idle: Specifies that `SfListView` is not currently scrolling.
 * Programmatic: Specifies that scrolling is performed by using [ScrollTo](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ScrollTo_System_Double_System_Boolean_) or [ScrollToRowIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LayoutBase.html#Syncfusion_ListView_XForms_LayoutBase_ScrollToRowIndex_System_Int32_Syncfusion_ListView_XForms_ScrollToPosition_System_Boolean_) method.

{% tabs %}
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
{% endtabs %}

## Identify when end of the list is reached on scrolling

The SfListView allows notifying when scrolling using the [Changed](https://help.syncfusion.com/cr/xamarin/Syncfusion.GridCommon.ScrollAxis.ScrollAxisBase.html) event of [ScrollAxisBase](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ScrollAxis.ScrollAxisBase.html) in [VisualContainer](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.VisualContainer.html) of the SfListView. By using this event, you can find whether reached the last item in the list in the SfListView based on the [LastBodyVisibleLineIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.GridCommon.ScrollAxis.ScrollAxisBase.html#Syncfusion_GridCommon_ScrollAxis_ScrollAxisBase_LastBodyVisibleLineIndex) property and underlying collection count.

{% tabs %}
{% highlight c# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public partial class MainPage : ContentPage
{
    VisualContainer visualContainer;
    bool isAlertShown = false;

    public MainPage()
    {
        InitializeComponent();
        visualContainer = listView.GetVisualContainer();
        visualContainer.ScrollRows.Changed += ScrollRows_Changed;
    }

    ///<summary>
    ///To notify when end reached
    ///</summary>
    private void ScrollRows_Changed(object sender, ScrollChangedEventArgs e)
    {
        var lastIndex = visualContainer.ScrollRows.LastBodyVisibleLineIndex;

        //To include header if used
        var header = (listView.HeaderTemplate != null && !listView.IsStickyHeader) ? 1 : 0;

        //To include footer if used
        var footer = (listView.FooterTemplate != null && !listView.IsStickyFooter) ? 1 : 0;
        var totalItems = listView.DataSource.DisplayItems.Count + header + footer;

        if ((lastIndex == totalItems - 1))
        {
            if (!isAlertShown)
            {
                DisplayAlert("Alert", "End of list reached...", "Ok");
                isAlertShown = true;
            }
        }
        else
            isAlertShown = false;
    }
}

{% endhighlight %}
{% endtabs %}

You can get the item elements to hold by a scrollable visual container using the [GetVisualContainer](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.Control.Helpers.SfListViewHelper.html#Syncfusion_ListView_XForms_Control_Helpers_SfListViewHelper_GetVisualContainer_Syncfusion_ListView_XForms_SfListView_) method. It is a helper method of SfListView control.

{% tabs %}
{% highlight c# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public partial class MainPage : ContentPage
{
    VisualContainer visualContainer;
	
    public MainPage()
    {
        InitializeComponent();
        visualContainer = listView.GetVisualContainer();
	}
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Notify-when-end-of-the-xamarin.forms-listview-reached-on-scrolling).

## Maintain the scroll position while updating ItemsSource at runtime

The SfListView have scrolled to top automatically when changing the ItemsSource at runtime. However, you can maintain the same scrolled position by using the `ScrollY` value of ExtendedScrollView from the [VisualContainer](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.VisualContainer.html). After changing the ItemsSource, you can pass the ScrollY value to [ScrollTo](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ScrollTo_System_Double_System_Boolean_) method of SfListView and scroll back to the same position.

For horizontal orientation, use the `ScrollX` value of ExtendedScrollView.

 By using [Reflection](https://msdn.microsoft.com/en-us/library/system.reflection(v=vs.110).aspx), get the value of `ScrollOwner` from `VisualContainer` and use it.

{% tabs %}
{% highlight c# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public partial class MainPage : ContentPage
{
    ExtendedScrollView scrollView;

    public MainPage()
    {
        InitializeComponent();
        scrollView = listView.GetScrollView();
    }

    private void ChangeItemsSource_Clicked(object sender, EventArgs e)
    {
        var viewModel = new ContactsViewModel();
        listView.ItemsSource = viewModel.EmployeeInfo;
        listView.ScrollTo(scrollView.ScrollY);
    }
}

{% endhighlight %}
{% endtabs %}

You can get the scroll view by using the [GetScrollView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.Control.Helpers.SfListViewHelper.html#Syncfusion_ListView_XForms_Control_Helpers_SfListViewHelper_GetScrollView_Syncfusion_ListView_XForms_SfListView_) method. It is a helper method to get the Syncfusion.ListView.XForms.ExtendedScrollView class.

{% tabs %}
{% highlight c# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public partial class MainPage : ContentPage
{
    ExtendedScrollView scrollView;

    public MainPage()
    {
        InitializeComponent();
        scrollView = listView.GetScrollView();
    }
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Maintaing-scroll-position-on-changing-itemssource-xamarin.forms-listview).

## How to handle the recycle of the ListView Items

By default, the Listview reuses items on scrolling and source collection change. You can skip the reusing while scrolling by setting the [ListViewCachingStrategy](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ListViewCachingStrategy.html) property to `CreateNewTemplate` for the ListView. It creates a new element for every data in the ItemsSource. The default value is `ListViewCachingStrategy.RecycleTemplate` where the data template gets reused while the data object associated with the listview item gets changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ListViewCachingStrategy="CreateNewTemplate" />
{% endhighlight %}
{% highlight c# %}
listView.ListViewCachingStrategy = ListViewCachingStrategy.CreateNewTemplate; 
{% endhighlight %}
{% endtabs %}

You can skip the reusing of list items on the `ItemsSourcePropertyChanged` by setting the [ItemsSourceChangeCachingStrategy](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemsSourceChangeCachingStrategy.html) property to `ClearItems` for the listview. Here, the existing ListView items will be cleared and create a new list of items when the ItemsSource changed. The default value is `ItemsSourceChangeCachingStrategy.RecycleItems` where the listView items will be recycled in the ItemsSource changes.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemsSourceChangeCachingStrategy="ClearItems" />
{% endhighlight %}
{% highlight c# %}
listView.ItemsSourceChangeCachingStrategy = ItemsSourceChangeCachingStrategy.ClearItems;
{% endhighlight %}
{% endtabs %}

## See Also

[How to detect listview scrolling direction in Xamarin.Forms](https://www.syncfusion.com/kb/11019)                                                                                
[How to maintain the same scroll position of ListView while updating ItemsSource at runtime](https://www.syncfusion.com/kb/8029)                                                                                
[How to add a jump list with Xamarin.Forms ListView](https://www.syncfusion.com/kb/11021)                                                                                                   
[How to load more items when scroll reached the end of list](https://www.syncfusion.com/kb/7792)                                                                                      
[How to automatically scroll to bring a selected item into the view](https://www.syncfusion.com/kb/8190)                                                                                
[How to maintain the scroll position of ListView after clearing the filter at runtime](https://www.syncfusion.com/kb/9535)                                                                                                                          
[How to bring the item into view when adding at runtime in the listview](https://www.syncfusion.com/kb/9957)                                                                                                                                                                                                                                                            
[How to update the header height on scrolling in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11830/)

