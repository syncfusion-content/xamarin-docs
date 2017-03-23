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

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="1000" FormatString="c" />
	
{% endhighlight %}
	
{% highlight c# %}

	SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.FormatString="c";
	numericTextBox.Value=1000;
	this.content=numericTextBox;

{% endhighlight %}

{% endtabs %}
	
![](images/currency.png)

### Display Number Notation

`n` – Displays the value in number format.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="1000" FormatString="n" />
	
{% endhighlight %}
	
{% highlight c# %}
	
    SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.FormatString="n";
	numericTextBox.Value=1000;
	this.content=numericTextBox;
	 
{% endhighlight %}

{% endtabs %}

![](images/number.png)

### Display Percentage Notation

`p` – Displays the value in percentage.
	
{% tabs %}	

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="1000" FormatString="p" />
	
{% endhighlight %}
	
{% highlight c# %}

    SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.FormatString="p";
	numericTextBox.Value=1000;
	this.content=numericTextBox;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/percentage.png)

N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in SfNumericTextBox. 

By passing any string , we can get the same as appended with the value of NumericTextBox

{% tabs %}	

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="1000" FormatString="years" />
	
{% endhighlight %}
	
{% highlight c# %}

    SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.FormatString="years";
	numericTextBox.Value=23;
	this.content=numericTextBox;
	 
{% endhighlight %}

{% endtabs %}


![](images/years.png)

## Compute to Percentage

When the NumericTextBox is in percentage format, the value can be displayed in two ways as follows

* `Value`: Displays the actual value with percentage symbol.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" FormatString="p" Value="1000"  PercentDisplayMode="Value" />
	
{% endhighlight %}

{% highlight c# %}

    SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.PercentDisplayMode=PercentDisplayMode.Value;
	numericTextBox.FormatString="p";
	numericTextBox.Value=1000;
	this.content=numericTextBox;

{% endhighlight %}

{% endtabs %}

![](images/percentage.png)


* `Compute`: Displays the computed value with percentage symbol.

{% tabs %}
{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" FormatString="p" Value="1000"  PercentDisplayMode="Compute" />
	
{% endhighlight %}

{% highlight c# %}

    SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.PercentDisplayMode=PercentDisplayMode.Compute;
	numericTextBox.FormatString="p";
	numericTextBox.Value=1000;
	this.content=numericTextBox;

{% endhighlight %}

{% endtabs %}

![](images/percentagevalue.png)


