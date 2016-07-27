---
layout: post
title: Label Support for Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set label and their positions in RangeSlider control
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Labels Customization

SfRangeSlider provides option to show or hide the label and position customization.

## Show Value Label

This property allows us to display labels for the ticks. When it sets to true, it displays the label for all the ticks based on the `ValuePlacement` property.

N> The default value of the `ShowValueLabel` property is false.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ShowValueLabel="true"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeslider.ShowValueLabel= true;

{% endhighlight %}

{% endtabs %}

## Set Custom Label

To display custom labels, `ShowCustomLabel` property should be set to true and need to populate the `CustomLabels` property with observable collection of items by specifying the custom labels for corresponding values.

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

![](images/customLabel.png)


## Value Placement

The `ValuePlacement` property describes the position of the Value respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ValuePlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeslider.ValuePlacement=ValuePlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![](images/value-TopLeft.png)

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ValuePlacement="BottomRight"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeslider.ValuePlacement=ValuePlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

![](images/Value-BottomRight.png)

## Label Placement

The `LabelPlacement` property describes the position of the custom labels respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"LabelPlacement="TopLeft"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeslider.LabelPlacement=LabelPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}
