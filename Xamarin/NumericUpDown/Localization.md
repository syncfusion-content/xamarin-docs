---
layout: post
title: Localization in Xamarin NumericUpDown Control | Syncfusion
description: Learn about localization support in the Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Localization in Xamarin NumericUpDown (SfNumericUpDown)

The [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) control allows localization of its value according to specific cultures using the [`Culture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Culture) property. This property can be set with a `System.Globalization.CultureInfo` object instance to specify the desired culture.

> **Note:** The `Culture` property cannot be set in XAML.
{% tabs %}
	
{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Value="123456" FormatString="c"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.Culture = new System.Globalization.CultureInfo("hi-IN");
	 
{% endhighlight %}

{% endtabs %}


![Display the SfNumericUpDown control with culture](images/Culture.png)

## See Also

- [How to Change the Culture of SfNumericUpDown](https://support.syncfusion.com/kb/article/6971/does-sfnumericupdown-responds-change-in-culture)

- [How to Set a Customized Currency Symbol in SfNumericUpDown](https://support.syncfusion.com/kb/article/9119/how-to-configure-a-certain-currency-symbol-in-xamarincontrols-with-numbers-on-forms)

- [How to Display the Value with Currency Symbol in SfNumericUpDown](https://support.syncfusion.com/kb/article/9141/how-to-display-the-value-with-currency-symbol-in-xamarinforms-numeric-controls)

- [How to Get the Localized Return Key on the iOS Keyboard in SfNumericUpDown](https://support.syncfusion.com/kb/article/7039/how-to-get-the-localized-return-key-on-the-ios-keyboard-in-xamarinforms-numeric-controls)
