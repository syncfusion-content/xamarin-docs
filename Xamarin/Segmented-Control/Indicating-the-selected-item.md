---
layout: post
title: Indicating the Selected Item in Xamarin Segmented Control | Syncfusion<sup>&reg;</sup>
description: Discover how to indicate the selected item in Syncfusion<sup>&reg;</sup> Xamarin Segmented Control (SfSegmentedControl) and more.
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Indicating the Selected Item in Xamarin Segmented Control

The segmented control indicates the selected item by differentiating it with either the text color of the item or by using a selection strip.

## Selection Text Color

The text color of the selected item can be changed to a desired color. Customize the selected item's text color using the [`SelectionTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectionTextColor) property.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl SelectionTextColor="#02A0AE"/> 

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectionTextColor = Color.FromHex("#02A0AE");

{% endhighlight %}

{% endtabs %}

![Xamarin_Forms_SelectionTextColor](images/Selection-indicator/Xamarin_Forms_selectiontextcolor.png)

## Selection Strip

A selection strip is used to indicate the selected item in the segmented control. The selection strip can be customized in various ways.

### Position

Customize the position of the selection indicator according to your needs.
#### Top

The selection strip can be displayed as a line with customizable color and thickness, positioned at the top of an item.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl.SelectionIndicatorSettings>
    <buttons:SelectionIndicatorSettings 
        Position="Top">
    </buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Top;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}

![Xamarin_Forms_Top](images/Selection-indicator/Xamarin_Forms_Top.png)

#### Bottom

Similarly, the selection strip can be positioned at the bottom of an item with customizable color and thickness.
{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl.SelectionIndicatorSettings>
    <buttons:SelectionIndicatorSettings 
        Position="Bottom">
    </buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Bottom;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}

![Xamarin_Forms_Bottom](images/Selection-indicator/Xamarin_Forms_Bottom.png)

#### Fill

The selection strip can be placed over a segment item to indicate selection, with customizable color to highlight the item.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl.SelectionIndicatorSettings>
    <buttons:SelectionIndicatorSettings 
        Position="Fill">
    </buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Fill;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}

![Xamarin_Forms_Fill](images/Selection-indicator/Xamarin_Forms_Fill.png)

#### Border

You can set the selection strip as a border to emphasize the selected item.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl.SelectionIndicatorSettings>
    <buttons:SelectionIndicatorSettings 
        Position="Border">
    </buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Position = Position.Border;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}

![Xamarin_Forms_Border](images/Selection-indicator/Xamarin_Forms_Border.png)

### Color

Customize the background color of the selection strip using the [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_Color) property of [`SelectionIndicatorSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectionIndicatorSettings).

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl.SelectionIndicatorSettings>
<buttons:SelectionIndicatorSettings 
    Color="#2C7BBC">
</buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Color = Color.FromHex("#2C7BBC");
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}

![Xamarin_Forms_StripColor](images/Selection-indicator/Xamarin_Forms_stripcolor.png)

### Thickness

Customize the thickness of the selection strip border using the [`StrokeThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_BorderThickness) property of [`SelectionIndicatorSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectionIndicatorSettings).

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl.SelectionIndicatorSettings>
<buttons:SelectionIndicatorSettings 
    StrokeThickness="10">
</buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>

{% endhighlight %}

{% highlight c# %}

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.StrokeThickness = 10;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;

{% endhighlight %}

{% endtabs %}





