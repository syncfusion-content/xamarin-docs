---
layout: post
title: Set Max Number of Decimal Digits in Xamarin Numeric Entry | Syncfusion
description: Learn here all about Set Maximum Number of Decimal Digits support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Decimal Digits in Xamarin Numeric Entry

## Set Maximum Number of Decimal Digits in Xamarin Numeric Entry

The maximum number of digits to be displayed after the decimal point can be specified by using the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_MaximumNumberDecimalDigits) property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123.456" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123.456;
numericTextBox.MaximumNumberDecimalDigits=2;
this.Content = numericTextBox;
  
{% endhighlight %}

{% endtabs %}

![Display the textbox value](images/MaximumNumberDecimalDigits.png)

## Remove Default Decimal Digits in Xamarin Numeric Entry

Based on the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_MaximumNumberDecimalDigits) property, the default number of decimal digits is displayed. By disabling the [`AllowDefaultDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_AllowDefaultDecimalDigits) Boolean property, those default digits can be removed from the numeric entry view.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123" AllowDefaultDecimalDigits="False" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% highlight c# %}

            SfNumericTextBox numericTextBox = new SfNumericTextBox();
            numericTextBox.Value = 123;
            numericTextBox.MaximumNumberDecimalDigits = 2;
            numericTextBox.AllowDefaultDecimalDigits = false;
            this.Content = numericTextBox;
  
{% endhighlight %}

{% endtabs %}

![Display the textbox value without default decimal digits](images/AllowDefaultDecimalDigits.png)

## See also

[How to set the MaximumDecimalDigits in SfNumericTextBox](https://www.syncfusion.com/kb/7593/how-to-set-the-maximumdecimaldigits-in-numerictextbox)
