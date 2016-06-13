---
layout: post
title: Localization in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to localize the NumericUpDown control
platform: Xamarin.Forms
control: NumericUpDown
documentation: ug
---
# Localization

## Culture

The NumericUpDown value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

N> Default `Culture` property value is en-US.

{% tabs %}

{% highlight C# %}

	numericUpDown.Culture = new System.Globalization.CultureInfo("hi-IN");
	
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Culture="hi-IN"/>
	
{% endhighlight %}

{% endtabs %}


![](images/Culture.png)




