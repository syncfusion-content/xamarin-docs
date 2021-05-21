---
layout: post
title: Set Max Number of Decimal Digits in Xamarin NumericUpDown | Syncfusion
description: Learn here all about Set Maximum Number of Decimal Digits support in Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control and more.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Set Maximum Number of Decimal Digits in Xamarin NumericUpDown

The maximum number of digits to be displayed after the decimal point can be specified by using [`MaximumDecimalDigits `](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_MaximumDecimalDigits) property. 

N> The [`MaximumDecimalDigits `](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_MaximumDecimalDigits). The MaximumDecimalDigits property is provided with positive value only. By default, the value of this property is 2.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" MaximumDecimalDigits ="3"/>
	
{% endhighlight %}


{% highlight C# %}

	numericUpDown.MaximumDecimalDigits  = 3;

{% endhighlight %}

{% endtabs %}

![Display the SfNumericUpDown control with MaximumDecimalDigits](images/MaximumDecimalDigits.png)
