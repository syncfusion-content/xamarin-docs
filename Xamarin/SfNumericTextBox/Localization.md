---
layout: post
title: Localization in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to localize the  NumericTextBox
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Localization

The SfNumericTextBox value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

{% tabs %}

{% highlight c# %}
 
SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value=123.45;
numericTextBox.Culture = new System.Globalization.CultureInfo("fr-FR");
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![](images/Culture.png)

