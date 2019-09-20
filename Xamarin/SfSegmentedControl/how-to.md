---
layout: post
title: How to section of Syncfusion segmented control for Xamarin.Forms
description: Learn how to make a nullable selection in segmented control
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# How to clear the selection in SfSegmentedControl?

SfSegmentedControl provides the support to make a null selection. By default, it selects the 0th indexed item. Now providing the support to set the `SelectedIndex` as negative value or beyond the collection count for making a no selection.

{% tabs %}

{% highlight xaml %}

Namespace:

xmlns:sys="clr-namespace:System.Collections.Generic;assembly=netstandard"
...
   <buttons:SfSegmentedControl
        SelectedIndex="-9"
        BorderColor="#3F3F3F"
        FontColor="Black"
        HorizontalOptions="Center"
        VerticalOptions="Center"
        SegmentHeight="32"
        CornerRadius="20"
        VisibleSegmentsCount="3">
        <buttons:SfSegmentedControl.ItemsSource>
            <sys:List x:TypeArguments="x:String">
                <x:String>Formal</x:String>
                <x:String>Casual</x:String>
                <x:String>Trendy</x:String>
            </sys:List>
        </buttons:SfSegmentedControl.ItemsSource>
    </buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight C# %}

    SfSegmentedControl segmentedControl = new SfSegmentedControl()
    {
        SelectedIndex = -9,
        BorderColor = Color.FromHex("#3F3F3F"),
        FontColor = Color.Black,
        HorizontalOptions = LayoutOptions.Center,
        VerticalOptions = LayoutOptions.Center,
        SegmentHeight = 32,
        CornerRadius = 20,
        VisibleSegmentsCount = 3,
    };

    segmentedControl.ItemsSource = new List<String>()
    {
        "Formal","Casual","Trendy"
    };

{% endhighlight %}

{% endtabs %}

![Indicates the nullable selection of SfSegmentedControl in Xamarin.Forms](images/how-to/Xamarin_Forms_SegmentedControl_Nullable_Selection.png)

