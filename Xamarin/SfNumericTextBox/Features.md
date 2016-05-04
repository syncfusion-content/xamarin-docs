---
layout: post
title: Various features in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed and nullable value support in NumericTextBox.
platform: Xamarin.Forms
control: NumericTextBox
documentation: ug
---
# Features

## Maximum Number Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumNumberDecimalDigits` property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% tabs %}

{% highlight c# %}

	numericTextBox.MaximumNumberDecimalDigits=2;
  
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% endtabs %}

![](images/MaximumNumberDecimalDigits.png)

## Nullable Value

The null values can be set in NumericTextBox `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% tabs %}

{% highlight c# %}

	numericTextBox.AllowNull=true;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" AllowNull="true" />
	
{% endhighlight %}

{% endtabs %}

![](images/AllowNull.png)

