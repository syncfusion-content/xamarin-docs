---
layout: post
title: Changing display Orientation of Syncfusion SfRangeSlider control
description: Learn how to set orientation for SfRangeSlider
platform: Xamarin
control: SfRangeSlider
documentation: ug
---

# Orientation

SfRangeSlider provides options to display values and slider to slide either horizontally or vertically.

N> The default option is Vertical.

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


