---
layout: post
title: Number Formatting in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to add format String, enable parser mode and percent display mode for NumericUpDown control.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Number Formatting

The Values of the SfNumericUpDown can be configured to display different formats like currency format, percent format etc. 

## Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n". 

### Display Currency Notation

`c` - Displays the value with currency notation.

{% tabs %}
	
{% highlight C# %}
	SfNumericUpDown numericUpDown=new SfNumericUpDown();
	numericUpDown.FormatString="c";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="c"/>
	
{% endhighlight %}

{% endtabs %}

### Display Number Notation

`n` – Displays the value in number format.
	
{% tabs %}	

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="n"/>
	
{% endhighlight %}

	
{% highlight C# %}
	
	SfNumericUpDown numericUpDown=new SfNumericUpDown();
	numericUpDown.FormatString="n";
	 
{% endhighlight %}

{% endtabs %}

### Display Percentage Notation

`p` – Displays the value in Percentage.
	
{% tabs %}	
	
{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
	numericUpDown.FormatString="p";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="p"/>
	
{% endhighlight %}

{% endtabs %}

	
N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in SfNumericUpDown.

![](images/format.png)

## Parser Input Value

The value of the SfNumericUpDown can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal. The default Value for `ParsingMode` is Double.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" ParsingMode="Decimal"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
	numericUpDown.ParsingMode=ParsingMode.Decimal;
	  
{% endhighlight %}


{% endtabs %}


![](images/ParserMode.png)

## Compute to Percentage

When the control is in percentage format, the value can be displayed in two ways as follows

* `Value`: Displays the actual value with percentage symbol.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" PercentDisplayMode="Value"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
	numericUpDown.FormatString="p";
	numericUpDown.PercentDisplayMode=PercentDisplayMode.Value;

{% endhighlight %}

{% endtabs %}


* `Compute`: Displays the value computed by 100 with percentage symbol.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" PercentDisplayMode="Compute"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
	numericUpDown.FormatString="p";
	numericUpDown.PercentDisplayMode=PercentDisplayMode.Compute;

{% endhighlight %}

{% endtabs %}

N> The control displays the percent value on lost focus. 


![](images/PercentageDisplayMode.png)