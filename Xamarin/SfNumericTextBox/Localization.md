---
layout: post
title: Localization in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to localize the  NumericTextBox
platform: Xamarin.Forms
control: NumericTextBox
documentation: ug
---
# Localization

## Culture

The NumericTextBox value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

N> Default `Culture` property value is en-US.

{% highlight c# %}

	numericTextBox.Culture = new System.Globalization.CultureInfo("fr-FR");
	
{% endhighlight %}


![](images/Culture.png)

