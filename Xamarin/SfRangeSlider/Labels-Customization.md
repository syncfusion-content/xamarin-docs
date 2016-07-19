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

## Show or Hide Value Label

This property allows us to display labels for the ticks. When it sets to true, it displays the label for all the ticks based on the `ValuePlacement` property.

N> The default value of the `ShowValueLabel` property is false.

{% tabs %}

{% highlight c# %}

	rangeslider.ShowValueLabel= true;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ShowValueLabel="true"/>
	
{% endhighlight %}

{% endtabs %}


## Displaying Value in Different Positions

The `ValuePlacement` property describes the position of the Value respective to ticks. 

Available options for this property are:

* BottomRight

* TopLeft

{% tabs %}

{% highlight c# %}

	rangeslider.ValuePlacement=ValuePlacement.TopLeft;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ValuePlacement="TopLeft"/>
	
{% endhighlight %}

{% endtabs %}

![](images/value-TopLeft.png)

{% tabs %}

{% highlight c# %}

	rangeslider.ValuePlacement=ValuePlacement.BottomRight;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ValuePlacement="BottomRight"/>
	
{% endhighlight %}

{% endtabs %}

![](images/Value-BottomRight.png)
