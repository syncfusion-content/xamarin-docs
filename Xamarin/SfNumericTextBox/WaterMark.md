---
layout: post
title: WaterMark Support in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to add watermark text in NumericTextBox.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# WaterMark

The `WaterMark` property can be used to provide a hint that helps the user to get started with their input. The watermark text is visible when value is empty or null.

{% tabs %}

{% highlight c# %}

	numericTextBox.Watermark = "Principal Amount";
	
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" Watermark="Principal Amount" />
	
{% endhighlight %}

{% endtabs %}


![](images/WaterMark.png)
