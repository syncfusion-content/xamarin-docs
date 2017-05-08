---
layout: post
title: Parsing in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to enable the parser mode for NumericTextBox control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Parsing the Value

Value of the SfNumericTextBox gets parsed based on `ParserMode` property. ParsingMode is of type Parsers which is enum of Double and Decimal. Hence we have option to display the value in double or decimal. 

Following code shows the Decimal parsing mode which can be set through `ParserMode` property.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123.45" ParserMode="Decimal" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.ParserMode=Parsers.Decimal;
numericTextBox.Value = 123.45;
this.Content = numericTextBox;
	
{% endhighlight %}

{% endtabs %}

N>The default Value for `ParserMode` is Double.

![](images/value.png)
