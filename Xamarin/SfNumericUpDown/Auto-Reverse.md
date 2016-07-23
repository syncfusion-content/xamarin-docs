---
layout: post
title: Watermark support in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to add water mark text to NumericUpDown.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Auto Reverse

While incrementing, the control will start from Minimum value once it reaches the Maximum value and vice-versa.

N> By default the property value is false.

{% tabs %}

{% highlight C# %}

	numericUpDown.AutoReverse = true;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" AutoReverse="true"/>
	
{% endhighlight %}

{% endtabs %}

## Continuous Spinning Between Ranges

User can restrict the Values between a specific range by setting `Maximum` and `Minimum` property value.

N> By default the minimum property value is 0 and maximum property value is 100.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Minimum="10" Maximum="50"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.Minimum = 0;
	numerucUpDown.Maximum = 100

{% endhighlight %}

{% endtabs %}

![](images/maximum.png)

![](images/minimum.png)

## Set Increment

Frequency in which values gets incremented can be decided using `StepValue` property.

N> By default the property value is 1.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" StepValue="6"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.StepValue = 6;

{% endhighlight %}

{% endtabs %}

