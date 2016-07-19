---
layout: post
title: Label Support for Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set label and their positions in RangeSlider control
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Providing Custom Labels

This section explains about setting CustomLabel using ObservableCollection of items in SfRangeSlider. 

## CustomLabel

To display custom labels, `ShowCustomLabel` property should be set to true and need to populate the `CustomLabels` property with observable collection of items. Each items should be specified by the custom labels for corresponding values.

{% tabs %}

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

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" HeightRequest="400" ShowCustomLabel="true" CustomLabels="customCollection"/>
	
{% endhighlight %}

{% endtabs %}

![](images/customLabel.png)


## Displaying Label in Different Positions

The `LabelPlacement` property describes the position of the labels respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% tabs %}

{% highlight c# %}

	rangeslider.LabelPlacement=LabelPlacement.TopLeft;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"LabelPlacement="TopLeft"/>
	
{% endhighlight %}

{% endtabs %}
