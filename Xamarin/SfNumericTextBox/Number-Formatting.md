---
layout: post
title: Number Formatting in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to add format String, enable parser mode and percent display mode for NumericTextBox control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Number Formatting

The Values of the SfNumericTextBox can be configured to display different formats like currency format, percent format etc. 

## Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

### Display Currency Notation

`c` - Displays the value with currency notation.
	
{% tabs %}	

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" FormatString="c" />
	
{% endhighlight %}
	
{% highlight c# %}
	
	numericTextBox.FormatString="c";
	 
{% endhighlight %}

{% endtabs %}
	
### Display Number Notation

`n` – Displays the value in number format.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" FormatString="n" />
	
{% endhighlight %}
	
{% highlight c# %}
	
	numericTextBox.FormatString="n";
	 
{% endhighlight %}

{% endtabs %}

### Display Percentage Notation

`p` – Displays the value in percentage.
	
{% tabs %}	

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" FormatString="p" />
	
{% endhighlight %}
	
{% highlight c# %}

	numericTextBox.FormatString="p";
	 
{% endhighlight %}

{% endtabs %}
	
N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in SfNumericTextBox. 

![](images/FormatString.png)

## Parser Input Value

The value of the SfNumericTextBox can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParsingMode` is Double.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" ParsingMode="Decimal" />
	
{% endhighlight %}

{% highlight c# %}

	numericTextBox.ParsingMode=ParsingMode.Decimal;
	  
{% endhighlight %}

{% endtabs %}

![](images/ParserMode.png)

## Compute to Percentage

The `PercentDisplayMode` property can be used to display numeric data in Percent mode. 

N> The control displays the percent value on lost focus. 

It provides the following options:

* `Value`: Displays the value with percentage symbol.

{% tabs %}
{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" PercentDisplayMode="Value" />
	
{% endhighlight %}

{% highlight c# %}

	numericTextBox.PercentDisplayMode=PercentDisplayMode.Value;

{% endhighlight %}

{% endtabs %}

* `Compute`: Displays the computed value with percentage symbol.

{% tabs %}
{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" PercentDisplayMode="Compute" />
	
{% endhighlight %}

{% highlight c# %}

	numericTextBox.PercentDisplayMode=PercentDisplayMode.Compute;

{% endhighlight %}

{% endtabs %}

![](images/PercentageDisplayMode.png)


