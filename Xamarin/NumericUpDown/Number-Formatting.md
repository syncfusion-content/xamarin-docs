---
layout: post
title: Number Formatting in Syncfusion NumericUpDown for Xamarin.Forms
description: Learn how to apply format strings, enable parser mode, and use percent display mode in the NumericUpDown control.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Number Formatting in Xamarin NumericUpDown (SfNumericUpDown)

The [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) values can be configured to display in various formats, such as currency or percentage.

## Format String Support in SfNumericUpDown

The [`FormatString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_FormatString) property specifies the format specifier for the display text.

N> The control displays the formatted text when the focus is lost. The default Value of [`FormatString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_FormatString) is "n". 

### Display currency notation

`c` - Displays the value with currency notation.

{% tabs %}
	
{% highlight xaml %}

	<numeric:SfNumericUpDown FormatString="c"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.FormatString="c";
	 
{% endhighlight %}

{% endtabs %}

![Display value with currency notation](images/CurrencyValueformat.PNG)

### Displaying Percentage Notation

Use `p` to display values as percentages.
	
{% tabs %}	

{% highlight xaml %}

	<numeric:SfNumericUpDown  FormatString="p"/>
	
{% endhighlight %}
	
{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.FormatString="p";
	 
{% endhighlight %}


{% endtabs %}

![Display value with percentage notation](images/PercentageValueformat.PNG)

### Displaying Number Notation

Use `n` to display values in number format.
	
{% tabs %}	

{% highlight xaml %}

	<numeric:SfNumericUpDown  FormatString="n"/>
	
{% endhighlight %}

{% highlight C# %}
	
SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.FormatString="n";
	 
{% endhighlight %}

{% endtabs %}

N> Instead of using above [`FormatString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_FormatString) types, you can provide any symbol or value as string in [`FormatString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_FormatString) property which will be appended with the value in [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html).

![Display the value with number notation](images/format.png)

## Compute to percentage

When the control is in percentage format, the value can be displayed in two ways as follows

* [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Value) : Displays the actual value with percentage symbol.

{% capture codesnippet1 %}

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown  Value="5" FormatString="p" PercentDisplayMode="Value"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.Value = 5;
numericUpDown.FormatString="p";
numericUpDown.PercentDisplayMode=PercentDisplayMode.Value;

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

![Display value with PercentageDisplayMode as Value](images/PercentDisplayMode_Value.png)

* [`Compute`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.PercentDisplayMode.html#Syncfusion_SfNumericUpDown_XForms_PercentDisplayMode_Compute) : Displays the value computed by 100 with percentage symbol.

{% capture codesnippet2 %}

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown Value="5" FormatString="p" PercentDisplayMode="Compute"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.Value = "5";
numericUpDown.FormatString="p";
numericUpDown.PercentDisplayMode=PercentDisplayMode.Compute;

{% endhighlight %}

{% endtabs %}

> **Note:** The control displays the percent value on lost focus.

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

![Display value with PercentageDisplayMode as Compute](images/PercentDisplayMode_Compute.png)

## Enabling Group Separator

The [`EnableGroupSeparator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_EnableGroupSeparator) property controls whether commas are used as group separators in the `SfNumericUpDown`.

{% tabs %}

{% highlight xaml %}

	   <numeric:SfNumericUpDown  Value="12345" EnableGroupSeparator="True"/>
	
{% endhighlight %}

{% highlight c# %}
 
SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.Value=12345;
NumericUpDown.EnableGroupSeparator = true;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the SfNumericUpDown control with EnableGroupSeparator](images/enablegroupseparator.PNG)

## See Also

[Providing String Formats Support in SfNumericUpDown](https://support.syncfusion.com/kb/article/6976/does-sfnumericupdown-supports-other-formats)
