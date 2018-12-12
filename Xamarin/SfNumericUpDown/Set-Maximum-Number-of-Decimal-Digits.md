---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Set Maximum Number of Decimal Digits

The maximum number of digits to be displayed after the decimal point can be specified by using `MaximumDecimalDigits `(https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms~Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown~MaximumDecimalDigits.html) property. 

N> The `MaximumDecimalDigits `(https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms~Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown~MaximumDecimalDigits.html) property can be provided with positive value only.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" MaximumDecimalDigits ="2"/>
	
{% endhighlight %}


{% highlight C# %}

	numericUpDown.MaximumDecimalDigits  = 2;

{% endhighlight %}

{% endtabs %}
