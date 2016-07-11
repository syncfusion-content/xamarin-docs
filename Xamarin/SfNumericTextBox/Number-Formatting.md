---
layout: post
title: Number Formatting in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to add format String, enable parser mode and percent display mode for NumericTextBox control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Number Formatting

## Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

It has three types,

* `c` - Display the value with currency notation.
	
{% tabs %}	
	
{% highlight c# %}
	
	numericTextBox.FormatString="c";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" FormatString="c" />
	
{% endhighlight %}

{% endtabs %}
	

* `n` – Display the value in number format.

{% tabs %}
	
{% highlight c# %}
	
	numericTextBox.FormatString="n";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" FormatString="n" />
	
{% endhighlight %}

{% endtabs %}
	

* `p` – Display the value in percentage.
	
{% tabs %}	
	
{% highlight c# %}

	numericTextBox.FormatString="p";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" FormatString="p" />
	
{% endhighlight %}

{% endtabs %}
	
N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in SfNumericTextBox. 

![](images/FormatString.png)

## Parser Mode

The value of the SfNumericTextBox can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParsingMode` is Double.

{% tabs %}

{% highlight c# %}

	numericTextBox.ParserMode=ParserMode.Decimal;
	  
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" ParserMode="Decimal" />
	
{% endhighlight %}

{% endtabs %}

![](images/ParserMode.png)

## Percent Display Mode

The `PercentDisplayMode` property can be used to display numeric data in Percent mode. 

N> The control displays the percent value on lost focus. 

It provides the following options:

* `Value`: Displays the value with percentage symbol.

{% tabs %}

{% highlight c# %}

	numericTextBox.PercentDisplayMode=PercentDisplayMode.Value;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" PercentDisplayMode="Value" />
	
{% endhighlight %}

{% endtabs %}

* `Compute`: Displays the computed value with percentage symbol.

{% tabs %}

{% highlight c# %}

	numericTextBox.PercentDisplayMode=PercentDisplayMode.Compute;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" PercentDisplayMode="Compute" />
	
{% endhighlight %}

{% endtabs %}

![](images/PercentageDisplayMode.png)


