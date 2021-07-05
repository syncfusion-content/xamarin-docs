---
layout: post
title: Localization in Xamarin NumericUpDown control | Syncfusion
description: Learn here all about Localization support in Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control and more.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Localization in Xamarin NumericUpDown (SfNumericUpDown)

The [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) value can be localized to any specific culture. It can be specified by setting the [`Culture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Culture) property with `System.Globalization.CultureInfo` object instance.

N> You cannot set value to the Culture property in XAML.

{% tabs %}
	
{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Value="123456" FormatString="c"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.Culture = new System.Globalization.CultureInfo("hi-IN");
	 
{% endhighlight %}

{% endtabs %}


![Display the SfNumericUpDown control with culture](images/Culture.png)

## See also

[How to change the culture of SfNumericUpDown](https://www.syncfusion.com/kb/7689/does-sfnumericupdown-responds-change-in-culture)

[How to set customized currency symbol in SfNumericUpDown](https://www.syncfusion.com/kb/10446/how-to-set-customized-currency-symbol-in-xamarin-forms-numeric-controls)

[How to display the value with currency symbol in SfNumericUpDown](https://www.syncfusion.com/kb/10444/how-to-display-the-value-with-currency-symbol-in-xamarin-forms-numeric-controls)

[How to get the localized return key on the iOS keyboard in SfNumericUpDown](https://www.syncfusion.com/kb/8074/how-to-get-the-localized-return-key-on-the-ios-keyboard-in-xamarin-forms-numeric-controls)


