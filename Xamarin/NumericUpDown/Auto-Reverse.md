---
layout: post
title: Watermark support in Syncfusion NumericUpDown for Xamarin.Forms
description: This section explain how to set the auto reverse, continuous spinning between ranges for Syncfusion NumericUpDown.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Auto Reverse in Xamarin NumericUpDown (SfNumericUpDown)

While incrementing, the control will start from Minimum value once it reaches the Maximum value and vice-versa.

N> By default the property value is false.

{% tabs %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.AutoReverse = true;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" AutoReverse="true"/>
	
{% endhighlight %}

{% endtabs %}

## Continuous Spinning Between Ranges

User can restrict the Values between a specific range by setting `Maximum` and `Minimum` property value.

N> By default, the value of minimum property is Double.MinValue and the value of maximum property is Double.MaxValue.
In iOS, if typed value is less than minimum value, the minimum value will be validated.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Minimum="10" Maximum="100"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.Minimum = 0;
numericUpDown.Maximum = 100;
this.Content = numericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the value with maximum](images/maximum.png)

![Display the value with minimum](images/minimum.png)

## Set Increment

Frequency in which values gets incremented can be decided using `StepValue` property.

N> By default the property value is 1.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" StepValue="6"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.StepValue = 6;
this.Content = numericUpDown;

{% endhighlight %}

{% endtabs %}

## Set IsEditable

This property is used to decide whether users need to perform edit operation in input field.

N> By default, the value of IsEditable property is true.
{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown Value="123"  IsEditable="True"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.IsEditable = true;

{% endhighlight %}

{% endtabs %}

## See also

[How to restrict the values of SfNumericUpDown within certain range](https://www.syncfusion.com/kb/7687/how-to-restrict-the-values-of-sfnumericupdown-within-certain-range)

[How to set AutoReverse property in SfNumericUpDown](https://www.syncfusion.com/kb/7686/how-to-set-autoreverse-property-in-sfnumericupdown)