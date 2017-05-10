---
layout: post
title: Item Size Customization in SfListView
description: Describes the Item Size Customization in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Item Size Customization

This section explains about how to customize the item size in SfListView.

## Customize ItemSize of a particular item on demand

SfListView allows you to customize the size of item on demand by [SfListView.QueryItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~QueryItemSize_EV.html) event. This event is raised whenever items come to view. You can customize the size of a particular item on demand by using the item index.

### QueryItemSize

[SfListView.QueryItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~QueryItemSize_EV.html) is the event that returns item size on demand. This event is triggered with [QueryItemSizeEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html),

`SfListView.QueryItemSize` event provides the following properties in their arguments:

* [ItemIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemIndex.html) - This property helps you to identify a particular item in SfListView. 
* [ItemData](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemData.html) - This property helps you to identify a underlying data bounded to that item.
* [ItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemSize.html) - The size of the queried item. For vertical orientation, it will be considered as item height and for horizontal orientation, it will be considered as item width.
* [ItemType](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemType.html) - This property helps you to identify the item type of queried item.
* [Handled](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~Handled.html) - This property decides whether the specified size can be set to item or not. The default value is false. When this property is not set, the decided size is not set to the item.

The following code example illustrates how to hook the `SfListView.QueryItemSize` event and customize a item size in SfListView.

{% highlight c# %}
this.listView.QueryItemSize += ListView_QueryItemSize;

private void ListView_QueryItemSize(object sender, Syncfusion.ListView.XForms.QueryItemSizeEventArgs e)
{
    if(e.ItemIndex == 5)
    {
        e.ItemSize = 100;
        e.Handled = true;
    }
}
{% endhighlight %}

## Autofit the items based on content

SfListView allows you to dynamically adjust the size of items based on content loaded in the [SfListView.ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html) by defining the [SfListView.AutoFitMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AutoFitMode.html) property. SfListView has two types of AutoFitMode as listed below,

* Height - Autofit the item based on it's content and consider the height of the item when vertical [SfListView.Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Orientation.html). For horizontal orientation, consider the width of the item. If [SfListView.GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html), after autofit all items in a row, it will take the maximum item height in that row and applies to all other items in the row.
* None - SfListView items are layout by [SfListView.ItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemSize.html).

The following code example illustrates how to customize the item size based on content.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:local="clr-namespace:AutoFitItems;assembly=AutoFitItems"
             x:Class="AutoFitItems.MainPage">
             
  <ContentPage.BindingContext>
    <local:BookInfoRepository />
  </ContentPage.BindingContext>

  <syncfusion:SfListView x:Name="listView" 
                     ItemSize="200"
                     AutoFitMode="Height"
                     ItemsSource="{Binding BookInfo}">
    <sync:SfListView.ItemTemplate>
        <DataTemplate>
          <Grid RowSpacing="0" Padding="0,12,8,0" ColumnSpacing="0" Margin="0">
            <Grid.RowDefinitions>
              <RowDefinition Height="Auto" />
              <RowDefinition Height="1" />
            </Grid.RowDefinitions>
            <Grid RowSpacing="0" Padding="8,0,8,10">
              <Grid.RowDefinitions>
                <RowDefinition Height="Auto" />
              </Grid.RowDefinitions>
              <Grid.ColumnDefinitions>
                <ColumnDefinition Width="Auto" />
                <ColumnDefinition Width="Auto" />
              </Grid.ColumnDefinitions>
              <Image Source="{Binding AuthorImage}" Grid.Column="0" Grid.Row="0"
                   HeightRequest="80" WidthRequest="70"
                   HorizontalOptions="Start" VerticalOptions="Start" />
              <StackLayout Orientation="Vertical" Padding="5,-5,0,0" VerticalOptions="Start" Grid.Row="0" Grid.Column="1">
                <Label Text="{Binding BookName}" FontAttributes="Bold" FontSize="16" TextColor="#000000" />
                <Label Text="{Binding BookAuthor}" Grid.Row="1" FontSize="14"  Opacity=" 0.67" TextColor="#000000" />
                <Label Text="{Binding BookDescription}" Opacity=" 0.54" TextColor="#000000" FontSize="13"/>
              </StackLayout>
            </Grid>
          <BoxView Grid.Row="1" HeightRequest="1" Opacity="0.75" BackgroundColor="#CECECE" />
        </Grid>
      </DataTemplate>
    </sync:SfListView.ItemTemplate>
  </syncfusion:SfListView>                  
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.AutoFitMode = AutoFitMode.Height; 
{% endhighlight %}
{% endtabs %}

The following screenshot shows the output of Autofit items. You can download the entire source code of this demo from [here](http://files2.syncfusion.com/Xamarin.Forms/Samples/ListView_AutoFitItems.zip)

![](SfListView_images/AutofitItems.png)

## Limitations

* In Android, you need to set approximate size to [SfListView.ItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemSize.html) which matches calculated size of each items to avoid the reverse scrolling when scroll to end of SfListView.
* Need to specify the size of the image when you load image in the [SfListView.ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html) while define for item. If you measure the size of the template which loaded with image before layout the item, doesn't returns actual measured size. Hence, should specify the size to image.