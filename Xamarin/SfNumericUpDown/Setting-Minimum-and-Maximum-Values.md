---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Setting Minimum and Maximum Values

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumNumberDecimalDigits` property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% tabs %}

{% highlight C# %}

	numericUpDown.MaximumNumberDecimalDigits = 2;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" MaximumNumberDecimalDigits="2"/>
	
{% endhighlight %}

{% endtabs %}

## AutoReverse

While incrementing, the control will start from Minimum once it reaches the Maximum and vice-versa.

N> By default the property value is false.

{% tabs %}

{% highlight C# %}

	numericUpDown.AutoReverse = true;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" AutoReverse="true"/>
	
{% endhighlight %}

{% endtabs %}


