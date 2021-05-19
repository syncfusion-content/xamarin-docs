---
layout: post
title: Parsing the Value in Xamarin NumericUpDown control | Syncfusion
description: Learn here all about Parsing the Value support in Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control and more.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Parsing the Value in Xamarin NumericUpDown (SfNumericUpDown)

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
