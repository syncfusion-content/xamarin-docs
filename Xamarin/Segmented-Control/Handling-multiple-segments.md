---
layout: post
title: Handling Multiple Segments in Xamarin Segmented Control | Syncfusion<sup>&reg;</sup>
description: Learn about handling multiple segments in Syncfusion<sup>&reg;</sup> Xamarin Segmented Control (SfSegmentedControl) and more.
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Handling Multiple Segments in Xamarin Segmented Control

The segmented control handles segmented items with space that can be distributed in two ways. If the available space in the segmented control is not equally distributed, items beyond the edges of the control become accessible by scrolling the panel.

## Visible Segment Counts

The segmented control displays items based on the count set for [`VisibleSegmentsCount`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_VisibleSegmentsCount).

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl 
    SegmentHeight="20"
    VisibleSegmentsCount="4"
    SelectedIndex="2"
    FontColor="Black"
    Color="Transparent"
    DisplayMode = "Text"
    SelectionTextColor="#02A0AE"> 
<segmentCollection:List x:TypeArguments="x:String">
<x:String>Item1</x:String>
<x:String>Item2</x:String>
<x:String>Item3</x:String>
<x:String>Item4</x:String>
<x:String>Item5</x:String>
<x:String>Item6</x:String>
<x:String>Item7</x:String>
<x:String>Item8</x:String>
<x:String>Item9</x:String>
</segmentCollection:List>
</buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight c# %}

public partial class SegmentedControlSample : ContentPage
{
SfSegmentedControl segmentedControl;
public SegmentedControlSample()
{
InitializeComponent();
segmentedControl = new SfSegmentedControl();
List<String> itemsList = new List<String>
{
        "Item1","Item2","Item3","Item4","Item5","Item6","Item7","Item8","Item9"
};
segmentedControl.ItemsSource = itemsList;
segmentedControl.Color = Color.Transparent;
segmentedControl.VisibleSegmentsCount = 4;
segmentedControl.SelectedIndex = 2;
segmentedControl.FontColor = Color.Black;
segmentedControl.SelectionTextColor = Color.FromHex("#02A0AE");
this.Content = segmentedControl;
}
}

{% endhighlight %}

{% endtabs %}

![Visible Segment Count](images/Handling-multiple-segments/visiblesegment.png)

## Segment Width

Users can apply the [`SegmentWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SegmentWidth) property to display segmented items within the specified width as an alternative to [`VisibleSegmentsCount`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_VisibleSegmentsCount).

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl SegmentWidth = "80"/> 

{% endhighlight %}

{% highlight c# %}

segmentedControl.SegmentWidth = 80;

{% endhighlight %}

{% endtabs %}

