---
layout: post
title: Working with Xamarin.Forms ListView | Syncfusion
description: This topic describes how to use Syncfusion Xamarin.Forms ListView along with SQLite, Prism frameworks, interacting events, and other different functionalities.
platform: xamarin
control: SfListView
documentation: ug
---

# Working with ListView in Xamarin ListView (SfListView)

## Interacting with ListView Items

### Loaded event

The [Loaded](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is raised when the SfListView is loading in view for the first time.

{% tabs %}
{% highlight c# %}

listView.Loaded += ListView_Loaded;

private void ListView_Loaded(object sender, ListViewLoadedEventArgs e)
{
   listView.SelectedItems.Add(viewModel.Customers[2]);
}

{% endhighlight %}
{% endtabs %}

The `Loaded` event used for the following use cases:

* To scroll the desired position or index by using the [ScrollTo](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ScrollTo_System_Double_System_Boolean_) or [ScrollToRowIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LayoutBase.html#Syncfusion_ListView_XForms_LayoutBase_ScrollToRowIndex_System_Int32_Syncfusion_ListView_XForms_ScrollToPosition_System_Boolean_).
* To collapse all the groups.
* To find the sorted or grouped [DataSource.DisplayItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_DisplayItems) of underlying bound data to SfListView.

### Tapped event

The [ItemTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event will be triggered whenever tapping the item. Here, [TapCommandParameter](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_TapCommandParameter) property sets the parameter for [SfListView.TapCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_TapCommand) and its default value is [ItemTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemTappedEventArgs.html). `ItemTappedEventArgs` has the following members which provides the information for `ItemTapped` event:

 * [ItemType](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemTappedEventArgs.html#Syncfusion_ListView_XForms_ItemTappedEventArgs__ctor_Syncfusion_ListView_XForms_ItemType_System_Object_Xamarin_Forms_Point_): It gets the type of the tapped item.
 * [ItemData](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemTappedEventArgs.html#Syncfusion_ListView_XForms_ItemTappedEventArgs_ItemData): The underlying data associated with the tapped item as its arguments.
 * [Position](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemTappedEventArgs.html#Syncfusion_ListView_XForms_ItemTappedEventArgs_Position): Gets the touch position in the tapped item.

{% tabs %}
{% highlight c# %}

listView.ItemTapped += ListView_ItemTapped;

private void ListView_ItemTapped(object sender, Syncfusion.ListView.XForms.ItemTappedEventArgs e)
{
    if (e.ItemData == viewModel.InboxInfo[0])
      viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo);  
}

{% endhighlight %}
{% endtabs %}

The [ItemTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is used for the following use cases:

* To show the context menu.
* To navigate to another page.
* To delete the item in the list view at runtime.
* To display the item details into another view.
* To expand the view like, accordion.
* To change the underlying bound data.
* To skip other events like selection events if the Handled property set to true.

### ItemDoubleTapped event

The [ItemDoubleTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event will be triggered whenever double tapping the item. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDoubleTappedEventArgs.html) has the following members providing information for the `ItemDoubleTapped` event:

 * [ItemType](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDoubleTappedEventArgs.html#Syncfusion_ListView_XForms_ItemDoubleTappedEventArgs__ctor_Syncfusion_ListView_XForms_ItemType_System_Object_Xamarin_Forms_Point_): It gets the type of double tapped item.
 * [ItemData](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDoubleTappedEventArgs.html#Syncfusion_ListView_XForms_ItemDoubleTappedEventArgs_ItemData): The underlying data associated with the double tapped item as its arguments.
 * [Position](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDoubleTappedEventArgs.html#Syncfusion_ListView_XForms_ItemDoubleTappedEventArgs_Position): Gets the touch position in the double tapped item.

{% tabs %}
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
{% endtabs %}

The [ItemDoubleTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is used for the following use cases:

* To show the context menu.
* To delete the item in the list view at runtime.
* To change the underlying bound data.

### ItemHolding event

The [ItemHolding](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event will be triggered whenever long pressing the item. Here, [HoldCommandParameter](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HoldCommandParameter) sets the parameter for [SfListView.HoldCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HoldCommand) and its default value is [ItemHoldingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemHoldingEventArgs.html). `ItemHoldingEventArgs` has the following members which provides the information for `ItemHolding` event:

 * [ItemType](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemHoldingEventArgs.html#Syncfusion_ListView_XForms_ItemHoldingEventArgs__ctor_Syncfusion_ListView_XForms_ItemType_System_Object_Xamarin_Forms_Point_): It gets the type of the long pressed item.
 * [ItemData](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemHoldingEventArgs.html#Syncfusion_ListView_XForms_ItemHoldingEventArgs_ItemData): The underlying data associated with the holding item as its arguments.
 * [Position](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemHoldingEventArgs.html#Syncfusion_ListView_XForms_ItemHoldingEventArgs_Position): Gets the touch position in the holding item.

{% tabs %}
{% highlight c# %}

listView.ItemHolding += ListView_ItemHolding;

private void ListView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
   if (e.ItemData == viewModel.InboxInfo[3])
      viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo);         
}

{% endhighlight %}
{% endtabs%}

The [ItemHolding](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is used for the following use cases:

* To show the context menu.

N> Interaction events of the `SfListView` will be triggered for all the `ListViewItems` like `HeaderItem`, `FooterItem`, `GroupHeaderItem`, `LoadMoreItem`, and `RecordItem`. You can handle the interaction actions based on the `ItemType` of the event args. 

### ItemAppearing

The [ItemAppearing](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is raised when the items are appearing in the view on scrolling, loading, and navigating from one page to another page. The [ItemAppearingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemAppearingEventArgs.html) has the following member which provides the information of appearing Items.

* [ItemData](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemAppearingEventArgs.html#Syncfusion_ListView_XForms_ItemAppearingEventArgs_ItemData): The underlying data associated with the appearing item.

{% tabs %}
{% highlight c# %}

listView.ItemAppearing += listView_ItemAppearing;

private void listView_ItemAppearing(object sender, Syncfusion.ListView.XForms.ItemAppearingEventArgs e)
{
    if (e.ItemData == viewModel.BookInfo[0])
        Debug.WriteLine((e.ItemData as BookInfo).BookName);

    // If the ItemData value is "Header", then it's a header item.
    if (e.ItemData == "Header")
        Debug.WriteLine("Header is Appeared");
}

{% endhighlight %}
{% endtabs %}

The [ItemAppearing](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event used for the following use cases:

* To find the item appears in the view.
* To customize the appearing item to change the background color using converter.

### ItemDisappearing

The [ItemDisappearing](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is raised when the items disappearing in the view on scrolling, disposing, and navigating from one page to another page. The [ItemDisappearingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDisappearingEventArgs.html) has the following member which provides the information on disappearing Items:

* [ItemData](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDisappearingEventArgs.html#Syncfusion_ListView_XForms_ItemDisappearingEventArgs_ItemData): The underlying data associated with the disappearing item.

{% tabs %}
{% highlight c# %}

listView.ItemDisappearing += listView_ItemDisappearing;

private void listView_ItemDisappearing(object sender, Syncfusion.ListView.XForms.ItemDisappearingEventArgs e)
{
    if (e.ItemData == viewModel.BookInfo[0])
        Debug.WriteLine((e.ItemData as BookInfo).BookName);

    // If the ItemData value is "Footer" then it's a Footer item.
    if (e.ItemData == "Footer")
        Debug.WriteLine("Footer is Disappeared");
}

{% endhighlight %}
{% endtabs %}

The [ItemDisappearing](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event used for the following use cases:

* To find the item disappears in the view.

## Improving ListView performance

The SfListView has been built from the ground up with an optimized view reuse strategy for the best possible performance on the Xamarin platform even when loading large data sets. Following techniques are used to improve performance of the SfListView:

 * Bind the ItemsSource property to an IList<T> collection instead of an IEnumerable<T> collection because IEnumerable<T> collection do not support random access.
 * The `SfListView` gets refreshed each and every time a new item added into the underlying collection. Because, when adding items at runtime, the `DataSource` gets refreshed. To avoid this behavior, use [BeginInit()](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_BeginInit) to stop the RefreshView() calling in each time, and use [EndInit()](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_EndInit) to start the RefreshView() calling when adding number of finished items.
 * Avoid loading complex layout in template of listview. For example, loading large-size images or nested containers degrades the scrolling performance. This practice commonly degrades performance in all platforms, and particularly more in Android version API level 19. So, use fewer elements and images with small size and resolution to achieve the maximum performance.
 * Avoid placing the SfListView inside ScrollView for the following reasons:
    * The SfListView implement its own scrolling.
    * The SfListView will not receive any gestures as it will be handled by the parent ScrollView.
    * Should define size to the SfListView if it loads inside ScrollView.
 * Avoid changing the cell layout based on the BindingContext. This incurs large layout and initialization costs.
 * Implement a model class inherited with `INotifyPropertyChanged` interface to notify the property changes at runtime.

## Loading ListView inside ScrollView

When the `SfListView` is loaded inside the `ScrollView` with the height of total items, scrolling will not occur in the SfListView only when [AllowSwiping](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_AllowSwiping) is set to `true`. The SfListView does not pass touch to the parent ScrollView in UWP, because swiping is handled in it. 

When the SfListView is loaded inside the ScrollView the following scenarios, the height of the total items is set to `HeightRequest` of the SfListView.

* If the position of the SfListView is not in view when loading inside the StackLayout with more than one children, the SfListView will not be loaded. Because, the StackLayout passes the height for the `SfListView` as 1. 

* When loading the SfListView inside the `Grid` with row definition as `Auto` in UWP, Grid passes the height for the SfListView to be `1`.

When the SfListView is loaded inside the ScrollView with sticky header and sticky group header, it changed to scrollable. The empty space remains after the `SfListView` items, when the device orientation is changed to horizontal. Because, the total extend is set to the ScrollView in horizontal orientation.

{% tabs %}
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
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/xamarin.forms-listview-inside-scrollview).

## Loading ListView inside CarouselPage/Master detail page

When the SfListView is loaded in CarouselView with [SfListView.AllowSwiping](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_AllowSwiping) as false, it behaves in UWP platform as follows:
 
 * When performing first swipe on the view, it will be handled by ScrollView to ensure whether scrolling is happened or not. If not means the manipulation to parent cannot be passed immediately due to UWP platform behavior. The second swipe will be listened by CarouselView, and the view gets swiped. This is the behavior of the SfListView. 

When the SfListView is loaded in CarouselView with `SfListView.AllowSwiping` as true, it behaves as follows:  
 
 * When swiping in iOS, suddenly carousel swipe happened even if gesture is added to the carousel view. To swipe ListViewItem, touch and hold the item for some fraction of seconds (0.25 - 0.5 seconds) and then swipe. 
 * When swiping any Item, the SfListView handles the touch and swipe the ListViewItem.  
 * After swiping on ListViewItem, SwipeView will load along with it. If you swipe SwipeView element, Carousel view is swiped. Or else swipe on ListViewItem, control handles touching and swiping the item as usual. 
 * If you swipe header, footer or group header elements, Carousel view will swipe in Android platform. But in UWP, first swipe on those elements will be handled by SfListView itself, because manipulation to parent cannot be passed immediately. The second swipe will be listened by CarouselView.

## Context menu on items

The SfListView allows displaying a pop-up menu with different menu items to an item when it is long pressed by customizing the SfListView and by using custom view in it. For UWP platform, you can also display the pop-up menu when pressing right click button over the item. Display the pop-up menu by accessed the touch position in the item based on [Position](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemHoldingEventArgs.html#Syncfusion_ListView_XForms_ItemHoldingEventArgs_Position) property from [ItemHolding](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event.

Defining SfPopUpView

{% highlight c# %}

namespace SfListViewSample
{
    public class Behavior : Behavior<SfListView>
    {
        SfListView ListView;
        int sortOrder = 0;
        Contacts item;
        SfPopupLayout popupLayout;
        protected override void OnAttachedTo(SfListView listView)
        {
            ListView = listView;
            ListView.ItemHolding += ListView_ItemHolding;
            ListView.ScrollStateChanged += ListView_ScrollStateChanged;
            ListView.ItemTapped += ListView_ItemTapped;
            base.OnAttachedTo(listView);
        }

        private void ListView_ItemTapped(object sender, Syncfusion.ListView.XForms.ItemTappedEventArgs e)
        {
            popupLayout.Dismiss();
        }

        private void ListView_ScrollStateChanged(object sender, ScrollStateChangedEventArgs e)
        {
            popupLayout.Dismiss();
        }

        private void ListView_ItemHolding(object sender, ItemHoldingEventArgs e)
        {
            item = e.ItemData as Contacts;
            popupLayout = new SfPopupLayout();
            popupLayout.PopupView.HeightRequest = 100;
            popupLayout.PopupView.WidthRequest = 100;
            popupLayout.PopupView.ContentTemplate = new DataTemplate(() =>
            {

                var mainStack = new StackLayout();
                mainStack.BackgroundColor = Color.Teal;

                var deletedButton = new Button()
                {
                    Text = "Delete",
                    HeightRequest=50,
                    BackgroundColor=Color.Teal,
                    TextColor = Color.White
                };
                deletedButton.Clicked += DeletedButton_Clicked;
                var sortButton = new Button()
                {
                    Text = "Sort",
                    HeightRequest = 50,
                    BackgroundColor = Color.Teal,
                    TextColor=Color.White
                };
                sortButton.Clicked += SortButton_Clicked;
                mainStack.Children.Add(deletedButton);
                mainStack.Children.Add(sortButton);
                return mainStack;

            });
            popupLayout.PopupView.ShowHeader = false;
            popupLayout.PopupView.ShowFooter = false;
            if (e.Position.Y + 100 <= ListView.Height && e.Position.X + 100 > ListView.Width)
                popupLayout.Show((double)(e.Position.X - 100), (double)(e.Position.Y));
            else if (e.Position.Y + 100 > ListView.Height && e.Position.X + 100 < ListView.Width)
                popupLayout.Show((double)e.Position.X, (double)(e.Position.Y - 100));
            else if (e.Position.Y + 100 > ListView.Height && e.Position.X + 100 > ListView.Width)
                popupLayout.Show((double)(e.Position.X - 100), (double)(e.Position.Y - 100));
            else
                popupLayout.Show((double)e.Position.X, (double)(e.Position.Y));
        }

        private void SortButton_Clicked(object sender, EventArgs e)
        {
            if (ListView == null)
                return;

            ListView.DataSource.SortDescriptors.Clear();
            popupLayout.Dismiss();
            ListView.DataSource.LiveDataUpdateMode = LiveDataUpdateMode.AllowDataShaping;
            if (sortOrder == 0)
            {
                ListView.DataSource.SortDescriptors.Add(new SortDescriptor { PropertyName = "ContactName", Direction = ListSortDirection.Descending });
                sortOrder = 1;
            }
            else
            {
                ListView.DataSource.SortDescriptors.Add(new SortDescriptor { PropertyName = "ContactName", Direction = ListSortDirection.Ascending });
                sortOrder = 0;
            }
        }

        private void Dismiss()
        {
            popupLayout.IsVisible = false;
        }

        private void DeletedButton_Clicked(object sender, EventArgs e)
        {
            
            if (ListView == null)
                return;

            var source = ListView.ItemsSource as IList;

            if (source != null && source.Contains(item))
                source.Remove(item);
            else
                App.Current.MainPage.DisplayAlert("Alert", "Unable to delete the item", "OK");

            item = null;
            source = null;
        }
    }
}

{% endhighlight %}

Defining the SfListView

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <ContentPage.BindingContext>
    <local:ContactsViewModel x:Name="viewModel"/>
  </ContentPage.BindingContext>
    <ContentPage.Content>
        <Grid>
            <listView:SfListView x:Name="listView" ItemsSource="{Binding Items}" >
                <listView:SfListView.ItemTemplate>
                    <DataTemplate>
                        <Grid>
                            <Image Source="{Binding ContactImage}"/>
                            <Label Text="{Binding ContactName}" />
                            <Label Text="{Binding ContactNumber}" />
                        </Grid>
                    </DataTemplate>
                </listView:SfListView.ItemTemplate>
            <listView:SfListView>
        </Grid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% endtabs %}
    
You can download the entire source code of this demo [here](https://github.com/SyncfusionExamples/How-to-display-context-menu-when-tapping-in-Xamarin.Forms-ListView).

![Xamarin.Forms listview with Context menu](SfListView_images/ContextMenu.jpg)

## Paging

The SfListView allows displaying paging using the [SfDataPager](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.html) control. It can be performed through loading data dynamically into ItemsSource of the SfListView using OnDemandLoading event for the current page by setting the [SfDataPager.UseOnDemandPaging](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_UseOnDemandPaging) to ‘True’. By using the [SfDataPager.PageSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_PageSize) property, you can define the number of list items to be displayed in each page.

N> For more details about paging refer to [here](https://help.syncfusion.com/xamarin/sfdatagrid/paging).

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:sfPager="clr-namespace:Syncfusion.SfDataGrid.XForms.DataPager;assembly=Syncfusion.SfDataGrid.XForms">

    <ContentPage.Behaviors>
        <local:SfListViewPagingBehavior/>
    </ContentPage.Behaviors>

    <ContentPage.Resources>
        <ResourceDictionary>
            <local:CurrencyFormatConverter x:Key="currencyFormatConverter"/>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <StackLayout>

            <syncfusion:SfListView x:Name="listView" >
                <syncfusion:SfListView.LayoutManager>
                    <syncfusion:GridLayout SpanCount = "2">
                </syncfusion:SfListView.LayoutManager>
                <syncfusion:SfListView.ItemTemplate>
                    <DataTemplate>
                        <Grid>
                            <Image Source="{Binding Image}" />    
                            <Label Text="{Binding Name}" />
                            <Label Text="{Binding Weight}" />
                        </Grid>
                    </DataTemplate>
                </syncfusion:SfListView.ItemTemplate>
            </syncfusion:SfListView>

            <sfPager:SfDataPager x:Name="dataPager" UseOnDemandPaging="True" DisplayMode = "PreviousNextNumeric" NumericButtonCount = "4" PageSize = "6">

        </StackLayout>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.ListView.XForms;
using Syncfusion.SfDataGrid.XForms.DataPager;

namespace Paging
{
    public class Paging : ContentPage
    {
        SfDataPager sfPager = new SfDataPager();
        SfListView listView = new SfListView();
        public Paging()
        {
            var stackLayout = new StackLayout();
            sfPager.DisplayMode = PagerDisplayMode.PreviousNextNumeric;
            sfPager.UseOnDemandPaging = true;
            sfPager.NumericButtonCount = 4;
            sfPager.PageSize = 6;
            listView = new SfListView();
            listView.LayoutManager = new GridLayout() { SpanCount = 2 };
            listView.ItemTemplate = new DataTemplate(() => 
            {
                var grid = new Grid();
                var image = new Image();
                image.SetBinding(Image.SourceProperty, new Binding("Image"));
                var label = new Label();
                label.SetBinding(Label.TextProperty, new Binding("Name"));
                var label1 = new Label();
                label1.SetBinding(Label.TextProperty, new Binding("Weight"));
                grid.Children.Add(image);
                grid.Children.Add(label);
                grid.Children.Add(label1);
                return grid;
            });
            stackLayout.Children.Add(listView);
            stackLayout.Children.Add(sfPager);
        }
    }
}

{% endhighlight %}
{% endtabs %}

{% highlight c# %}

public class SfListViewPagingBehavior : Behavior<ContentPage>
{

    private Syncfusion.ListView.XForms.SfListView listView;
    private PagingViewModel PagingViewModel;
    private SfDataPager dataPager;

    protected override void OnAttachedTo(ContentPage bindable)
    {
        listView = bindable.FindByName<Syncfusion.ListView.XForms.SfListView>("listView");
        dataPager = bindable.FindByName<SfDataPager>("dataPager");
        PagingViewModel = new PagingViewModel();
        listView.BindingContext = PagingViewModel;
        dataPager.Source = PagingViewModel.pagingProducts;
        dataPager.OnDemandLoading += DataPager_OnDemandLoading;
        base.OnAttachedTo(bindable);
    }

    private void DataPager_OnDemandLoading(object sender, OnDemandLoadingEventArgs e)
    {
        var source = PagingViewModel.pagingProducts.Skip(e.StartIndex).Take(e.PageSize);
        listView.ItemsSource = source.AsEnumerable();
    }

    protected override void OnDetachingFrom(ContentPage bindable)
    {
        listView = null;
        PagingViewModel = null;
        dataPager = null;
        base.OnDetachingFrom(bindable);
    }
}

{% endhighlight %}

Download the entire source code form GitHub [here](https://github.com/SyncfusionExamples/xamarin.forms-listview-paging).

![Xamarin.Forms listview with paging](SfListView_images/Paging.png)
 
## Loading data from SQLite online database

The SfListView allows binding the data from online database with the help of `Azure App Service`. To perform this, follow the steps:

Step 1: Get URL to store the data online.
Step 2: Create table using `AppServiceHelpers`.
Step 3: Populate the data into the table using the ObservableCollection `Items`.
Step 4: Bind it to SfListView using [SfListView.ItemSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemsSource) property.
Step 5: Refer to the following link to know more about working with `Azure App Service`.
        https://blog.xamarin.com/add-a-backend-to-your-app-in-10-minutes/ 

N> Install the following NuGet packages to successfully run the application:

* Microsoft.Azure.Mobile.Client(v.2.1.1)
* Microsoft.Azure.Mobile.Client.SQLiteStore(v.2.1.1)
* AppService.Helpers (Does not support UWP platform)
* AppService.Helpers.Forms (Does not support UWP platform)

Refer to the following code which illustrates, how to initialize the library with the URL of the Azure Mobile App and registering the Model with the client to create a table.

{% tabs %}
{% highlight c# %}
public App()
{
    InitializeComponent();
    IEasyMobileServiceClient client = new EasyMobileServiceClient();
    client.Initialize("http://xamarin-todo-sample.azurewebsites.net");
    client.RegisterTable<ToDo>();
    client.FinalizeSchema();
    MainPage = new NavigationPage(new Pages.ToDoListPage(client));
}
{% endhighlight %}
{% endtabs %}

Refer to the following code which illustrates, how to create a table using AppServiceHelpers and insert items in it.

{% tabs %}
{% highlight c# %}
using AppServiceHelpers.Abstractions;
using AppServiceHelpers.Models;
public class BaseAzureViewModel<T> : INotifyPropertyChanged where T : EntityData
{
    IEasyMobileServiceClient client;
    ITableDataStore<T> table;

    public BaseAzureViewModel(IEasyMobileServiceClient client)
    {
        this.client = client;
        table = client.Table<T>();
    }

    // Returns an ObservableCollection of all the items in the table
    ObservableCollection<T> items = new ObservableCollection<T>();
    public ObservableCollection<T> Items
    {
        get { return items; }
        set
        {
            items = value;
            OnPropertyChanged("items");
        }
    }

    // Adds an item to the table.
    public async Task AddItemAsync(T item)
    {
        await table.AddAsync(item);
    }

    // Deletes an item from the table.
    public async Task DeleteItemAsync(T item)
    {
        await table.DeleteAsync(item);
    }

    // Updates an item in the table.
    public async Task UpdateItemAsync(T item)
    {
        await table.UpdateAsync(item);
    }

    // Refresh the table and synchronize data with Azure.
    Command refreshCommand;
    public Command RefreshCommand
    {
        get { return refreshCommand ?? (refreshCommand = new Command(async () => await ExecuteRefreshCommand())); }
    }

    async Task ExecuteRefreshCommand()
    {
        if (IsBusy)
            return;

        IsBusy = true;

        try
        {
            var _items = await table.GetItemsAsync();
            Items.Clear();
            foreach (var item in _items)
            {
                Items.Add(item);
            }
            IsBusy = false;
        }
        catch (Exception ex)
        {
            await Application.Current.MainPage.DisplayAlert("Error", ex.Message, "OK");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;
    public void OnPropertyChanged(string propertyName)
    {
        if (PropertyChanged == null)
            return;

        PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
    }
}
{% endhighlight %}
{% endtabs %}

Refer to the following code which illustrates, how to bind the table contents into the SfListView.

{% tabs %}
{% highlight c# %}
public partial class ToDoListPage : ContentPage
{
  public ToDoListPage(IEasyMobileServiceClient client)
  {
    InitializeComponent();
    var viewModel = new ViewModels.ToDosViewModel(client);
    BindingContext = viewModel;
    listView.ItemsSource = viewModel.Items;
  }
  
  private void FetchButton_Clicked(object sender, EventArgs e)
  {
    var viewModel1 = (ToDosViewModel)BindingContext;
    viewModel1.RefreshCommand.Execute(null);
  }
}
{% endhighlight %}

{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <ContentPage.Content>
        <StackLayout>
            <syncfusion:SfListView x:Name="listView" SelectedItem="{Binding SelectedToDoItem, Mode=TwoWay}" ItemSize="50">
                <syncfusion:SfListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <StackLayout Orientation="Horizontal" HorizontalOptions="FillAndExpand" VerticalOptions="CenterAndExpand">
                                <Label Text="{Binding Text}" />
                                <Switch IsToggled="{Binding Completed}"/>
                            </StackLayout>
                        </ViewCell>
                    </DataTemplate>
                </syncfusion:SfListView.ItemTemplate>
            </syncfusion:SfListView>
            <Button Text="Add New" Command="{Binding AddNewItemCommand}"/>
            <Button Text="Fetch" Command="{Binding FetchItemCommand}" />
        </StackLayout>
    </ContentPage.Content>

</ContentPage>
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Loading-data-from-SQlite-online-database-from-xamarin.forms-listview-).

## Loading data from SQLite offline database

The SfListView allows binding the data from local database by using SQLite. To perform this, follow the steps: SQLiteConnection

Step 1: Create a `SQLite database table`
Step 2: Populate the data into the table
Step 3: Store them as an `IEnumerable` collection
Step 4: Bind it to SfListView using [SfListView.ItemSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemsSource) property.
Step 5: Refer to the following link to know how to create SQLite connection,
http://developer.xamarin.com/guides/xamarin-forms/working-with/databases/

N> To run this sample in UWP, install [sqLite.Net.Pcl](https://www.nuget.org/packages/sqlite-net-pcl), version v1.0.10 (Only this version of SQLite supports UWP platform, later versions don’t support UWP).

{% tabs %}
{% highlight c# %}
using SQLite;

public class OrderItem
{
    public int ID { get; set; }
    public string Name { get; set; }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
using SQLite;
  
public class ViewModel
{
    SQLiteConnection database;
    IEnumerable<OrderItem> orderItemCollection;
    public IEnumerable<OrderItem> OrderItemCollection
    {
        get
        {
            if (orderItemCollection == null)
                orderItemCollection = GetItems();
            return orderItemCollection;
        }
    }
    public ViewModel()
    {
        database = DependencyService.Get<ISQLite>().GetConnection();
        // Create the table
        database.CreateTable<OrderItem>();
  
        // Insert items into table
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1001,'Antony')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1002,'Blake')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1003,'Catherine')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1004,'Jude')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1005,'Mark')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1006,'Anderson')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1007,'Wilson')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1008,'Jade')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1009,'Zachery')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1010,'Dhotis')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1011,'Trunks')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1012,'Kevin')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1013,'Mathew')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1014,'Watson')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1015,'Chris')");
        database.Query<OrderItem>("INSERT INTO OrderItem (ID,Name)values (1016,'Phantom')");
    }
  
    public IEnumerable<OrderItem> GetItems()
    {
        // Changing the database table items as ObservableCollection
        var table = (from i in database.Table<OrderItem>() select i);
        ObservableCollection<OrderItem> OrderList = new ObservableCollection<OrderItem>();
        foreach (var order in table)
        {
            OrderList.Add(new OrderItem()
            {
                ID = order.ID,
                Name = order.Name
            });
        }
        return OrderList;
    }
}
{% endhighlight %}
{% endtabs %}

Refer to the following code which illustrates, how to bind the data from the SQLite database to SfListView.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <Grid>
            <listView:SfListView x:Name="listView" ItemSize="70" 
                                BackgroundColor="Teal"
                        ItemsSource="{Binding OrderItemCollection}">
                <listView:SfListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <ViewCell.View>
                                <Grid>
                                    <Grid.RowDefinitions>
                                        <RowDefinition Height="*" />
                                        <RowDefinition Height="1" />
                                    </Grid.RowDefinitions>
                                    <Grid>
                                        <Grid.ColumnDefinitions>
                                            <ColumnDefinition Width="*" />
                                            <ColumnDefinition Width="*" />
                                        </Grid.ColumnDefinitions>
                                        <Label LineBreakMode="NoWrap" Text="{Binding ID}" VerticalOptions="Center"/>
                                        <Label LineBreakMode="NoWrap" Text="{Binding Name}" Grid.Column="1" VerticalOptions="Center" />
                                    </Grid>
                                    <StackLayout Grid.Row="1" BackgroundColor="Gray" HeightRequest="1"/>
                                </Grid>
                            </ViewCell.View>
                        </ViewCell>
                    </DataTemplate>
                </listView:SfListView.ItemTemplate>
            </listView:SfListView>
        </Grid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Loading-data-from-SQlite-offline-database-from-xamarin.forms-listview-).

## ListView with Prism Framework

The SfListView allows the user to work with prism for MVVM Framework. Steps to be followed:

1. Replace your application to prism application in App.xaml file.
2. Inherit App.xaml.cs from prism application instead of your application.
3. Create a prism namespace library reference in xaml file of the ContentPage.
4. Connect view and view model instead of binding context by registering them.

{% tabs %}
{% highlight c# %}
public partial class App : PrismApplication
{
    public App(IPlatformInitializer initializer = null) : base(initializer) { }

    protected override void OnInitialized()
    {
        InitializeComponent();

    }

    protected override void RegisterTypes()
    {
        Container.RegisterTypeForNavigation<MainPage, MainPageViewModel>();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<prism:PrismApplication xmlns="http://xamarin.com/schemas/2014/forms"
                        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                        xmlns:prism="clr-namespace:Prism.Unity;assembly=Prism.Unity.Forms"
                        x:Class="ListViewPrism.App">
</prism:PrismApplication>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:prism="clr-namespace:Prism.Mvvm;assembly=Prism.Forms"
             xmlns:local="clr-namespace:ListViewPrism;assembly=ListViewPrism"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             x:Class="ListViewPrism.Views.MainPage"
             Title="MainPage">
    <StackLayout HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand">
        <syncfusion:SfListView x:Name="listView" ItemSize="70" ItemSpacing="0,0,5,0"
                             AutoFitMode="Height"
                             ItemsSource="{Binding ContactsInfo,}" IsStickyHeader="True" 
                             AllowSwiping="True" IsStickyGroupHeader="True" GroupHeaderSize="50">
        </syncfusion:SfListView>
    </StackLayout>
</ContentPage>    
{% endhighlight %}
{% endtabs %}

For more details, refer to [https://xamgirl.com/prism-in-xamarin-forms-step-by-step-part-1](https://xamgirl.com/prism-in-xamarin-forms-step-by-step-part-1).

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Using-xamarin.forms-listview-in-prism).

## Scrolling ListView without virtualization

ListView allows you to scroll by loading the entire collection of items inside the ScrollView and defining the total extend of its container to `HeightRequest` in the [Loaded](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event.

{% tabs %}
{% highlight xaml %}
<ScrollView>
   <sync:SfListView x:Name="listView" ItemsSource="{Binding BookInfo}" Loaded="listView_Loaded"/>
</ScrollView>
{% endhighlight %}
{% highlight C# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public partial class MainPage : ContentPage
{ 
	public MainPage()
	{
		InitializeComponent();
	}
 
	private void listView_Loaded(object sender, ListViewLoadedEventArgs e)
	{
		var container = listView.GetVisualContainer();
		var extent = (double)container.GetType().GetRuntimeProperties().FirstOrDefault(x => x.Name == "TotalExtent").GetValue(container);
		listView.HeightRequest = extent;
	}
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/How-to-load-xamarin.forms-listview-for-full-height-without-virtualization).

When ListView is in [AutoFitMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_AutoFitMode) as 'Height', the extend of the ListView will be updated only while scrolling. So you can resize the ListView in `VisualContainer` [PropertyChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.VisualContainer.html) method as like below.

{% tabs %}
{% highlight xaml %}
<ScrollView>
   <sync:SfListView x:Name="listView" AutoFitMode="Height" ItemsSource="{Binding BookInfo}" Loaded="listView_Loaded"/>
</ScrollView>
{% endhighlight %}
{% highlight C# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public partial class MainPage : ContentPage
{
    VisualContainer visualContainer;
    bool loaded;

    public MainPage()
    {
        InitializeComponent();
        visualContainer = listView.GetVisualContainer();
        visualContainer.PropertyChanged += VisualContainer_PropertyChanged;
    }

    private void VisualContainer_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
    {
        if (e.PropertyName == "Height" && listView.HeightRequest != visualContainer.Height && loaded)
            listView.HeightRequest = visualContainer.Height;
    }

    private void listView_Loaded(object sender, ListViewLoadedEventArgs e)
    {
        var extent = (double)visualContainer.GetType().GetRuntimeProperties().FirstOrDefault(x => x.Name == "TotalExtent").GetValue(visualContainer);
        listView.HeightRequest = extent;
        loaded = true;
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ListViewSample_(2)1126902862).

N> While loading in `AutoFitMode` make sure that the [ItemSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemSize) property value is not specified, to avoid extra space below the list. Update the size of the container after ListView loaded to render all the list items in the view.

The following limitations should be noted when using the previous approaches:

* As the entire list items are loaded inside the parent `ScrollView` element, the [ItemAppearing](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) and [ItemDisappearing](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) events will not be fired when scrolling.
* When performing keyboard navigation, the view cannot be scrolled automatically while navigating out of view.
* Scrolling through the touch action will be handled in all platforms and ListView scrolling will be handled by the parent ScrollView.


## Working with nested ListView
 
ListView allows you to load another ListView inside its [ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemTemplate). When the [AutoFitMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_AutoFitMode) of the outer ListView is height, the size of the inner ListView will be allocated from the maximum screen size. Since the exact size for the inner list cannot not be obtained before loading the view. 
 
To get a fixed height for the inner ListView, define a value in its `HeightRequest`. If the items inside the inner ListView are less, allocate the total extend of the inner list to its `HeightRequest`.
 
Follow the steps to set the size for the outer ListView based on the extend of inner ListView:

1. Define a property in the Model class and bind it to the HeightRequest of inner ListView, as the height for various inner ListView has to be identified while scrolling.
2. Hook the container's [PropertyChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.VisualContainer.html) event. When the height of the container changes, set the value of `TotalExtent` to the property bound to the HeightRequest.
3. Call the `RefreshView` method asynchronously with few seconds delay in the `Loaded` event of the outer SfListView. The height requested for each inner SfListView will be set but the outer SfListView will not get any notification regarding the size change. So, call the RefreshView method asynchronously after loading the view.

{% tabs %}
{% highlight xaml %}
 <listView:SfListView x:Name="listView"  ItemsSource="{Binding ContactInfo}" AutoFitMode="Height" Loaded="listView_Loaded" AllowGroupExpandCollapse="True">
    <listView:SfListView.ItemTemplate>
        <DataTemplate>
            <ViewCell>
                <ViewCell.View>
                    <Grid>
                        <local:ExtendedListView x:Name="list1" HeightRequest="{Binding InnerListHeight}" ItemsSource="{Binding ContactDetails}" ItemSize="75">
                            <local:ExtendedListView.ItemTemplate>
                                <DataTemplate>
                                    <StackLayout>
                                        <Image Source="{Binding Image}" />
                                        <Label Text="{Binding Name}" />
                                        <Label Text="{Binding Number}" />
                                    </StackLayout>
                                </DataTemplate>
                            </local:ExtendedListView.ItemTemplate>
                        </local:ExtendedListView>
                    </Grid>
                </ViewCell.View>
            </ViewCell>
        </DataTemplate>
    </listView:SfListView.ItemTemplate>
</listView:SfListView>
{% endhighlight %}
{% highlight C# %}
 public partial class NestedListView : ContentPage
{
    public NestedListView()
    {
        InitializeComponent();
    }

    private async void listView_Loaded(object sender, Syncfusion.ListView.XForms.ListViewLoadedEventArgs e)
    {
        await Task.Delay(2000);
        listView.RefreshView();
    }
}
{% endhighlight %}
{% endtabs %}

{% highlight C# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public class ExtendedListView : SfListView
{
    VisualContainer container;
    public ExtendedListView()
    {
        container = this.GetVisualContainer();
        container.PropertyChanged += Container_PropertyChanged;
    }
    
    private void Container_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
    {
        Device.BeginInvokeOnMainThread(async () =>
        {
            var extent = (double)container.GetType().GetRuntimeProperties().FirstOrDefault(container => container.Name == "TotalExtent").GetValue(container);
            if (e.PropertyName == "Height")
                (this.BindingContext as ContactInfo_NestedListView).InnerListHeight = extent;
        });
    }
}
{% endhighlight %}

 Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/xamarin-forms-listview-inside-another-listview).
 
## Rendering ListView when loading in different layouts

The options are as follows:

* Creates the measurement and layout similar to Xamarin.Forms ListView, when the ListView is loaded inside the layouts such as StackLayout, ScrollView, and Grid, in which the RowDefinition or ColumnDefinition is set to 'Auto'. In all other layouts, the ListView size will be allocated from the framework.
* Sets the value of total extend to the HeightRequest of ListView, since the scrolling will be handled by the parent ScrollView, when ListView is loaded inside the StackLayout with base parent as ScrollView having multiple elements inside the StackLayout.

## Dispose listview

You can dispose and release resources used by ListView by calling the [ListView.Dispose](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_Dispose().html) method.

{% tabs %}
{% highlight c# %}
protected override void OnDisappearing()  
{  
   listview.Dispose();  
   base.OnDisappearing();  
}
{% endhighlight %}
{% endtabs %}

## Refresh view

You can refresh the view by using the [RefreshView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_RefreshView) method. It will be used to refresh the items in the listview at runtime while updating the view.

{% tabs %}
{% highlight c# %} 
   listview.RefreshView();   
{% endhighlight %}
{% endtabs %}

## How to

### Swipe and move an item to another listview on swipe item tapped action

By using swipe view action, you can move an item from one listview to another listview.

{% tabs %}
{% highlight c# %}
private void FavoriteTapped(object obj)
{
    var departureInfo = obj as DepartureInfo;
    var pinnedInfo = FirstLVCollection.Any(o => o.Name == departureInfo.Name) ? FirstLVCollection.First(o => o.Name == departureInfo.Name) : null;
    if (pinnedInfo == null)
    {
        FirstLVCollection.Add(new PinnedInfo() { Name = departureInfo.Name, RouteName = departureInfo.Name, Icon = departureInfo.Icon, IsFavorite = true });
    }
}
{% endhighlight %}
{% endtabs %}

### Filter listview items based on another listview selection

To filter the listview items based on the item selection in another listview, use the SfListView.DataSource.Filter property.

{% tabs %}
{% highlight c# %}
private void ItemTapped(Syncfusion.ListView.XForms.ItemTappedEventArgs e)
{
    tappedPinedInfo = e.ItemData as PinnedInfo;
    if (tappedPinedInfo.IsFavorite)
    {
        secondLV.DataSource.Filter = FilterDepartures;
        tappedPinedInfo.IsFavorite = false;
    }
    else
    {
        secondLV.DataSource.Filter = null;
        tappedPinedInfo.IsFavorite = true;
    }
    secondLV.DataSource.RefreshFilter();
}

private bool FilterDepartures(object obj)
{
    var departureInfo = obj as DepartureInfo;
    if (tappedPinedInfo == null)
        return true;

    if (departureInfo.Name.ToLower().Contains(tappedPinedInfo.Name.ToLower())
            || departureInfo.RouteName.ToLower().Contains(tappedPinedInfo.RouteName.ToLower()))
        return true;
    else
        return false;
}
{% endhighlight %}
{% endtabs %}

 Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Filter-xamarin.forms-listview-based-on-swiped-items-in-another-listview).

## See also

[How to highlight the tapped view in ItemTemplate in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11235)                                                                                                                                                                                                                                                      
[How to access a named ListView inside a XAML DataTemplate in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11287)                                                                                                                                                  
[How to edit the ListView tapped item in Xamarin.Forms (SfListView) using DataForm](https://www.syncfusion.com/kb/11286)                                                                                                                                                                                            
[How to add or remove an item from Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11275)                                                                                                                                                                                    
[How to show Xamarin.Forms ListView (SfListView) in popup using Rg.Plugin.Popup framework](https://www.syncfusion.com/kb/11353)                                                                                                                                                                                                                                                                                                                                                                                             
[How to set the font size for Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11403)                                                                                                                                                                         
[How to improve performance when doing bulk changes in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11395/)                                                                                                                                                                                                                                                                                                                                                                                                           
[How to dispose of children of ListView in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11417/)                                                                                                                                                                                                                                                                                        
[How to make sound on tapping an item in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11687/)                                                                                                                                 
[How to apply the ListView item text color in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11699/)                                                                                                                                                                             
[How to share items source among Xamarin.Forms ListView with carousel page (SfListView)](https://www.syncfusion.com/kb/11789/)                                                                                                                                                                                                                                                          
[How to enable compiled binding for Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11807/)
