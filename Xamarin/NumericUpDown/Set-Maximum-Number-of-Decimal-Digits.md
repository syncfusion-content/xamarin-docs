---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Set Maximum Number of Decimal Digits

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