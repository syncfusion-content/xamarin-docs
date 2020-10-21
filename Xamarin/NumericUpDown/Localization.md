---
layout: post
title: Localization in Syncfusion NumericUpDown control for Xamarin.Forms
description: This scetion expalin how to Localize the Syncfusion Xamarin.Forms SfNumericUpDown value and Change localization of return key text.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Localization in Xamarin NumericUpDown (SfNumericUpDown)

The SfNumericUpDown value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

N> You cannot set value to the Culture property in XAML.

{% tabs %}

{% highlight C# %}

	numericUpDown.Culture = new System.Globalization.CultureInfo("hi-IN");
	
{% endhighlight %}

{% endtabs %}

![Display the SfNumericUpDown control with culture](images/Culture.png)

## Change Localization of Return key text

The SfNumericUpDown provides the Localization support for the Return Key in soft keypad of iOS. We have provided the knowledge base document for the same. Please refer the Knowledge Base document from this [link.](https://www.syncfusion.com/kb/8074/how-to-localize-the-return-buttons-text-in-sfnumericupdown-in-xforms-ios)

## See also

[How to change the culture of SfNumericUpDown](https://www.syncfusion.com/kb/7689/does-sfnumericupdown-responds-change-in-culture)

[How to set customized currency symbol in SfNumericUpDown](https://www.syncfusion.com/kb/10446/how-to-set-customized-currency-symbol-in-xamarin-forms-numeric-controls)

[How to display the value with currency symbol in SfNumericUpDown](https://www.syncfusion.com/kb/10444/how-to-display-the-value-with-currency-symbol-in-xamarin-forms-numeric-controls)

[How to get the localized return key on the iOS keyboard in SfNumericUpDown](https://www.syncfusion.com/kb/8074/how-to-get-the-localized-return-key-on-the-ios-keyboard-in-xamarin-forms-numeric-controls)


