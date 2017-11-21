---
layout: post
title: Load More in SfListView
description: Describes about the Load More behavior in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---
# Load More

SfListView lets you to enable Load More by setting [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) property and [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html) property. When the scrollbar reaches the end of the list, the Load More View will be displayed in the SfListView which provides an option to add the items at runtime. 

The `LoadMoreOption` property has three different modes of operation as listed below.
* None: Disables the load more button. This is the default value.
* Manual: Displays the load more button, when end of list is reached.
* Auto: Displays loading indicator, when end of list is reached.

## Load More Automatically

Load more items automatically when the scrollbar reaches the end of the list by setting [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) property is `Auto`. Add more items by [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html), it will be executed automatically.

The following code shows to load more items automatically in SfListView.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"
                 ItemSize="120"
                 LoadMoreOption="Auto"
                 LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                 ItemsSource="{Binding Products}"/>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.Auto;
listView.LoadMoreCommand = viewModel.LoadMoreItemsCommand;
{% endhighlight %}
{% endtabs %}

## Load More Manually

Enable manually to load more items by setting [SfListView.LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) property is `Manual`. The load more button will be displayed when scrollbar reaches the end of the list. Add more items by [SfListView.LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html), it will be executed only when tap the load more button. 

The following code shows to load more items manually in SfListView.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"
                 ItemSize="120"
                 LoadMoreOption="Manual"
                 LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                 ItemsSource="{Binding Products}"/>
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.Manual;
listView.LoadMoreCommand = viewModel.LoadMoreItemsCommand;
{% endhighlight %}
{% endtabs %}

## Show Loading Indicator

The [SfListView.LoadMoreIndicator](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LoadMoreIndicator.html) will be displayed when loading more items into the list. If [LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) is `Auto`, loading indicator will be displayed automatically whenever the scrollbar reaches the end of the list. If `LoadMoreOption` is `Manual`, the `LoadMoreIndicator` will be displayed when tap the load more button. 
   
The visibility of `LoadMoreIndicator` is changed by setting [SfListView.IsBusy](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsBusy.html) property to be `true` before load more items and set it to be `false` after loading the items. 

The following code example shows how to set indicator visibility using `IsBusy`.

{% highlight c# %}
private async void LoadMoreItems(object obj)
{
    var listview = obj as Syncfusion.ListView.XForms.SfListView;
    listview.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    listview.IsBusy = false;
}
{% endhighlight %}

## Customize Load More View

SfListView allows you to customize user interface(UI) of Load More view.

### Load More Button

To customize load more button by adding custom user interface(UI) in [SfListView.LoadMoreTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreTemplate.html) property. 

N> Must add the [InverseBoolConverter](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.Helpers.InverseBoolConverter.html) to disable the load more button for displaying the loading indicator.

The following code example shows how to customize load more button.

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

### Loading Indicator

To customize loading indicator by adding custom user interface(UI) in [SfListView.LoadMoreTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreTemplate.html) property.

N> You can customize only the color and height of [LoadMoreIndicator](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LoadMoreIndicator.html).

The following code example shows how to set the custom loading indicator.

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
                           ItemsSource="{Binding Products}">
        <syncfusion:SfListView.LoadMoreTemplate>
            <DataTemplate>
                <Grid>
                    <Label Text="Load More Items..." TextColor="Black" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" IsVisible="{Binding IsBusy, Converter={StaticResource inverseBoolConverter}}" />
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

## Disable Load More at Runtime

You can disable the Load More View by return value is `false` from  CanLoadMoreItems method of [LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html).

The following code example shows to disable the load more view if scrollbar reaches the maximum count (for example, totalItems = 22) in the list.

{% highlight c# %}
LoadMoreItemsCommand = new Command<object>(LoadMoreItems, CanLoadMoreItems);
private async void LoadMoreItems(object obj)
{
    var listview = obj as Syncfusion.ListView.XForms.SfListView;
    listview.IsBusy = true;
    await Task.Delay(2500);
    var index = Products.Count;
    var count = index + 3 >= totalItems ? totalItems - index : 3;
    AddProducts(index, count);
    listview.IsBusy = false;
}
private bool CanLoadMoreItems(object obj)
{
    if (Products.Count >= totalItems)
        return false;
    return true;
}
{% endhighlight %}

Refer the following output for load more items. You can download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Load_More978576440.zip).

![](SfListView_images/SfListView-LoadMore.gif)

## Limitations

SfListView does not support [LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html) in `Manual` mode, when the [Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.Orientation.html) is `Horizontal`.

