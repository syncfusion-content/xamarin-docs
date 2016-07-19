---
layout: post
title: Range in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to set Dual thumb slider and its ranges in RangeSlider control.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Displaying Dual Thumb

The SfRangeSlider control supports to select range of value by using two Thumbs. The `ShowRange` property should be set to true for displaying two thumbs in track with range of values.

Setting ShowRange property to false shows the single thumb without any range. To set the Range of the thumb in SfRangeSlider Value property is used when ShowRange is disabled.

{% tabs %}

{% highlight c# %}

    rangeslider.Value = 50;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ShowRange="false" Value="50"/>
	
{% endhighlight %}

{% endtabs %}

N> Default value of `ShowRange` is true.

{% tabs %}

{% highlight c# %}

	rangeslider.ShowRange= true;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ShowRange="true"/>
	
{% endhighlight %}

{% endtabs %}

## Setting Thumb Values

This section explains about setting Range start and end value.

### RangeStart

Gets and sets the start value of the Range.

{% tabs %}

{% highlight c# %}

	rangeslider.RangeStart=0;

{% endhighlight %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"  RangeStart="4" />
	
{% endhighlight %}

{% endtabs %}

### RangeEnd

Gets and sets the end value of the Range.

{% tabs %}

{% highlight c# %}

	rangeslider.RangeEnd=10;

{% endhighlight  %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" RangeEnd="20" />
	
{% endhighlight %}

{% endtabs %}
