---
layout: post
title: Various customization in Syncfusion SegmentedControl for Xamarin.Forms
description: Learn how to customize the segmented control
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Customization

The segmented control supports customizing segment color, text color, icon size, selection color, and more. This control also supports enabling the segments to fit your application’s theme. It can be customized in the following areas.

## Text appearance

The text inside the segmented control can be customized by its font size, color, and its font family.

### Font family

You can customize the font family of the segmented item using the `FontFamily` property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl>
<buttons:SfSegmentedControl.FontFamily>
        <OnPlatform x:TypeArguments="x:String">
        <On Platform="iOS" Value="Helvetica" />
        <On Platform="Android" Value="Roboto" />
        <On Platform="UWP" Value="Helvetica" />
       </OnPlatform>
</buttons:SfSegmentedControl.FontFamily>
</buttons:SfSegmentedControl >


{% endhighlight %}

{% highlight c# %}

segmentedControl.FontFamily = Device.RuntimePlatform == Device.iOS ? "Helvetica" :
Device.RuntimePlatform == Device.Android ? "Roboto"  : "Helvetica";

{% endhighlight %}

{% endtabs %}

### Font color

You can customize the text color of the segmented item using the `FontColor` property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl FontColor="Red" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectionTextColor = Color.Red;

{% endhighlight %}

{% endtabs %}

![Font color customization in segmented control](images/Customization/Xamarin_Forms_Fontcolor.png)

### Font size

You can change the text size of the segmented item using the `FontSize` property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl FontSize="20" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.FontSize = 20;

{% endhighlight %}

{% endtabs %}

![Font size customization in segmented control](images/Customization/Xamarin_Forms_Size.png)

## Border

You can customize the border by their color and thickness.

### Border color

You can customize the border color of all the items in the segmented control.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl BorderColor="Red" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.BorderColor = Color.Red;

{% endhighlight %}

{% endtabs %}

![Border color customization in segmented control](images/Customization/Xamarin_Forms_Bordercolor.png)

### Border thickness

You can customize the width of the border using the `BorderThickness` property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl  BorderThickness="5" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.BorderThickness = 5;

{% endhighlight %}

{% endtabs %}

![Border thickness customization in segmented control](images/Customization/Xamarin_Forms_BorderThickness.png)

### Padding

The segmented control handles padding between the items.

#### Segment padding

Spacing between the segmented items in the control can be customized using the `SegmentPadding`.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl SegmentPadding="15" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.SegmentPadding = 15;

{% endhighlight %}

{% endtabs %}

![Segment padding customization in segmented control](images/Customization/Xamarin_Forms_Padding.png)

### Corner radius

The segmented control provides corner radius support for the segmented items and strip.

#### Item radius

The segmented control customizes the corner radius for each segmented item.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl SegmentCornerRadius="15" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.SegmentCornerRadius = 15;

{% endhighlight %}

{% endtabs %}

![Segment corner radius customization in segmented control](images/Customization/Xamarin_Forms_ItemCornerRadius.png)

#### Selection strip radius

The segmented control customizes corner radius for selection strip using the `CornerRadius` inside the SelectionIndicatorSetting class.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl>
<buttons:SfSegmentedControl.SelectionIndicatorSettings>
<buttons:SelectionIndicatorSettings 
    CornerRadius="15">
</buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>
</buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.CornerRadius = 15;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}

![Selected segment corner radius customization in segmented control](images/Customization/Xamarin_Forms_SelectionstripRadius.png)

#### Control radius

The segmented control also handles corner radius for border line of the whole control.


{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl CornerRadius="15" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.CornerRadius = 15;

{% endhighlight %}

{% endtabs %}

![Corner radius customization in segmented control](images/Customization/Xamarin_Forms_controlRadius.png)

### Color

The segmented control allows users to customize the background color of the segmented items and background color of the control.

#### Item color

You can customize the background color of each segmented item using the `Color` property in the SelectionIndicatorSettings class.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl.SelectionIndicatorSettings>
<buttons:SelectionIndicatorSettings 
    Color="#FF355088">
</buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Color = Color.FromHex("#FF355088");
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}

![Segment item color customization in segmented control](images/Customization/Xamarin_Forms_ItemCornerRadius.png)

#### Control color

You can customize the background color of the control by setting value for the `Color` property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl Color="#02A0AE" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.Color = Color.FromHex("#02A0AE");

{% endhighlight %}

{% endtabs %}

![Segmented control color customization in segmented control](images/Customization/Xamarin_Forms_color.png)

## Scrolling in segmented control programmatically

The SegmentedControl allows programmatic scrolling based on index and item using the `ScrollTo` methods mentioned as follows.

### ScrollTo(index, scrollToPosition)

This method is used to scroll the segment item based on given index and [`ScrollToPosition`]() value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(5,  Syncfusion.XForms.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}

### ScrollTo(item, scrollToPosition)

This method is used to scroll the segment item based on the given data or `SfSegmentItem` and [`ScrollToPosition`]() value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(viewModel.Items[5], Syncfusion.XForms.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}
