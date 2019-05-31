---
layout: post
title: Parsing in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to enable the parsing mode for NumericUpDown control.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Parsing the Value

The value of NumericUpDown is parsed based on the ParsingMode property. ParsingMode is a type of Parsers; it can be enum of Double and Decimal. You have options to update the value in double or decimal.

The following code demonstrates the decimal parsing mode, which can be set using the ParsingMode property.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="NumericUpDown" Value="123.45" ParsingMode="Decimal" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.ParsingMode=Parsers.Decimal;
NumericUpDown.Value = 123.45;
this.Content = NumericUpDown;
	
{% endhighlight %}

{% endtabs %}

N> The default value of ParsingMode is Double.

![ParsingMode](images/value.png)
