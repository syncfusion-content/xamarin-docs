---
layout: post
title: Item Size Customization in SfListView
description: Describes the Item Size Customization in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Item Size Customization

This section explains how to customize the item size in the SfListView.

## Customize item size of a particular item on demand

The SfListView allows customizing size of the item on demand by [SfListView.QueryItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~QueryItemSize_EV.html) event. This event is raised whenever items come to view. The size of a particular item can be customized on demand by using the item index.

### QueryItemSize

[SfListView.QueryItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~QueryItemSize_EV.html) is the event returns item size on demand. This event is triggered with [QueryItemSizeEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs.html).

`SfListView.QueryItemSize` event provides the following properties in their arguments:

 * [ItemIndex](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemIndex.html): This property helps to identify a particular item in the SfListView. 
 * [ItemData](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemData.html): This property helps to identify the underlying data bounded to that item.
 * [ItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemSize.html): This property identifies size of the queried item. For vertical orientation, it will be considered as item height. For horizontal orientation, it will be considered as item width.
 * [ItemType](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~ItemType.html): This property helps to identify the item type of the queried item.
 * [Handled](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.QueryItemSizeEventArgs~Handled.html): This property decides whether the specified size can be set to item or not. The default value is false. When this property is not set, the decided size is not set to the item.

To hook `SfListView.QueryItemSize` event, and customize item size in the SfListView, follow the code example:

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

You can download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoFit-1318092121).

![](SfListView_images/QueryItemSize.jpg)

## AutoFit the items based on the content

The SfListView allows dynamically adjusting size of items based on the content loaded in the [SfListView.ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html) by defining the [SfListView.AutoFitMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AutoFitMode.html) property. The control has two types of AutoFitMode as listed as follows:

 * Height: AutoFit the item based on the content, and consider height of the item when vertical [SfListView.Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Orientation.html). For horizontal orientation, consider width of the item. If [SfListView.GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html). After AutoFit all items in a row, it will take the maximum item height in that row, and applies to all other items in the row.
 * None: The SfListView items are layout by [SfListView.ItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemSize.html).

To customize the item size based on the content, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                     ItemSize="200"
                     AutoFitMode="Height"
                     ItemsSource="{Binding BookInfo}" />
{% endhighlight %}
{% highlight c# %}
listView.AutoFitMode = AutoFitMode.Height; 
{% endhighlight %}
{% endtabs %}

N> If you define any size manually to view which loaded in [SfListView.ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html), the SfListView will returns that size as item size of each item. 

The following screenshot shows the output of AutoFit items. You can download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoFit2085660985).

![](SfListView_images/AutoFit.jpg)

## Limitations

 * To define size of the image when loading image in the [SfListView.ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html). Because, it does not returns actual measured size while measuring before layout the item.
 * Avoid the SfListView inside the SfListView if [SfListView.AutoFitMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AutoFitMode.html) as Height. Because, the inner SfListView does not returns actual measured size while measuring before layout the item.
 