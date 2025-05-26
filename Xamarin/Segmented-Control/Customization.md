---
layout: post
title: Customization in Xamarin Segmented Control | Syncfusion<sup>&reg;</sup>
description: Explore customization capabilities in Syncfusion<sup>&reg;</sup> Xamarin Segmented Control (SfSegmentedControl).
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Customization in Xamarin Segmented Control (SfSegmentedControl)

The segmented control supports customizing segment color, text color, icon size, selection color, and more. This control also allows segments to seamlessly integrate with your application's theme. Below are the areas that can be customized.

## Text Appearance

The text within the segmented control can be tailored by adjusting its font size, color, and font family.

### Font Family

Customize the font family of segmented items using the [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_FontFamily) property.

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

### Font Color

Customize the text color of segmented items using the [`FontColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_FontColor) property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl FontColor="Red" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectionTextColor = Color.Red;

{% endhighlight %}

{% endtabs %}

![Font color customization in segmented control](images/Customization/Xamarin_Forms_Fontcolor.png)

### Font Size

Change the text size of segmented items using the [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_FontSize) property.

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

Customize the border by both color and thickness.

### Border Color

Adjust the border color for all items in the segmented control.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl BorderColor="Red" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.BorderColor = Color.Red;

{% endhighlight %}

{% endtabs %}

![Border color customization in segmented control](images/Customization/Xamarin_Forms_Bordercolor.png)

### Border Thickness

Customize the border width using the [`BorderThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_BorderThickness) property.

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

The segmented control can handle padding between items.

#### Segment Padding

Customize the spacing between segmented items with the [`SegmentPadding`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SegmentPadding).

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl SegmentPadding="15" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.SegmentPadding = 15;

{% endhighlight %}

{% endtabs %}

![Segment padding customization in segmented control](images/Customization/Xamarin_Forms_Padding.png)

### Corner Radius

The segmented control provides corner radius support for segmented items and strips.

#### Item Radius

Customize the corner radius for each segmented item.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl SegmentCornerRadius="15" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.SegmentCornerRadius = 15;

{% endhighlight %}

{% endtabs %}

![Segment corner radius customization in segmented control](images/Customization/Xamarin_Forms_ItemCornerRadius.png)

#### Selection Strip Radius

Customize the corner radius for the selection strip using the [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_CornerRadius) within the [`SelectionIndicatorSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectionIndicatorSettings) class.

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

#### Control Radius

The segmented control also supports the corner radius for the border line enclosing the entire control.


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

The segmented control allows users to customize the background color of segmented items and the control itself.

#### Item Color

Customize the background color of each segmented item using the [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_Color) property within the [`SelectionIndicatorSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectionIndicatorSettings) class.

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

#### Control Color

Customize the background color of the entire control by setting the [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_Color) property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl Color="#02A0AE" />

{% endhighlight %}

{% highlight c# %}

segmentedControl.Color = Color.FromHex("#02A0AE");

{% endhighlight %}

{% endtabs %}

![Segmented control color customization in segmented control](images/Customization/Xamarin_Forms_color.png)

## Scrolling in Segmented Control Programmatically

The segmented control supports programmatic scrolling using the [`ScrollTo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_ScrollTo_System_Int32_Syncfusion_XForms_Buttons_ScrollToPosition_) methods as follows.

### ScrollTo(index, scrollToPosition)

This method scrolls the segment item based on a given index and [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_ScrollToPosition) value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(5,  Syncfusion.XForms.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}

### ScrollTo(item, scrollToPosition)

Scroll a segment item based on the given data or [`SfSegmentItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentItem.html) and [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_ScrollToPosition) value.

{% tabs %}

{% highlight c# %}

segmentedControl.ScrollTo(viewModel.Items[5], Syncfusion.XForms.Buttons.ScrollToPosition.Start);

{% endhighlight %}

{% endtabs %}

## Segment Height

The segmented control height can be customized using the [SegmentHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SegmentHeight) property as shown below.
 
{% tabs %}

{% highlight xaml %}
     
     <? xml version="1.0" encoding="utf-8" ?>
     <ContentPage 
     xmlns = "http://xamarin.com/schemas/2014/forms" 
     xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
     xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms" 
     x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <buttons:SfSegmentedControl SegmentHeight="60"/>
    </ContentPage.Content>
    </ContentPage>


{% endhighlight %}

{% highlight c# %}

    using Syncfusion.XForms.Buttons;
    using Xamarin.Forms;

    namespace GettingStarted
    {
        public partial class MainPage : ContentPage
        {
            private SfSegmentedControl segmentedControl;
            public MainPage()
            {
                InitializeComponent();
                segmentedControl = new SfSegmentedControl();
                segmentedControl.SegmentHeight = 60;
                this.Content = segmentedControl;
            }
        }
    }

{% endhighlight %}

{% endtabs %}

A sample demonstrating segment height customization can be downloaded from this [link](https://github.com/SyncfusionExamples/how-to-customize-segment-contol-height-in-xamarin.forms).

![Segment Height customization in segmented control](images/Customization/Xamarin_Forms_SegmentHeight.png)

