---
layout: post
title: Localization in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to localize the NumericUpDown control
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Localization

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




