---
layout: post
title: Nullable selection in Syncfusion segmented control for Xamarin.Forms
description: Learn how to clear the default selection in segmented control
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Clear the default selection in SfSegmentedControl

The SfSegmentedControl provides support to clear the default selection on segments by setting the value of `SelectedIndex` as negative or beyond the collection count.

N> By default, it selects the 0th indexed item.

{% tabs %}

{% highlight xaml %}

Namespace:

xmlns:sys="clr-namespace:System.Collections.Generic;assembly=netstandard"
...
   <buttons:SfSegmentedControl
        SelectedIndex="-1"
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
        SelectedIndex = -1,
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

![Indicates the nullable selection of SfSegmentedControl in Xamarin.Forms](images/Xamarin_Forms_SegmentedControl_Nullable_Selections.png)
