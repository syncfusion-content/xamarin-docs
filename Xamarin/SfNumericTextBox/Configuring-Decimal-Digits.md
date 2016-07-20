---
layout: post
title: Various features in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in NumericTextBox.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Configuring Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumNumberDecimalDigits` property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% highlight c# %}

	numericTextBox.MaximumNumberDecimalDigits=2;
  
{% endhighlight %}

{% endtabs %}

![](images/MaximumNumberDecimalDigits.png)

