---
layout: post
title: Parsing the Value in Xamarin Numeric Entry control | Syncfusion
description: Learn here all about Parsing the Value support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Parsing the Value in Xamarin Numeric Entry (SfNumericTextBox)

Value of the SfNumericTextBox gets parsed based on `ParserMode` property. ParsingMode is of type Parsers which is enum of Double and Decimal. Hence we have option to display the value in double or decimal. 

Following code shows the `Double` parsing mode which can be set through `ParserMode` property.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123.45" ParserMode="Double" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.ParserMode=Parsers.Double;
numericTextBox.Value = 123.45;
this.Content = numericTextBox;
	
{% endhighlight %}

{% endtabs %}

N>The default Value for `ParserMode` is Decimal.

![Shows a parser mode behavior](images/value.png)
