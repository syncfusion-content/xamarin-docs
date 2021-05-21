---
layout: post
title: Selection Support in Xamarin Numeric Entry control | Syncfusion
description: Learn here all about Selection Support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Selection Support in Xamarin Numeric Entry (SfNumericTextBox)

`SelectAllOnFocus` the property is used to specify whether the text should be selected when the control gets focus.

{% tabs %}

{% highlight xaml %}

       <numeric:SfNumericTextBox SelectAllOnFocus="True" Value="12345"/>
	
{% endhighlight %}

{% highlight c# %}
 
SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value=12345;
numericTextBox.SelectAllOnFocus = true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display the value with selection mode](images/SelectAllOnFocus.png)



