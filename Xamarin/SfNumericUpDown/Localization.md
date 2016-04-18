---
layout: post
title: Localization in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to localize the NumericUpDown control
platform: xamarin
control: NumericUpDown
documentation: ug
---
# Localization

## Culture

The NumericUpDown value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

N> Default `Culture` property value is en-US.

{% highlight C# %}

	sfNumericUpDown.Culture = new System.Globalization.CultureInfo("en-US");
	
{% endhighlight %}

![](images/Culture.png)




