---
layout: post
title: Load More in Xamarin.Forms ListView | Syncfusion
description: Load more with manual and automatic loading options in Xamarin.Forms ListView which loads the Items in On-Demand.
platform: xamarin
control: SfListView
documentation: ug
---
# Load More in Xamarin ListView (SfListView)

The ListView enables `Load More` view by setting the [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreOption) and [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommand) properties. This can be displayed either on the top or bottom of the view by setting the [SfListView.LoadMorePosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LoadMorePosition.html) property. This view will be displayed when reaching the end of the list when the `LoadMorePosition` is bottom. This provides an option to add the items at runtime. If the `SfListView.LoadMorePosition` property is set as top, the items will be loaded only by using the `LoadMoreOption.Manual` mode.

The `SfListView.LoadMoreOption` property contains the following four different modes of operations:

 * None: Disables the load more button. This is the default value.
 * Manual: Displays the load more button when reaching the end of the list and execute `SfListView.LoadMoreCommand` when tapping the button.
 * Auto: Automatically execute the `SfListView.LoadMoreCommand` when reaching end of the list.
 * AutoOnScroll: Executes `SfListView.LoadMoreCommand` when users interact with listview and reach to the end of list.

The `SfListView.LoadMorePosition` property has two positions:

* Top: Positioned on the top of list.
* Bottom: Positioned on the bottom of list when reaching the end of the list. This is the default value.

`SfListView.LoadMoreCommand` executes when the listview is empty. This is the default behavior of `Manual` and `Auto`.

## Load more automatically

To automatically load more items using the [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommand) and [SfListView.LoadMoreCommandParameter](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommandParameter) when reaching end of the list, set the [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreOption) property as `Auto`.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView"
                 ItemSize="120"
                 LoadMoreOption="Auto"
                 LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                 LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                 ItemsSource="{Binding Products}"/>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.Auto;
listView.LoadMoreCommand = viewModel.LoadMoreItemsCommand;

//ViewModel.cs
LoadMoreItemsCommand = new Command<object>(LoadMoreItems, CanLoadMoreItems);

private bool CanLoadMoreItems(object obj)
{
    if (Products.Count >= totalItems)
        return false;
    return true;
}

private async void LoadMoreItems(object obj)
{
    var listView = obj as Syncfusion.ListView.XForms.SfListView;
    listView.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    listView.IsBusy = false;
}

private void AddProducts(int index, int count)
{
    for (int i = index; i < index + count; i++)
    {
        var name = Names[i];
        var p = new Product()
        {
            Name = name,
            Weight = Weights[i],
            Price = Prices[i],
            Image = ImageSource.FromResource("LoadMoreUG.LoadMore." + name.Replace(" ", string.Empty) + ".jpg")
        };
    
    Products.Add(p);
    }
}
{% endhighlight %}
{% endtabs %}

## Load more manually

To load more items manually using the [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommand) and [SfListView.LoadMoreCommandParameter](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommandParameter) when tapping the load more button at end of the list, set the [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreOption) property as `Manual`.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView"
                 ItemSize="120"
                 LoadMoreOption="Manual"
                 LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                 LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                 ItemsSource="{Binding Products}"/>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.Manual;
listView.LoadMoreCommand = viewModel.LoadMoreItemsCommand;

//ViewModel.cs
LoadMoreItemsCommand = new Command<object>(LoadMoreItems, CanLoadMoreItems);

private bool CanLoadMoreItems(object obj)
{
    if (Products.Count >= totalItems)
        return false;
    return true;
}

private async void LoadMoreItems(object obj)
{
    var listView = obj as Syncfusion.ListView.XForms.SfListView;
    listView.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    listView.IsBusy = false;
}

private void AddProducts(int index, int count)
{
    for (int i = index; i < index + count; i++)
    {
        var name = Names[i];
        var p = new Product()
        {
            Name = name,
            Weight = Weights[i],
            Price = Prices[i],
            Image = ImageSource.FromResource("LoadMoreUG.LoadMore." + name.Replace(" ", string.Empty) + ".jpg")
        };
    
    Products.Add(p);
    }
}
{% endhighlight %}
{% endtabs %}

## Load more when user interacts

To load more items only when users interact with the listview and reach to the end of list using `SfListView.LoadMoreCommand` and `SfListView.LoadMoreCommandParameter`, set the `SfListView.LoadMoreOption` property to [AutoOnScroll](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LoadMoreOption.html).

The `SfListView.LoadMoreCommand` will not execute when the listview is initially loaded. The `SfListView.LoadMoreCommand` will execute only when users interact and reach to the end of list.

The `SfListView.LoadMoreTemplate` is not displayed when the listview is initially loaded. When users interact, the `SfListView.LoadMoreTemplate` is displayed for the initially loaded items. Then, the visibility of `SfListView.LoadMoreTemplate` will be handled by the `CanExecute` method.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView"
                 ItemSize="120"
                 LoadMoreOption="AutoOnScroll"
                 LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                 LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                 ItemsSource="{Binding Products}"/>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.AutoOnScroll;
listView.LoadMoreCommand = viewModel.LoadMoreItemsCommand;

//ViewModel.cs
LoadMoreItemsCommand = new Command<object>(LoadMoreItems, CanLoadMoreItems);

/// <summary>
/// When AutoOnScroll load more is enabled, the CanExecute method will be called only when the user interacts and reach to the end of list.
/// Based on return value, the visibility of the LoadMoreTemplate is handled and the Execute method is called.
/// </summary>
/// <param name="obj">ListView is passed as default parameter.</param>
/// <returns>Returns true if the list has items to load, else returns false.</returns>
private bool CanLoadMoreItems(object obj)
{
    if (Products.Count >= totalItems)
        return false;
    return true;
}

/// <summary>
/// The Execute method is called based on the return value of the CanExecute method. If CanExecute returns false, the Execute method will not be executed.
/// </summary>
/// <param name="obj">ListView is passed as default parameter.</param>
private async void LoadMoreItems(object obj)
{
    var listView = obj as Syncfusion.ListView.XForms.SfListView;

    //Enables LoadMoreIndicator to the LoadMoreTemplate.
    listView.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;

    //Adding the items to the list.
    AddProducts(index, count);

    //Disables LoadMoreIndicator after adding the items.
    listView.IsBusy = false;
}

private void AddProducts(int index, int count)
{
    for (int i = index; i < index + count; i++)
    {
        var name = Names[i];
        var p = new Product()
        {
            Name = name,
            Weight = Weights[i],
            Price = Prices[i],
            Image = ImageSource.FromResource("LoadMoreUG.LoadMore." + name.Replace(" ", string.Empty) + ".jpg")
        };
    
    Products.Add(p);
    }
}
{% endhighlight %}
{% endtabs %}

## Show loading indicator

The [SfListView.LoadMoreIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LoadMoreIndicator.html) will be displayed when loading more items in the list.

By using the [SfListView.IsBusy](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_IsBusy) property, you can interchange the visibility of the button and busy indicator when creating the load more view. You can set the value of the `SfListView.IsBusy` property to `true` before adding items to the list and set it to `false`, after adding the items. You can also bind the `IsBusy` property through ViewModel.

{% tabs %}
{% highlight c# %}
private async void LoadMoreItems(object obj)
{
    var listView = obj as Syncfusion.ListView.XForms.SfListView;
    listView.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    listView.IsBusy = false;
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/xamarin-listview-loadmore).

Items can be loaded either on the top or bottom of the view.

![Xamarin.Forms listview load more on scrolling at bottom](SfListView_images/SfListView-LoadMore.gif)

![Xamarin.Forms listview load more on scrolling at top](SfListView_images/SfListView-TopLoadMore.gif)

## Load more view customization

The SfListView allows customizing User Interface(UI) of `Load More` view.

### Load more button

To customize the load more button, add the custom UI in the [SfListView.LoadMoreTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreTemplate) property. 

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="Sample.MainPage"
             xmlns:helper="clr-namespace:Syncfusion.ListView.XForms.Helpers;assembly=Syncfusion.SfListView.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <ContentPage.BindingContext>
        <local:LoadMoreViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Resources>
        <ResourceDictionary>
            <helper:InverseBoolConverter x:Key="inverseBoolConverter"/>
        </ResourceDictionary>
    </ContentPage.Resources>
    <syncfusion:SfListView x:Name="listView" 
                           ItemSize="120"
                           LoadMoreOption="Manual"
                           LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                           LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                           ItemsSource="{Binding Products}">
        <syncfusion:SfListView.LoadMoreTemplate>
            <DataTemplate>
                <Grid>
                    <Label Text="Load More Items..." TextColor="Black" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" IsVisible="{Binding IsBusy, Converter={StaticResource inverseBoolConverter}, Source={x:Reference Name=listView}}" />
                </Grid>
            </DataTemplate>
        </syncfusion:SfListView.LoadMoreTemplate>
    </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreTemplate = new DataTemplate(() =>
{
    var grid = new Grid();
    var label = new Label
    {
        Text = "Load More Items...",
        FontSize = 20,
        BackgroundColor = Color.AliceBlue,
        HorizontalTextAlignment = TextAlignment.Center,
        VerticalTextAlignment = TextAlignment.Center
    };
    label.SetBinding(Label.IsVisibleProperty, new Binding("IsBusy", BindingMode.Default, new InverseBoolConverter(), null, null, listView));
    grid.Children.Add(label);
    return grid;
});
{% endhighlight %}
{% endtabs %}

### Loading Indicator

To customize the loading indicator, add the custom UI in the [SfListView.LoadMoreTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreTemplate) property.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="Sample.MainPage"
             xmlns:helper="clr-namespace:Syncfusion.ListView.XForms.Helpers;assembly=Syncfusion.SfListView.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <ContentPage.BindingContext>
        <local:LoadMoreViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Resources>
        <ResourceDictionary>
            <helper:InverseBoolConverter x:Key="inverseBoolConverter"/>
        </ResourceDictionary>
    </ContentPage.Resources>
    <syncfusion:SfListView x:Name="listView" 
                           ItemSize="120"
                           LoadMoreOption="Manual"
                           LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                           LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                           ItemsSource="{Binding Products}">
        <syncfusion:SfListView.LoadMoreTemplate>
            <DataTemplate>
                <Grid>
                    <Label Text="Load More Items" TextColor="Black" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" IsVisible="{Binding IsBusy, Converter={StaticResource inverseBoolConverter}, Source={x:Reference Name=listView}}" />
                    <syncfusion:LoadMoreIndicator IsRunning="{Binding IsBusy, Source={x:Reference Name=listView}}" IsVisible="{Binding IsBusy, Source={x:Reference Name=listView}}" Color="Red" VerticalOptions="Center"/>                             
                </Grid>
            </DataTemplate>
        </syncfusion:SfListView.LoadMoreTemplate>
    </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreTemplate = new DataTemplate(() =>
{
    var grid = new Grid();
    var label = new Label
    {
        Text = "Load More Items...",
        FontSize = 20,
        BackgroundColor = Color.AliceBlue,
        HorizontalTextAlignment = TextAlignment.Center,
        VerticalTextAlignment = TextAlignment.Center
    };
    label.SetBinding(Label.IsVisibleProperty, new Binding("IsBusy", BindingMode.Default, new InverseBoolConverter(), null, null, listView));
    var loadMoreIndicator = new LoadMoreIndicator();
    loadMoreIndicator.Color = Color.Red;
    loadMoreIndicator.VerticalOptions = LayoutOptions.Center;
    loadMoreIndicator.SetBinding(LoadMoreIndicator.IsRunningProperty, new Binding("IsBusy", BindingMode.Default, null, null,null, listView));
    loadMoreIndicator.SetBinding(LoadMoreIndicator.IsVisibleProperty, new Binding("IsBusy", BindingMode.Default, null, null, null, listView));
    grid.Children.Add(label);
    grid.Children.Add(loadMoreIndicator);
    return grid;
});
{% endhighlight %}
{% endtabs %}

### Customize the size of load more view and indicator

ListView allows customizing the size of the load more item by the [SfListView.QueryItemSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event using the item type. 

{% tabs %}
{% highlight c# %}
this.listView.QueryItemSize += ListView_QueryItemSize;

private void ListView_QueryItemSize(object sender, Syncfusion.ListView.XForms.QueryItemSizeEventArgs e)
{
    if(e.ItemType == ItemType.LoadMore)
    {
        e.ItemSize = 300;
        e.Handled = true;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the size of the loading indicator, add the custom UI to the [SfListView.LoadMoreTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreTemplate) property and assign the height and width for the grid and loading indicator.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="Sample.MainPage"
             xmlns:helper="clr-namespace:Syncfusion.ListView.XForms.Helpers;assembly=Syncfusion.SfListView.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <ContentPage.BindingContext>
        <local:LoadMoreViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Resources>
        <ResourceDictionary>
            <helper:InverseBoolConverter x:Key="inverseBoolConverter"/>
        </ResourceDictionary>
    </ContentPage.Resources>
    <syncfusion:SfListView x:Name="listView" 
                           ItemSize="120"
                           LoadMoreOption="Manual"
                           LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                           LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                           ItemsSource="{Binding Products}">
        <syncfusion:SfListView.LoadMoreTemplate>
            <DataTemplate>
                <Grid HeightRequest="100" WidthRequest="100">
                    <Label Text="Load More Items" TextColor="Black" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" IsVisible="{Binding IsBusy, Converter={StaticResource inverseBoolConverter}, Source={x:Reference Name=listView}}" />
                    <syncfusion:LoadMoreIndicator IsRunning="{Binding IsBusy, Source={x:Reference Name=listView}}" IsVisible="{Binding IsBusy, Source={x:Reference Name=listView}}" Color="Red" VerticalOptions="Center" HeightRequest="100" WidthRequest="100"/>                             
                </Grid>
            </DataTemplate>
        </syncfusion:SfListView.LoadMoreTemplate>
    </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreTemplate = new DataTemplate(() =>
{
    var grid = new Grid();
    grid.HeightRequest = 100;
    grid.WidthRequest = 100;
    var label = new Label
    {
        Text = "Load More Items...",
        FontSize = 20,
        BackgroundColor = Color.AliceBlue,
        HorizontalTextAlignment = TextAlignment.Center,
        VerticalTextAlignment = TextAlignment.Center
    };
    label.SetBinding(Label.IsVisibleProperty, new Binding("IsBusy", BindingMode.Default, new InverseBoolConverter(), null, null, listView));
    var loadMoreIndicator = new LoadMoreIndicator();
    loadMoreIndicator.Color = Color.Red;
    loadMoreIndicator.VerticalOptions = LayoutOptions.Center;
    loadMoreIndicator.SetBinding(LoadMoreIndicator.IsRunningProperty, new Binding("IsBusy", BindingMode.Default, null, null,null, listView));
    loadMoreIndicator.SetBinding(LoadMoreIndicator.IsVisibleProperty, new Binding("IsBusy", BindingMode.Default, null, null, null, listView));
    loadMoreIndicator.HeightRequest = 100;
    loadMoreIndicator.WidthRequest = 100;
    grid.Children.Add(label);
    grid.Children.Add(loadMoreIndicator);
    return grid;
});
{% endhighlight %}
{% endtabs %}

## Disable load more at runtime

To disable the `Load More` view, return the 'CanExecute' method of the [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommand) to `false`.

If you reach maximum count (for example, totalItems = 22) in the list, follow the code example to disable the `Load More` view.

{% tabs %}
{% highlight c# %}
LoadMoreItemsCommand = new Command<object>(LoadMoreItems, CanLoadMoreItems);

private async void LoadMoreItems(object obj)
{
    var listView = obj as Syncfusion.ListView.XForms.SfListView;
    listView.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    listView.IsBusy = false;
}
private bool CanLoadMoreItems(object obj)
{
    if (Products.Count >= totalItems)
        return false;
    return true;
}
{% endhighlight %}
{% endtabs %}


## Limitations

* Must set minimum delay for `LoadMore` in Execute method.
* SfListView does not support to set `Manual` in [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreOption) when [SfListView.Orientation](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.Orientation.html) is `Horizontal`.
* SfListView supports to set `Auto` and `AutoOnScroll` in `SfListView.LoadMoreOption` only when `SfListView.LoadMorePosition` is set to `Bottom`.
* Handle [LoadMoreCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommand) execution by implementing `CanExecute` predicate of command. 

## How to

### Load more on infinite scroll 

The SfListView allows adding more items infinite times either manually or automatically. 

{% tabs %}
{% highlight c# %}
public class LoadMoreViewModel:INotifyPropertyChanged
{
  public ObservableCollection<Product> Products { get; set; }
  public Command<object> LoadMoreItemsCommand { get; set; }

  public LoadMoreViewModel()
  {
     Products = new ObservableCollection<Product>();
     AddProducts(0, 10);
     LoadMoreItemsCommand = new Command<object>(LoadMoreItems);
  }
  private async void LoadMoreItems(object obj)
  {
     var listview = obj as Syncfusion.ListView.XForms.SfListView;
     listview.IsBusy = true;
     await Task.Delay(2500);
     AddProducts(11, 21);
     listview.IsBusy = false;
  }
  private void AddProducts(int value, int count)
  {
     Random rand= new Random();
     for (int i = value; i < count; i++)
     {
        var name = Names[rand.Next(1,22)];
        var p = new Product()
        {
           Name = name,
           Weight = Weights[i],
           Price = Prices[i],
           Image = ImageSource.FromResource("LoadMoreUG.LoadMore." + name.Replace(" ", string.Empty) + ".jpg")
        };
        Products.Add(p);
     }
  }
}
{% endhighlight %}
{% endtabs %}

Download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/Load-more-items-on-infinite-scroll-in-xamarin.forms-listview).

### Load more items automatically from up direction

The SfListView allows loading more items automatically when reaching top of the list by showing the busy indicator by loading in the [HeaderTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HeaderTemplate).

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
   <syncfusion:SfListView x:Name="ListView" IsBusy="True" 
                        ItemsSource="{Binding Messages}" 
                        AutoFitMode="Height">
        <syncfusion:SfListView.HeaderTemplate>
            <DataTemplate>
            <ViewCell>
                <Grid>
                <syncfusion:LoadMoreIndicator Color="Red" IsRunning="True" IsVisible="{Binding IndicatorIsVisible}"/>
                </Grid>
            </ViewCell>
            </DataTemplate>
        </syncfusion:SfListView.HeaderTemplate>
    </syncfusion:SfListView>
</ContentPage
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
  MainPageViewModel ViewModel;
  public MainPage()
  {
    InitializeComponent();
    ViewModel = new MainPageViewModel();
    ListView.IsBusy = true;
    ListView.ItemsSource = ViewModel.Messages;
    ListView.AutoFitMode = AutoFitMode.Height;
    ListView.HeaderTemplate = new DataTemplate(() =>
    {
      var grid = new Grid();
      var loadMoreIndicator = new LoadMoreIndicator()
      {
        Color = Color.Red,
        IsRunning = true
      };
      loadMoreIndicator.SetBinding(LoadMoreIndicator.IsVisibleProperty, new Binding("IndicatorIsVisible"));
      grid.Children.Add(loadMoreIndicator);
      return grid;
    });
  }
}
{% endhighlight %}
{% endtabs %}

Insert each new item in the 0th position of the underlying collection bound to the `SfListView.ItemsSource` property.

{% tabs %}
{% highlight c# %}
using Syncfusion.ListView.XForms.Control.Helpers;
public partial class MainPage : ContentPage
{
  MainPageViewModel ViewModel;
  VisualContainer visualContainer;
  public bool isScrolled;
  HeaderItem headerItem;

  public MainPage()
  {
    InitializeComponent();
    ViewModel = new MainPageViewModel();
    BindingContext = ViewModel;
    ViewModel.ListView = this.ListView;
    ListView.Loaded += ListView_Loaded;
    visualContainer = ListView.GetVisualContainer();
  }

  private void HeaderItem_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
  {
    if(e.PropertyName=="Visibility")
    {
      if (headerItem.Visibility && isScrolled)
        LoadMoreOnTop();
    }
  }
        
  private async void LoadMoreOnTop()
  {
    //To get the current first item which is visible in the View.
    var firstItem = ListView.DataSource.DisplayItems[0];
    ViewModel.IndicatorIsVisible = true;
    await Task.Delay(4000);
    var r = new Random();

    //To avoid layout calls for arranging each and every items to be added in the View. 
    ListView.DataSource.BeginInit();
    for (int i = 0; i < 5; i++)
    {
      var collection = new Message();
      collection.Text = ViewModel.MessageText[r.Next(0, ViewModel.MessageText.Count() - 1)];
      collection.IsIncoming = i % 2 == 0 ? true : false;
      collection.MessageDateTime = DateTime.Now.ToString();
      ViewModel.Messages.Insert(0, collection);
    }
    ListView.DataSource.EndInit();

    var firstItemIndex = ListView.DataSource.DisplayItems.IndexOf(firstItem);
    var header = (ListView.HeaderTemplate != null && !ListView.IsStickyHeader) ? 1 : 0;
    var totalItems = firstItemIndex + header;
            
    //Need to scroll back to previous position else the ScrollViewer moves to top of the list.
    ListView.LayoutManager.ScrollToRowIndex(totalItems, true);
    ViewModel.IndicatorIsVisible = false;
  }

  private void ListView_Loaded(object sender, Syncfusion.ListView.XForms.ListViewLoadedEventArgs e)
  {
    //To avoid loading items initially when page loaded.
    if (!isScrolled)
      (ListView.LayoutManager as LinearLayout).ScrollToRowIndex(ViewModel.Messages.Count - 1, true);
    headerItem = visualContainer.Children[0] as HeaderItem;
    headerItem.PropertyChanged += HeaderItem_PropertyChanged;
    isScrolled = true;
  }
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/load-more-automatic-up-direction-listview-xamarin)

![Loadmore automatic](SfListView_images/SfListView-LoadMoreAutomaticallyUpDirection.png)

### Load more items manually from up direction

The SfListView allows loading more items when tapping the button loaded in the [HeaderTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HeaderTemplate) when reaching top of the list and shows the busy indicator till the items are added into the collection.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
<syncfusion:SfListView x:Name="ListView"  IsBusy="True"
                       ItemTemplate="{StaticResource MessageTemplateSelector}" 
                       ItemsSource="{Binding Messages}"
                       ItemSize="100">
  <syncfusion:SfListView.HeaderTemplate>
    <DataTemplate>
      <ViewCell>
        <Grid>
          <Grid BackgroundColor="#d3d3d3" IsVisible="{Binding GridIsVisible}">
            <Button Text="Load More" Clicked="Button_Clicked" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand"/>
          </Grid>
          <syncfusion:LoadMoreIndicator Color="Red" IsRunning="True" IsVisible="{Binding IndicatorIsVisible}"/>
        </Grid>
      </ViewCell>
    </DataTemplate>
  </syncfusion:SfListView.HeaderTemplate>
</syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
  MainPageViewModel ViewModel;
  public MainPage()
  {
    InitializeComponent();
    ViewModel = new MainPageViewModel();
    ListView.IsBusy = true;
    ListView.ItemsSource = ViewModel.Messages;
    ListView.AutoFitMode = AutoFitMode.Height;
    ListView.HeaderTemplate = new DataTemplate(() =>
    {
      var grid = new Grid();
      grid.BackgroundColor = Color.FromHex("#d3d3d3");
      grid.SetBinding(Grid.IsVisibleProperty, new Binding("GridIsVisible"));
      var loadMore = new Button()
      {
        HorizontalOptions = LayoutOptions.CenterAndExpand,
        VerticalOptions = LayoutOptions.CenterAndExpand,
        Text = "LoadMore",
      };
      loadMore.Clicked += Button_Clicked;
      grid.Children.Add(loadMore);
      var grid1 = new Grid();
      var loadMoreIndicator = new LoadMoreIndicator()
      {
        Color = Color.Red,
        IsRunning = true
      };
      loadMoreIndicator.SetBinding(LoadMoreIndicator.IsVisibleProperty, new Binding("IndicatorIsVisible"));
      grid1.Children.Add(loadMoreIndicator);
      grid1.Children.Add(grid);
      return grid1;
    });
  }
}
{% endhighlight %}
{% endtabs %}

Insert each new item in the 0th position of the underlying collection bound to the `SfListView.ItemsSource` property.

{% tabs %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
  MainPageViewModel ViewModel;
  VisualContainer visualContainer;

  public MainPage()
  {
    InitializeComponent();
    ViewModel = new MainPageViewModel();
    BindingContext = ViewModel;
    ViewModel.ListView = this.ListView;
    ListView.Loaded += ListView_Loaded;
  }

  private void ListView_Loaded(object sender, Syncfusion.ListView.XForms.ListViewLoadedEventArgs e)
  {
    (ListView.LayoutManager as LinearLayout).ScrollToRowIndex(ViewModel.Messages.Count - 1, true);
  }

  private async void Button_Clicked(object sender, EventArgs e)
  {
    //To get the current first item which is visible in the View.
    var firstItem = ListView.DataSource.DisplayItems[0];
    ViewModel.GridIsVisible = false;
    ViewModel.IndicatorIsVisible = true;
    await Task.Delay(2000);
    var r = new Random();

    //To avoid layout calls for arranging each and every items to be added in the View. 
    ListView.DataSource.BeginInit();
    for (int i = 0; i < 5; i++)
    {
      var collection = new Message();
      collection.Text = ViewModel.MessageText[r.Next(0, ViewModel.MessageText.Count() - 1)];
      collection.IsIncoming = i % 2 == 0 ? true : false;
      collection.MessageDateTime = DateTime.Now.ToString();
      ViewModel.Messages.Insert(0, collection);
    }
    ListView.DataSource.EndInit();
    var firstItemIndex = ListView.DataSource.DisplayItems.IndexOf(firstItem);
    var header = (ListView.HeaderTemplate != null && !ListView.IsStickyHeader) ? 1 : 0;
    var totalItems = firstItemIndex + header;

    //Need to scroll back to previous position else the ScrollViewer moves to top of the list.
    ListView.LayoutManager.ScrollToRowIndex(totalItems, true);
    ViewModel.GridIsVisible = true;
    ViewModel.IndicatorIsVisible = false;
  }
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Xamarin-ListView-LoadMore-Upwards).

![Loadmore manual](SfListView_images/SfListView-LoadMoreManuallyUpDirection.jpg)

### How to disable LoadMoreCommand execution when ListView is Empty?

You can skip the load more action by checking the underlying collection count in the execute method.

{% highlight c# %}
//ViewModel.cs
LoadMoreItemsCommand = new Command<object>(LoadMoreItems, CanLoadMoreItems);

private bool CanLoadMoreItems(object obj)
{
    if (Products.Count >= totalItems)
        return false;
    return true;
}

private async void LoadMoreItems(object obj)
{
    if (Products.Count == 0)
        return;
    var listView = obj as Syncfusion.ListView.XForms.SfListView;
    listView.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    listView.IsBusy = false;
}

private void AddProducts(int index, int count)
{
    for (int i = index; i < index + count; i++)
    {
        var name = Names[i];
        var p = new Product()
        {
            Name = name,
            Weight = Weights[i],
            Price = Prices[i],
            Image = ImageSource.FromResource("LoadMoreUG.LoadMore." + name.Replace(" ", string.Empty) + ".jpg")
        };
        Products.Add(p);
    }
}
{% endhighlight %}

Download the GitHub sample from GitHub [here](https://github.com/SyncfusionExamples/How-to-disable-LoadMoreCommand-execution-when-ListView-is-Empty)

## See Also

[How to enable load more after loading in Xamarin.Forms listview](https://www.syncfusion.com/kb/9953/)                                                                           
[How to load more items in upward direction manually using button click](https://www.syncfusion.com/kb/8679/)
[How to load more items in upward direction automatically when reaching the top of the list](https://www.syncfusion.com/kb/8678/)                                                                                                                                                                      
[How to load more items when scroll reached the end of list](https://www.syncfusion.com/kb/7792/)                                                                                                                                                                                                              
