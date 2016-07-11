---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Features

## MaximumNumberDecimalDigits

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


## Nullable Value

The null values can be set in SfNumericUpDown `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% tabs %}

{% highlight C# %}

	numericUpDown.AllowNull=true;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" AllowNull="true"/>
	
{% endhighlight %}

{% endtabs %}


![](images/AllowNull.png)

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


## Range

User can restrict the Values between a specific range by setting `Maximum` and `Minimum` property value.

N> By default the minimum property value is 0 and maximum property value is 100.

{% tabs %}

{% highlight C# %}

	numericUpDown.Minimum = 0;
	numerucUpDown.Maximum = 100

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Minimum="10" Maximum="50"/>
	
{% endhighlight %}

{% endtabs %}

![](images/maximum.png)

![](images/minimum.png)

## Step Value

Frequency in which values gets incremented can be decided using `StepValue` property.

N> By default the property value is 1.

{% tabs %}

{% highlight C# %}

	numericUpDown.StepValue = 6;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" StepValue="6"/>
	
{% endhighlight %}

{% endtabs %}

