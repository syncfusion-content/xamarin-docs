---
layout: post
title: Orientation in Xamarin Range Slider control | Syncfusion
description: Learn here all about Orientation support in Syncfusion Xamarin Range Slider (SfRangeSlider) control and more.
platform: Xamarin
control: SfRangeSlider
documentation: ug
---

# Orientation in Xamarin Range Slider (SfRangeSlider)

[`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) provides options to display values and slider to slide either horizontally or vertically.

N> The default option is [`Vertical`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.Orientation.html#Syncfusion_SfRangeSlider_XForms_Orientation_Vertical).

## Horizontal

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

![Horizantal image](images/RangeSlider-Horizontal.png)

## Vertical

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

![Vertical image](images/RangeSlider-Vertical.png)


