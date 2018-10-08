---
layout: post
title: Ticks of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set ticks in proper position for RangeSlider control in Xamarin.Forms
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Customizing ticks

Tick marks can be placed along the track in a uniform manner or it's position can also be customized.

## TickPlacement

The `TickPlacement` property determines where to draw tick marks in relation to the track. Available options for this property are,

* BottomRight

* Inline

* None

* Outside

* TopLeft

N> The default option is Inline.

### BottomRight

Tick marks can be placed either below the track in horizontal orientation or right of the track in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="BottomRight"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

![Tick has been placed at the bottom right of SfRangeSlider in Xamarin.Forms](images/BottomRight.png)

### TopLeft

Tick marks are placed either above the track in horizontal orientation or left of the track in vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![Tick has been placed at the top left of SfRangeSlider in Xamarin.Forms](images/TopLeft.png)

### Inline

Ticks are placed along the track.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="Inline"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.Inline;

{% endhighlight %}

{% endtabs %}

![Tick has been placed on the SfRangeSlider in Xamarin.Forms](images/Inline.png)

### Outside

Tick marks are placed on both sides of the track either in horizontal or vertical orientation.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" TickPlacement="Outside"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.Outside;

{% endhighlight %}

{% endtabs %}

![Tick has been placed outside of SfRangeSlider in Xamarin.Forms](images/Outside.png)

## Customizing tick color

The range slider control provides the `TickColor` property to customize the color of ticks in tick bar.

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

![Tick color customization of SfRangeSlider in Xamarin.Forms](images/TickColor.png)