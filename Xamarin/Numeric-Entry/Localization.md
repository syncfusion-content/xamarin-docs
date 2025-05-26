---
layout: post
title: Localization in Xamarin Numeric Entry Control | Syncfusion
description: Learn about Localization support in the Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Localization in Xamarin Numeric Entry (SfNumericTextBox)

The [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) control supports localization, allowing its value to be formatted according to a specific culture. You can achieve this by setting the [`Culture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Culture) property with an instance of `System.Globalization.CultureInfo`.

{% tabs %}
	
{% highlight xaml %}

	<numeric:SfNumericTextBox Value="12345"  x:Name="numericTextBox" FormatString="c"/>
	
{% endhighlight %}

{% highlight C# %}

   numericTextBox.Culture = new System.Globalization.CultureInfo("fr-FR");
{% endhighlight %}

{% endtabs %}

![Display the culturally formatted value](images/Culture.png)

## See Also

- [How to change the culture of SfNumericTextBox](https://support.syncfusion.com/kb/article/6845/how-to-change-the-culture-of-numerictextbox)
- [How to get the localized return key on the iOS keyboard in Xamarin.Forms numeric controls](https://support.syncfusion.com/kb/article/10234/how-to-get-the-localized-return-key-on-the-ios-keyboard-in-xamarin-forms-numeric-controls)
