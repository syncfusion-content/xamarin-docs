---
layout: post
title: Number Formatting in Syncfusion NumericUpDown for Xamarin.Forms
description: Learn how to add format String, enable parser mode and percent display mode for NumericUpDown control.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Number Formatting in Xamarin NumericUpDown (SfNumericUpDown)

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

### Display Percentage Notation

`p` – Displays the value in percentage.
	
{% tabs %}	
	
{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.FormatString="p";
	 
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="p"/>
	
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

N> Instead of using above `FormatString` types, we can provide any symbol or value as string in `FormatString` property which will be appended with the value in SfNumericUpDown.

![Display the value with number notation](images/format.png)

## Compute to Percentage

When the control is in percentage format, the value can be displayed in two ways as follows

* `Value`: Displays the actual value with percentage symbol.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Value="5" FormatString="p" PercentDisplayMode="Value"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.Value = 5;
numericUpDown.FormatString="p";
numericUpDown.PercentDisplayMode=PercentDisplayMode.Value;

{% endhighlight %}

{% endtabs %}

![Display the value with PercentageDisplayMode as Compute](images/PercentDisplayMode_Value.png)

* `Compute`: Displays the value computed by 100 with percentage symbol.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Value="5" FormatString="p" PercentDisplayMode="Compute"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.Value = "5";
numericUpDown.FormatString="p";
numericUpDown.PercentDisplayMode=PercentDisplayMode.Compute;

{% endhighlight %}

{% endtabs %}

N> The control displays the percent value on lost focus. 

![Display the value with PercentageDisplayMode as Compute](images/PercentDisplayMode_Compute.png)

## Set EnableGroupSeparator 

The `EnableGroupSeparator` property is used to get rid of the comma in the Value of SfNumericUpDown.

{% tabs %}

{% highlight xaml %}

	   <numeric:SfNumericUpDown x:Name="NumericUpDown" Value="12345" EnableGroupSeparator="True"/>
	
{% endhighlight %}

{% highlight c# %}
 
SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.Value=12345;
NumericUpDown.EnableGroupSeparator = true;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the SfNumericUpDown control with EnableGroupSeparator](images/enablegroupseparator.png)

## See also

[How to provide string formats support in SfNumericUpDown](https://www.syncfusion.com/kb/7690/does-sfnumericupdown-supports-other-formats)