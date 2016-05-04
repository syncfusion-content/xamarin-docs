---
layout: post
title: Number Formatting in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to add format String, enable parser mode and percent display mode for NumericUpDown control.
platform: Xamarin.Forms
control: NumericUpDown
documentation: ug
---
# Number Formatting

## Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

It has three types,

* `c` - Display the value with currency notation.

{% tabs %}
	
{% highlight C# %}
	
	numericUpDown.FormatString="c";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="c"/>
	
{% endhighlight %}

{% endtabs %}

* `n` – Display the value in number format.
	
{% tabs %}	
	
{% highlight C# %}
	
	numericUpDown.FormatString="n";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="n"/>
	
{% endhighlight %}

{% endtabs %}

* `p` – Display the value in Percentage.
	
{% tabs %}	
	
{% highlight C# %}

	numericUpDown.FormatString="p";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="p"/>
	
{% endhighlight %}

{% endtabs %}

	
N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in NumericUpDown.

![](images/format.png)

## Parser Mode

The value of the NumericUpDown can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParsingMode` is Double.

{% tabs %}

{% highlight C# %}

	numericUpDown.ParserMode=ParserMode.Decimal;
	  
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" ParserMode="Decimal"/>
	
{% endhighlight %}

{% endtabs %}


![](images/ParserMode.png)

## Percent Display Mode

The `PercentDisplayMode` property can be used to display numeric data in Percent mode. 

N> The control displays the percent value on lost focus. 

It provides the following options:

* `Value`: Displays the value with percentage symbol.

{% tabs %}

{% highlight C# %}

	numericUpDown.PercentDisplayMode=PercentDisplayMode.Value;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" PercentDisplayMode="Value"/>
	
{% endhighlight %}

{% endtabs %}


* `Compute`: Displays the computed value with percentage symbol.

{% tabs %}

{% highlight C# %}

	numericUpDown.PercentDisplayMode=PercentDisplayMode.Compute;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" PercentDisplayMode="Compute"/>
	
{% endhighlight %}

{% endtabs %}


![](images/PercentageDisplayMode.png)