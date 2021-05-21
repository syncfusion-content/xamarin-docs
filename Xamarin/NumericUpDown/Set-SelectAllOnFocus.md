---
layout: post
title: Selection Support in Xamarin NumericUpDown control | Syncfusion
description: Learn here all about Selection Support in Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control and more.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Selection Support in Xamarin NumericUpDown (SfNumericUpDown)

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



