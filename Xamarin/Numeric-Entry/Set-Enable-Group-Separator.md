---
layout: post
title: EnableGroupSeparator in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to set EnableGroupSeparator the  NumericTextBox
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Set EnableGroupSeparator 

`EnableGroupSeparator` property is used to get rid of the comma in the Value of SfNumericTextBox.

{% tabs %}

{% highlight c# %}
 
SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value=12345;
numericTextBox.EnableGroupSeparator = true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![](images/Culture.png)

