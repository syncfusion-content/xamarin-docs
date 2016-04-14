---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin.Forms
control: NumericUpDown
documentation: ug
---
# Features

## MaximumNumberDecimalDigits

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumNumberDecimalDigits` property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% highlight C# %}

	sfNumericUpDown.MaximumNumberDecimalDigits = 2;

{% endhighlight %}

## Nullable Value

The null values can be set in NumericUpDown `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% highlight C# %}

	SfNumericUpDown.AllowNull=true;

{% endhighlight %}

![](images/AllowNull.png)

## AutoReverse

While incrementing, the control will start from Minimum once it reaches the Maximum and vice-versa.

N> By default the property value is false.

{% highlight C# %}

	sfNumericUpDown.AutoReverse = true;

{% endhighlight %}

## Range

User can restrict the Values between a specific range by setting `Maximum` and `Minimum` property value.

N> By default the minimum property value is 0 and maximum property value is 100.

{% highlight C# %}

	sfNumericUpDown.Minimum = 10;
	sfNumerucUpDown.Maximum = 50

{% endhighlight %}

![](images/maximum.png)

![](images/minimum.png)

## Step Value

Frequency in which values gets incremented can be decided using `StepValue` property.

N> By default the property value is 1.

{% highlight C# %}

	sfNumericUpDown.StepValue = 6;

{% endhighlight %}
