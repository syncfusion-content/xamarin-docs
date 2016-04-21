---
layout: post
title: Number Formatting in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to add format String, enable parser mode and percent display mode for NumericTextBox control.
platform: Xamarin.Forms
control: NumericTextBox
documentation: ug
---
# Number Formatting

## Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

It has three types,

* `c` - Display the value with currency notation.
	
{% highlight c# %}
	
	numericTextBox.FormatString="c";
	 
{% endhighlight %}
	

* `n` – Display the value in number format.
	
{% highlight c# %}
	
	numericTextBox.FormatString="n";
	 
{% endhighlight %}
	

* `p` – Display the value in percentage.
	
{% highlight c# %}

	numericTextBox.FormatString="p";
	 
{% endhighlight %}
	
N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in NumericTextBox. 

![](images/FormatString.png)

## Parser Mode

The value of the NumericTextBox can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParsingMode` is Double.

{% highlight c# %}

	numericTextBox.ParserMode=ParserMode.Decimal;
	  
{% endhighlight %}

![](images/ParserMode.png)

## Percent Display Mode

The `PercentDisplayMode` property can be used to display numeric data in Percent mode. 

N> The control displays the percent value on lost focus. 

It provides the following options:

* `Value`: Displays the value with percentage symbol.

{% highlight c# %}

	numericTextBox.PercentDisplayMode=PercentDisplayMode.Value;

{% endhighlight %}

* `Compute`: Displays the computed value with percentage symbol.

{% highlight c# %}

	numericTextBox.PercentDisplayMode=PercentDisplayMode.Compute;

{% endhighlight %}

![](images/PercentageDisplayMode.png)


