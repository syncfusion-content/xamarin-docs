---
layout: post
title: Number Formatting in Xamarin Numeric Entry Control | Syncfusion
description: Learn about Number Formatting support in the Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Number Formatting in Xamarin Numeric Entry (SfNumericTextBox)

The values of the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) can be configured to display different formats such as currency and percentage.

## Format String in SfNumericTextBox

The [`FormatString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_FormatString) property determines the format specifier used to format the display text.

> **Note:** The control displays the formatted text when focus is lost. The default value for [`FormatString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_FormatString) is "n".

### Display Currency Notation in SfNumericTextBox

The specifier `c` displays the value with currency notation.
	
{% tabs %}	

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="1000" FormatString="c" />
	
{% endhighlight %}
	
{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.FormatString="c";
numericTextBox.Value=1000;
this.Content=numericTextBox;

{% endhighlight %}

{% endtabs %}
	
![Display the value with currency notation](images/currency.png)

### Display Number Notation in SfNumericTextBox

The specifier `n` displays the value in number format.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="1000" FormatString="n" />
	
{% endhighlight %}
	
{% highlight c# %}
	
SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.FormatString="n";
numericTextBox.Value=1000;
this.Content=numericTextBox;
	 
{% endhighlight %}

{% endtabs %}

![Display value with number notation](images/number.png)

### Display Percentage Notation in SfNumericTextBox

The specifier `p` displays the value in percentage format.
	
{% tabs %}	

{% highlight xaml %}

	<syncfusion:SfNumericTextBox  Value="1000" FormatString="p" />
	
{% endhighlight %}
	
{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.FormatString="p";
numericTextBox.Value=1000;
this.Content=numericTextBox;
	 
{% endhighlight %}

{% endtabs %}
	
![Display the value with percentage mode](images/percentage.png)

> **Note:** Instead of using the above [`FormatString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_FormatString) types, you can provide any symbol or value as a string in the `FormatString` property, which will be appended to the value in the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html).

By passing any string, you can append it to the value of the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html).

{% tabs %}	

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="23" FormatString="years" MaximumNumberDecimalDigits="0"/>
	
{% endhighlight %}
	
{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();
numericTextBox.FormatString = "years";
numericTextBox.MaximumNumberDecimalDigits = 0;
numericTextBox.Value = 23;
this.Content = numericTextBox;
	 
{% endhighlight %}

{% endtabs %}


![Display the value with custom format string](images/years.png)

## Compute to Percentage in SfNumericTextBox

When the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) is in percentage format, the value can be displayed in two ways:

- **[`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.PercentDisplayMode.html#Syncfusion_SfNumericTextBox_XForms_PercentDisplayMode_Value):** Displays the actual value with a percentage symbol.

{% capture codesnippet1 %}

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox FormatString="p" Value="1000"  PercentDisplayMode="Value" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.PercentDisplayMode=PercentDisplayMode.Value;
numericTextBox.FormatString="p";
numericTextBox.Value=1000;
this.content=numericTextBox;

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

![Display the value with percent display mode is value](images/percentage.png)


* [`Compute`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.PercentDisplayMode.html#Syncfusion_SfNumericTextBox_XForms_PercentDisplayMode_Compute): Displays the computed value with percentage symbol.

{% capture codesnippet2 %}

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox FormatString="p" Value="1000"  PercentDisplayMode="Compute" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.PercentDisplayMode=PercentDisplayMode.Compute;
numericTextBox.FormatString="p";
numericTextBox.Value=1000;
this.Content=numericTextBox;

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

![Display the value with percent display mode is compute](images/percentagevalue.png)

## Enable group separator in SfNumericTextBox 

[`EnableGroupSeparator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_EnableGroupSeparator) property is used to get rid of the comma in the value of [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html).

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="12345" EnableGroupSeparator="True" />
	
{% endhighlight %}

{% highlight c# %}
 
SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value=12345;
numericTextBox.EnableGroupSeparator = true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display the value with enable group separator](images/enablegroupseparator.PNG)

## Group Separator Modes in SfNumericTextBox

[`GroupSeparatorMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_GroupSeparatorMode) provides two states for displaying the group separator:

- **Always**: Displays the separator while typing.
- **[`LostFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.GroupSeparatorMode.html#Syncfusion_SfNumericTextBox_XForms_GroupSeparatorMode_LostFocus):** Enables the separator when the control loses focus.

> **Note:** The [`EnableGroupSeparator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_EnableGroupSeparator) property must be enabled to use the [`GroupSeparatorMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_GroupSeparatorMode).

{% tabs %}

{% highlight xaml %}
 
   <numeric:SfNumericTextBox Value="123456" FormatString="n" GroupSeparatorMode="Always" EnableGroupSeparator="True"/>

{% endhighlight %}

{% highlight c# %}

      SfNumericTextBox numericTextBox = new SfNumericTextBox();
            numericTextBox.Value = 123456;
            numericTextBox.FormatString = "n";
            numericTextBox.GroupSeparatorMode = GroupSeparatorMode.Always;
            numericTextBox.EnableGroupSeparator = true;
            this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display the value with enabled group separator](images/SeparatorMode.png)

## See Also

- [How to truncate the trailing zeros in SfNumericTextBox](https://support.syncfusion.com/kb/article/10127/how-to-truncate-the-trailing-zeros-in-xamarin-forms-numeric-control-sfnumerictextbox)
- [How to set customized currency symbol in SfNumericTextBox](https://support.syncfusion.com/kb/article/9131/how-to-set-customized-currency-symbol-in-xamarinforms-numeric-controls)
- [How to display the value with a currency symbol in SfNumericTextBox](https://support.syncfusion.com/kb/article/9143/how-to-display-the-value-with-currency-symbol-in-xamarinforms-numeric-controls)
