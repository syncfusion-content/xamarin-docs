---
layout: post
title: Orientation in Xamarin Range Slider Control | Syncfusion
description: Discover the orientation settings for the Syncfusion Xamarin Range Slider (SfRangeSlider) control, enabling horizontal and vertical slider configurations.
platform: Xamarin
control: SfRangeSlider
documentation: ug
---

# Orientation in Xamarin Range Slider (SfRangeSlider)

The [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) control allows you to configure the slider to move either horizontally or vertically.

> **Note**: The default orientation is set to [`Vertical`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.Orientation.html#Syncfusion_SfRangeSlider_XForms_Orientation_Vertical).

## Horizontal Orientation

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
xmlns:Range="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
xmlns:Local="clr-namespace:GettingStarted;assembly=GettingStarted"
x:Class="GettingStarted.RangeSliderSample">
	<ContentPage.Content>
		<Range:SfRangeSlider  Orientation="Horizontal"/>
	</Range:SfRangeSlider>
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System.Collections.ObjectModel;
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
			SfRangeSlider rangeSlider = new SfRangeSlider();
			rangeSlider.Orientation=Orientation.Horizontal;
            this.Content = rangeSlider;
        }
    }
}	

{% endhighlight %}

{% endtabs %}

![Horizontal orientation of SfRangeSlider in Xamarin.Forms](images/RangeSlider-Horizontal.png)

## Vertical Orientation
{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
xmlns:Range="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
xmlns:Local="clr-namespace:GettingStarted;assembly=GettingStarted"
x:Class="GettingStarted.RangeSliderSample">
	<ContentPage.Content>
		<Range:SfRangeSlider  Orientation="Vertical"/>
	</Range:SfRangeSlider>
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System.Collections.ObjectModel;
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
			SfRangeSlider rangeSlider = new SfRangeSlider();
			rangeSlider.Orientation=Orientation.Vertical;
            this.Content = rangeSlider;
        }
    }
}	

{% endhighlight %}

{% endtabs %}

![Vertical orientation of SfRangeSlider in Xamarin.Forms](images/RangeSlider-Vertical.png)
