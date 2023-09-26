---
layout: post
title: Localization in Xamarin Numeric Entry control | Syncfusion
description: Learn here all about Localization support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Localization in Xamarin Numeric Entry (SfNumericTextBox)

The [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) value can be localized to any specific culture. It can also be specified by setting the [`Culture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Culture) property with `System.Globalization.CultureInfo` object instance.

{% tabs %}
	
{% highlight xaml %}

	<numeric:SfNumericTextBox Value="12345"  x:Name="numericTextBox" FormatString="c"/>
	
{% endhighlight %}

{% highlight C# %}

   numericTextBox.Culture = new System.Globalization.CultureInfo("fr-FR");
	 
{% endhighlight %}

{% endtabs %}

![Display the culter applied value image](images/Culture.png)

## See also

[How to change the culture of SfNumericTextBox](https://support.syncfusion.com/kb/article/6845/how-to-change-the-culture-of-numerictextbox?isInternalRefresh=False)

[How to get the localized return key on the iOS keyboard in Xamarin.Forms numeric controls](https://support.syncfusion.com/kb/article/10234/how-to-get-the-localized-return-key-on-the-ios-keyboard-in-xamarin-forms-numeric-controls?isInternalRefresh=False)

