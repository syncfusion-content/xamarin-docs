---
layout: post
title: SelectAllOnFocus in Syncfusion NumericUpDown for Xamarin.Forms
description: Learn how to set SelectAllOnFocus the  NumericUpDown
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Set SelectAllOnFocus

The `SelectAllOnFocus` property is used to specify whether the text should be selected when the control gets the focus.

{% tabs %}

{% highlight xaml %}

       <numeric:SfNumericUpDown SelectAllOnFocus="True" Value="12345"/>
	
{% endhighlight %}

{% highlight c# %}
 
SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.Value=12345;
NumericUpDown.SelectAllOnFocus = true;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the SfNumericUpDown control with Selection](images/SelectAllOnFocus.png)



