---
layout: post
title: SelectAllOnFocus in Syncfusion NumericTextBox for Xamarin.Forms
description: Learn how to set SelectAllOnFocus the  NumericTextBox
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Set SelectAllOnFocus

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



