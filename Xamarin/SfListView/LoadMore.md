---
layout: post
title: Load More in SfListView
description: Describes about the Load More behavior in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---
# Load More

The SfListView enables `Load More` view by setting the [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html), [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html) and the [IsBusy](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsBusy.html) properties. The `Load More` view will be display when end of the list is reached and provides option to add the items at runtime.

The `LoadMoreOption` property has three different modes of operation listed as follows:

 * None: Disables the load more button. This is the default value.
 * Manual: Displays the load more button when end of the list is reached and execute `LoadMoreCommand` when button is tapped.
 * Auto: Automatically execute the `LoadMoreCommand` when end of the list is reached.

## Load more automatically

To automatically load more items using the [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html) and [LoadMoreCommandParameter](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommandParameter.html) while reaching end of the list, set the [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) property as `Auto`.

To load more items automatically, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"
                 ItemSize="120"
                 LoadMoreOption="Auto"
                 LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                 LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                 IsBusy="{Binding IsBusy}"
                 ItemsSource="{Binding Products}"/>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.Auto;
listView.LoadMoreCommand = viewModel.LoadMoreItemsCommand;
listView.SetBinding(SfListView.IsBusyProperty, new Binding("IsBusy"));

//ViewModel.cs
private bool isBusy;
public bool IsBusy
{
   get { return isBusy; }
   set
   {
       this.isBusy = value;
       RaisePropertyChanged("IsBusy");
   }
}
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
    IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    IsBusy = false;
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

To load more items manually using the [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html) and [LoadMoreCommandParameter](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommandParameter.html) while tapping on the load more button at end of the list, set the [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) property as `Manual`.

To load more items manually, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"
                 ItemSize="120"
                 LoadMoreOption="Manual"
                 LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                 LoadMoreCommandParameter="{Binding Source={x:Reference listView}}"
                 IsBusy="{Binding IsBusy}"
                 ItemsSource="{Binding Products}"/>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.Manual;
listView.LoadMoreCommand = viewModel.LoadMoreItemsCommand;
listView.SetBinding(SfListView.IsBusyProperty, new Binding("IsBusy"));

//ViewModel.cs
private bool isBusy;
public bool IsBusy
{
   get { return isBusy; }
   set
   {
       this.isBusy = value;
       RaisePropertyChanged("IsBusy");
   }
}

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
    IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    IsBusy = false;
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

The [SfListView.LoadMoreIndicator](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LoadMoreIndicator.html) will be displayed when loading more items into the list. Before loading more items, change the visibility of `LoadMoreIndicator` by setting the [SfListView.IsBusy](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsBusy.html) property to `true`. After loading more items, reset to `false`. 

To set indicator visibility using `IsBusy` property, follow the code example:

{% highlight c# %}
private async void LoadMoreItems(object obj)
{
    var listView = obj as Syncfusion.ListView.XForms.SfListView;
    IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    IsBusy = false;
}
{% endhighlight %}

Download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/LoadMoreUG978011112).

Refer to the following output to load more items:

![](SfListView_images/SfListView-LoadMore.gif)

## Load more view customization

The SfListView allows customizing user interface(UI) of `Load More` view.

### Load more button

To customize the load more button, add the custom user interface(UI) in the [SfListView.LoadMoreTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreTemplate.html) property. 

To customize the load more button, follow the code example:

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
                           IsBusy="{Binding IsBusy}"
                           ItemsSource="{Binding Products}">
        <syncfusion:SfListView.LoadMoreTemplate>
            <DataTemplate>
                <Grid>
                    <Label Text="Load More Items..." TextColor="Black" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" IsVisible="{Binding IsBusy, Converter={StaticResource inverseBoolConverter}}" />
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
    label.SetBinding(Label.IsVisibleProperty, new Binding("IsBusy", BindingMode.Default, new InverseBoolConverter()));
    grid.Children.Add(label);
    return grid;
});
{% endhighlight %}
{% endtabs %}

### Loading indicator

To customize the loading indicator, add the custom user interface(UI) in the [SfListView.LoadMoreTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreTemplate.html) property.

To set the custom loading indicator, follow the code example:

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
                           IsBusy="{Binding IsBusy}"
                           ItemsSource="{Binding Products}">
        <syncfusion:SfListView.LoadMoreTemplate>
            <DataTemplate>
                <Grid>
                    <Label Text="Load More Items" TextColor="Black" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" IsVisible="{Binding IsBusy, Converter={StaticResource inverseBoolConverter}}" />
                    <syncfusion:LoadMoreIndicator IsRunning="{Binding IsBusy}" IsVisible="{Binding IsBusy}" Color="Red" VerticalOptions="Center"/>                             
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
    label.SetBinding(Label.IsVisibleProperty, new Binding("IsBusy", BindingMode.Default, new InverseBoolConverter()));
    var loadMoreIndicator = new LoadMoreIndicator();
    loadMoreIndicator.Color = Color.Red;
    loadMoreIndicator.VerticalOptions = LayoutOptions.Center;
    loadMoreIndicator.SetBinding(LoadMoreIndicator.IsRunningProperty, new Binding("IsBusy"));
    loadMoreIndicator.SetBinding(LoadMoreIndicator.IsVisibleProperty, new Binding("IsBusy"));
    grid.Children.Add(label);
    grid.Children.Add(loadMoreIndicator);
    return grid;
});
{% endhighlight %}
{% endtabs %}

## Disable load more at runtime

To disable the `Load More` view, return 'CanExecute' method of the [LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html) to `false`.

If you reach maximum count (for example, totalItems = 22) in the list, follow the code example to disable the `Load More` view:

{% highlight c# %}
LoadMoreItemsCommand = new Command<object>(LoadMoreItems, CanLoadMoreItems);

private async void LoadMoreItems(object obj)
{
    var listView = obj as Syncfusion.ListView.XForms.SfListView;
    IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    IsBusy = false;
}
private bool CanLoadMoreItems(object obj)
{
    if (Products.Count >= totalItems)
        return false;
    return true;
}
{% endhighlight %}


## Limitation

The SfListView does not support the [LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) in `Manual` mode when the [Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.Orientation.html) is `Horizontal`.

## How to

### Load more on Infinite scroll 

SfListView allow you to add more items infinite times either manually or automatically. 

To make infinite scroll, follow the code example.

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
     IsBusy = true;
     await Task.Delay(2500);
     AddProducts(11, 21);
     IsBusy = false;
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

You can download the entire sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/LoadMore_Infinitescroll423993966).