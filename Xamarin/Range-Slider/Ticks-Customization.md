---
layout: post
title: Ticks Customization in Xamarin Range Slider Control | Syncfusion
description: Discover all about ticks customization support in the Syncfusion Xamarin Range Slider (SfRangeSlider) control.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Ticks Customization in Xamarin Range Slider (SfRangeSlider)

Tick marks can be uniformly placed along the track, or you can customize their position according to your needs.

## Tick Placement

The [`TickPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickPlacement) property determines where tick marks will appear relative to the track. Options are:

- [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.TickPlacement.html#Syncfusion_SfRangeSlider_XForms_TickPlacement_BottomRight)
- [`Inline`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.TickPlacement.html#Syncfusion_SfRangeSlider_XForms_TickPlacement_Inline)
- [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.TickPlacement.html#Syncfusion_SfRangeSlider_XForms_TickPlacement_None)
- [`Outside`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.TickPlacement.html#Syncfusion_SfRangeSlider_XForms_TickPlacement_Outside)
- [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.TickPlacement.html#Syncfusion_SfRangeSlider_XForms_TickPlacement_TopLeft)

> **Note**: The default setting is [`Inline`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.TickPlacement.html#Syncfusion_SfRangeSlider_XForms_TickPlacement_Inline).

### BottomRight

Place tick marks either below the track in horizontal orientation or to the right of the track in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="BottomRight"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

![Tick marks placed at the bottom right on SfRangeSlider in Xamarin.Forms](images/BottomRight.png)

### TopLeft

Place tick marks either above the track in horizontal orientation or to the left of the track in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![Tick marks placed at the top left on SfRangeSlider in Xamarin.Forms](images/TopLeft.png)

### Inline

[`Ticks`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SnapsTo.html#Syncfusion_SfRangeSlider_XForms_SnapsTo_Ticks) are placed along the track.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="Inline"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.Inline;

{% endhighlight %}

{% endtabs %}

![Tick marks placed inline on SfRangeSlider in Xamarin.Forms](images/Inline.png)

### Outside

Place tick marks on both sides of the track for either horizontal or vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="Outside"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.Outside;

{% endhighlight %}

{% endtabs %}

![Tick marks placed outside of SfRangeSlider in Xamarin.Forms](images/Outside.png)

## Customizing Tick Color

Customize the tick color using the [`TickColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_TickColor) property.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
xmlns:range="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
x:Class="GettingStarted.RangeSliderSample">
	<ContentPage.Content>
		<range:SfRangeSlider x:Name="rangeslider" Orientation="Horizontal"  TickColor="#FFFFFF"/>
	</ContentPage.Content>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.SfRangeSlider;
using Xamarin.Forms;
namespace GettingStarted
{
	/// <summary>
    /// Range slider sample.
    /// </summary>
    public partial class RangeSliderSample : ContentPage
    {
        public RangeSliderSample()
        {
            InitializeComponent();
			SfRangeSlider rangeSlider = new SfRangeSlider(){ TickColor = Color.FromHex("#FFFFFF"),Orientation=Orientation.Horizontal};
			this.Content = rangeSlider;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Tick color customization on SfRangeSlider in Xamarin.Forms](images/TickColor.png)
