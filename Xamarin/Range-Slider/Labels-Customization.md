---
layout: post
title: Labels Customization in Xamarin Range Slider control | Syncfusion
description: Learn here all about Labels Customization support in Syncfusion Xamarin Range Slider (SfRangeSlider) control and more.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Labels Customization in Xamarin Range Slider (SfRangeSlider)

[`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) provides option to show or hide the label and position customization.

## Show Value Label

This property allows us to display labels for the ticks. When it sets to true, it displays the label for all the ticks based on the [`ValuePlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ValuePlacement) property.

N> The default value of the [`ShowValueLabel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ShowValueLabel) property is false.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ShowValueLabel="true"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ShowValueLabel= true;

{% endhighlight %}

{% endtabs %}

## Set Custom Label

To display custom labels, [`ShowCustomLabel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ShowCustomLabel) property should be set to true and need to populate the [`CustomLabels`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_CustomLabels) property with observable collection of items by specifying the custom labels for corresponding values.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" HeightRequest="400" ShowCustomLabel="true" CustomLabels="customCollection"/>
	
{% endhighlight %}

{% highlight c# %}
	
SfRangeSlider rangeSlider; 
ObservableCollection<Items>  customCollection;
public RangeSliderPage ()
{
     customCollection = new ObservableCollection<Items> ();
     customCollection.Add(new Items(){Label = "Min", Value= 0});
     customCollection.Add(new Items() { Label = "Max", Value = 100 });
     rangeSlider = new SfRangeSlider ();
     rangeSlider.HeightRequest = 400;
     rangeSlider.ShowCustomLabel = true;
     rangeSlider.CustomLabels = customCollection
}

{% endhighlight %}

{% endtabs %}

![SfRangeSlider rendererd in vertical orientation with custom label in Xamarin.Forms](images/customLabel.png)


## Value Placement

The [`ValuePlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ValuePlacement) property describes the position of the [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Value) respective to ticks. 

Available options for this property are:

* [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValuePlacement.html#Syncfusion_SfRangeSlider_XForms_ValuePlacement_BottomRight)

* [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValuePlacement.html#Syncfusion_SfRangeSlider_XForms_ValuePlacement_TopLeft)

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ValuePlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ValuePlacement=ValuePlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![Value label placed at the top position of SfRangeSlider in Xamarin.Forms](images/value-TopLeft.png)

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ValuePlacement="BottomRight"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ValuePlacement=ValuePlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

![Value label placed at the bottom position of SfRangeSlider in Xamarin.Forms](images/Value-BottomRight.png)

## Label Placement

The [`LabelPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_LabelPlacement) property describes the position of the custom labels respective to ticks. 

Available options for this property are:

* [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.LabelPlacement.html#Syncfusion_SfRangeSlider_XForms_LabelPlacement_BottomRight)

* [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.LabelPlacement.html#Syncfusion_SfRangeSlider_XForms_LabelPlacement_TopLeft)

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" LabelPlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.LabelPlacement=LabelPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

## Customizing label font

The range slider control provides the [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_FontFamily), [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_FontSize), and [`FontAttribute`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_FontAttribute) properties to customize the value text and custom label text.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
xmlns:Range="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
xmlns:Local="clr-namespace:GettingStarted;assembly=GettingStarted"
x:Class="GettingStarted.RangeSliderSample">
	<ContentPage.Content>
		<Range:SfRangeSlider FontFamily="Times New Roman" ShowCustomLabel="true" FontAttribute="Italic" FontSize="12"  Orientation="Horizontal">
			<Range:SfRangeSlider.CustomLabels>
				<Local:ObservableCollectionList>
					<Range:Items Label="Min" Value="0"/>
					<Range:Items Label="Mid" Value="50"/>
					<Range:Items Label="Max" Value="100"/>
				</Local:ObservableCollectionList>
			</Range:SfRangeSlider.CustomLabels>
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
			SfRangeSlider rangeSlider = new SfRangeSlider(){ FontFamily="Times New Roman",ShowCustomLabel=true, FontAttribute=FontAttributes.Italic, FontSize=12,  Orientation=Orientation.Horizontal};
			rangeSlider.CustomLabels = new ObservableCollection<Items>()
			{
                new Items(){Value=0,Label="Min"},
				new Items(){Value=50,Label="Mid"},
				new Items(){Value=100,Label="Max"}
			};
			this.Content = rangeSlider;
        }
    }

}

{% endhighlight %}

{% endtabs %}


{% highlight c# %}

using System.Collections.ObjectModel;
using Syncfusion.XForms.SfRangeSlider;
using Xamarin.Forms;
namespace GettingStarted
{
	/// <summary>
	/// Observable collection of Items list.
	/// </summary>
	public class ObservableCollectionList : ObservableCollection<Items>
	{

	}

	/// <summary>
    /// Range slider sample.
    /// </summary>
    public partial class RangeSliderSample : ContentPage
    {
        public RangeSliderSample()
        {
            InitializeComponent();
        }
    }
}
	

{% endhighlight %}


![Font customization in SfRangeSlider in Xamarin.Forms](images/FontItalicCustom.png)

## LabelColor

The [`LabelColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_LabelColor) property used to change the color of the label.

{% tabs %}

{% highlight xaml %}

<range:SfRangeSlider x:Name="rangeslider" LabelColor="Red" Minimum="0" Maximum="100"/>

{% endhighlight %}

{% highlight c# %}

 rangeslider.LabelColor = Color.Red;

{% endhighlight %}

{% endtabs %}

![Label in SfRangeSlider in Xamarin.Forms](images/LabelColor.jpg)
