---
layout: post
title: Watermark support in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to add water mark text to NumericUpDown.
platform: Xamarin.Forms
control: NumericUpDown
documentation: ug
---
# WaterMark

The `WaterMark` property can be used to provide a hint that helps the user to get started with their input. The watermark text is visible when value is empty or null.

{% tabs %}

{% highlight C# %}

	numericUpDown.Watermark = "Principal Amount";
	
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Watermark="Principal Amount"/>
	
{% endhighlight %}

{% endtabs %}



![](images/WaterMark.png)
