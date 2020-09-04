---
layout: post
title: Item Size Customization in Syncfusion ListView
description: Describes the Item Size Customization in SfListView using ItemSize property, QueryItemSize event and AutoFitMode property.
platform: xamarin
control: SfListView
documentation: ug
---

# Item Size Customization in Xamarin ListView (SfListView)

This section explains how to customize the item size in the SfListView.

## Customize item size of a particular item on-demand

The SfListView allows customizing the size of the item on-demand by the [SfListView.QueryItemSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event using the item index. This event is raised whenever items come to view and triggered with [QueryItemSizeEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html).

The `SfListView.QueryItemSize` event provides the following properties in their arguments:

 * [ItemIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html#Syncfusion_ListView_XForms_QueryItemSizeEventArgs_ItemIndex): Identifies a particular item in the SfListView. 
 * [ItemData](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html#Syncfusion_ListView_XForms_QueryItemSizeEventArgs_ItemData): Identifies the underlying data bound to that item.
 * [ItemSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html#Syncfusion_ListView_XForms_QueryItemSizeEventArgs_ItemSize): Identifies size of the queried item. For vertical orientation, it will be considered as the item height. For horizontal orientation, it will be considered as the item width.
 * [ItemType](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html#Syncfusion_ListView_XForms_QueryItemSizeEventArgs_ItemType): Identifies the item type of the queried item.
 * [Handled](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html#Syncfusion_ListView_XForms_QueryItemSizeEventArgs_Handled): Decides whether the specified size can be set to the item or not. The default value is false. When this property is not set, the decided size will not set to the item.

{% tabs %}
{% highlight c# %}
this.listView.QueryItemSize += ListView_QueryItemSize;

private void ListView_QueryItemSize(object sender, Syncfusion.ListView.XForms.QueryItemSizeEventArgs e)
{
    if(e.ItemIndex == 1)
    {
        e.ItemSize = 300;
        e.Handled = true;
    }
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/How-to-set-different-row-height-for-each-row-in-Xamarin.Forms-listview).

![Size of item in listview](SfListView_images/QueryItemSize.jpg)

## AutoFit the items based on the content

The SfListView allows dynamically adjusting size of items based on the content loaded in the [SfListView.ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemTemplate) by defining the [SfListView.AutoFitMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_AutoFitMode) property.

The control contains the following three types of `AutoFitMode`:

 * Height: AutoFit the items based on the content.
 * DynamicHeight: AutoFit the items based on the content if size of the content is changed at run time.
 * None: The `SfListView` items are layout by [SfListView.ItemSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemSize).

 N> If you define any size manually to the view loaded in [SfListView.ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemTemplate), the `SfListView` will return that size as the item size for each item.

### AutoFitMode as Height

AutoFit considers height of the item when [SfListView.Orientation](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_Orientation) is vertical. When `SfListView.Orientation` is horizontal, it considers width of the item. The [SfListView.GridLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html) AutoFit all the items in a row and takes the maximum item height of the row and applies to all other items in the row.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                    ItemSize="200"
                    AutoFitMode="Height"
                    ItemsSource="{Binding BookInfo}" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.AutoFitMode = AutoFitMode.Height; 
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Autofit-listviewitem-in-xamarin.forms-listview).

![AutoFit items](SfListView_images/AutoFit.jpg)

### AutoFitMode as DynamicHeight

AutoFit considers height of the item when `SfListView.Orientation` is vertical. When `SfListView.Orientation` is horizontal, it considers width of the item. The `SfListView.GridLayout` AutoFit all the items in a row and takes the maximum item height of the row and applies to all other items in the row.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                    ItemSize="200"
                    AutoFitMode="DynamicHeight"
                    ItemsSource="{Binding BookInfo}" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.AutoFitMode = AutoFitMode.DynamicHeight; 
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo [here](https://github.com/SyncfusionExamples/listview_autofit).

![AutoFit items at runtime](SfListView_images/AutoFit_DynamicHeight.gif)

## Updating the listview item size based on font at runtime

ListView allows you to resize the item size based on the change in font size of the label element at runtime when `SfListView.AutoFitMode` is [DynamicHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.AutoFitMode.html).

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">       
 <Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="50"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Button Text="Modify FontSize" Clicked="Button_Clicked"/>
    <syncfusion:SfListView x:Name="listView" 
                ItemsSource="{Binding Items}"
                BackgroundColor="#FFE8E8EC"
                AutoFitMode="DynamicHeight"
                ItemSize="60">
        <syncfusion:SfListView.ItemTemplate>
            <DataTemplate>
                <Grid x:Name="grid" RowSpacing="1">
                    <Label LineBreakMode="NoWrap"
                    TextColor="#474747"
                    FontSize="{Binding BindingContext.FontSize, Source={x:Reference Name=listView}}"
                    Text="{Binding ContactName}">
                    </Label>
                </Grid>
            </DataTemplate>
        </syncfusion:SfListView.ItemTemplate>
    </syncfusion:SfListView>                
</ContentPage>
{% endhighlight %}
{% highlight c# %}
private void Button_Clicked(object sender, EventArgs e)
{
    ViewModel.FontSize += 25;
}
{% endhighlight %}
{% endtabs %}

![Customize label font size for listview item](SfListView_images/SfListView-FontSizeChanged.jpg)

## Updating the Header and Footer height based on font at runtime

ListView allows you to resize the header and footer item size based on the change in font size of the label element at runtime by calling [RefreshListViewItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_RefreshListViewItem_System_Int32_System_Int32_System_Boolean_) method asynchronously when [SfListView.AutoFitMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_AutoFitMode) is Height.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">       
 <Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="50"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Button Text="Change FontSize" Command="{Binding ResizeHeaderFooterCommand}" CommandParameter="{x:Reference listView}"/>
    <syncfusion:SfListView x:Name="listView" 
                ItemsSource="{Binding Contacts}"
                BackgroundColor="#FFE8E8EC"
                AutoFitMode="Height">
                <syncfusion:SfListView.HeaderTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <Grid>
                                <Label Text="Contact Details"
                                       FontSize="{Binding BindingContext.FontSize, Source={x:Reference listView}}"/>
                            </Grid>
                        </ViewCell>
                    </DataTemplate>
                </syncfusion:SfListView.HeaderTemplate>
                <syncfusion:SfListView.FooterTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <Grid >
                                <Label Text="Contacts Count" FontSize="{Binding BindingContext.FontSize, Source={x:Reference listView}}"/>
                                <Label Text="{Binding Contacts.Count}" FontSize="{Binding BindingContext.FontSize, Source={x:Reference listView}}"/>
                            </Grid>
                        </ViewCell>
                    </DataTemplate>
                </syncfusion:SfListView.FooterTemplate>
    </syncfusion:SfListView>                
</ContentPage>
{% endhighlight %}
{% highlight c# %}
namespace SfListViewSample
{
    public class ContactsViewModel : INotifyPropertyChanged
    {
        public Command ResizeHeaderFooterCommand { get; set; }
        private double MaxPhone = 70;
        private double MinPhone = 20;
        private double MaxTablet = 100;
        private double MinTablet = 30;
        public ContactsViewModel()
        {
           ResizeHeaderFooterCommand = new Command(ResizeHeaderFooter);
        }
        private void ResizeHeaderFooter(object obj)
        {
            list = obj as SfListView;
            var maxFont = Device.Idiom == TargetIdiom.Phone ? MaxPhone : MaxTablet;
            var minFont = (Device.Idiom == TargetIdiom.Phone) ? MinPhone : MinTablet;
            if (FontSize >= maxFont)
            {
                FontSize = minFont;
            }
            else
            {
                FontSize += 10;
            }
            list.RefreshListViewItem(-1, -1, true);
        }
    }
}       
{% endhighlight %}
{% endtabs %}

You can download entire source code from [GitHub](https://github.com/SyncfusionExamples/How-to-update-header-and-footer-height-based-on-font-size-at-runtime).

![Customize label font size for header and footer item](SfListView_images/SfListView_HeaderFooterFontSizeChange.png)

## Load images with autofit mode

By default, the image is not loaded with the actual size in autofit mode, as it measures the size before the layout. So, the size of the child view changes cannot be found from the parent view. It is a known issue in listview, but this can be overcome by calling the `RefreshListViewItem` method in the loaded event of listview.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <ContentPage.Content>
        <Grid>
            <syncfusion:SfListView x:Name="listView" 
                                   AutoFitMode="Height"
                                   ItemsSource="{Binding ContactsInfo}"
                                   Loaded="ListView_Loaded">
                <syncfusion:SfListView.ItemTemplate>
                    <DataTemplate>
                        <StackLayout>
                            <StackLayout>
                                <Label Text="{Binding ContactName}" />
                                <Label Text="{Binding ContactNumber}"  />
                            </StackLayout>
                            <Image Source="{Binding ContactImage}"  />
                        </StackLayout>
                    </DataTemplate>
                </syncfusion:SfListView.ItemTemplate>
            </syncfusion:SfListView>
        </Grid>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
private void ListView_Loaded(object sender, Syncfusion.ListView.XForms.ListViewLoadedEventArgs e)
{
    Device.BeginInvokeOnMainThread(async() =>
    {
        await Task.Delay(100);
        listView.RefreshListViewItem();
    });
}
{% endhighlight %}
{% endtabs %}

## Limitations

 * Defines the size of the image when loading image in the [SfListView.ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemTemplate). Because, it does not return actual measured size when measuring before layout the item.
 * Avoids SfListView inside the SfListView if `SfListView.AutoFitMode` is `Height` or `DynamicHeight`. Because, the inner SfListView does not return actual measured size when measuring before layout the item.

## See Also

[How to autofit the content based on the property change in Xamarin.Forms listview using MVVM](https://www.syncfusion.com/kb/9856/)                                                                                            
[How to set different row height for each row in listview](https://www.syncfusion.com/kb/9478/)                                                                                                                                                                    
