---
layout: post
title: Number Formatting in Syncfusion NumericTextBox for Xamarin.Forms
description: Learn how to add format String, enable parser mode and percent display mode for NumericTextBox control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Number Formatting in Xamarin Numeric Entry (SfNumericTextBox)

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
	
![Display the value with currency notation](images/currency.png)

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

![Display value with number notation](images/number.png)

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
	
![Display the value with Percentage mode](images/percentage.png)

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


![Display the value with custom format string](images/years.png)

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

![Display the value with percent display mode is value](images/percentage.png)


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

![Display the value with percent display mode is compute](images/percentagevalue.png)

## Set EnableGroupSeparator 

`EnableGroupSeparator` property is used to get rid of the comma in the Value of SfNumericTextBox.

{% tabs %}

{% highlight c# %}
 
SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value=12345;
numericTextBox.EnableGroupSeparator = true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display the value with enable group separator](images/enablegroupseparator.png)

## See also

[How to truncate the trailing zero's in SfNumericTextBox]( https://www.syncfusion.com/kb/11749/how-to-truncate-the-trailing-zeros-in-xamarin-forms-numeric-control-sfnumerictextbox)

[How to set customized currency symbol in SfNumericTextBox](https://www.syncfusion.com/kb/10445/how-to-set-customized-currency-symbol-in-xamarin-forms-numeric-controls)

[How to display the value with currency symbol in SfNumericTextBox](https://www.syncfusion.com/kb/10443/how-to-display-the-value-with-currency-symbol-in-xamarin-forms-numeric-controls)


