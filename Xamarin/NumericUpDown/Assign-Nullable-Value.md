---
layout: post
title: Assign Nullable Value in Xamarin NumericUpDown control | Syncfusion
description: Learn here all about Assign Nullable Value support in Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control and more.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Assign Nullable Value in Xamarin NumericUpDown (SfNumericUpDown)

The null values can be set in SfNumericUpDown `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" AllowNull="true"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.AllowNull=true;

{% endhighlight %}



{% endtabs %}

![AllowNull](images/AllowNull.png)


## Set Hint Text

The `WaterMark` property can be used to provide a hint that helps the user to get started with their input. The watermark text is visible when value is empty or null.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Watermark="NumericUpDown"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.Watermark = "NumericUpDown";
	
{% endhighlight %}


{% endtabs %}


![WaterMark](images/WaterMark.png)
