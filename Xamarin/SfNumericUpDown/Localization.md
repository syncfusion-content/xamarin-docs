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

N> Default `Culture` property value is en-US.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Culture="hi-IN"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.Culture = new System.Globalization.CultureInfo("hi-IN");
	
{% endhighlight %}

{% endtabs %}

![](images/Culture.png)




