---
layout: post
title: Range Support in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to use range support for NumericTextBox control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Range Support

Restrict the Values within a specific range by setting the Maximum and Minimum property values.

{% tabs %}

{% highlight xaml %}

	   <syncfusion:SfNumericTextBox x:Name="numericTextBox" Maximum="1000" Minimum="50" Value="10"/>
	
{% endhighlight %}
	
{% highlight c# %}
	
        StackLayout stack = new StackLayout();
        SfNumericTextBox numericTextBox = new SfNumericTextBox();
        numericTextBox.Minimum = 50;
        numericTextBox.Maximum = 1000;
        numericTextBox.Value = 10;
        stack.Children.Add(numericTextBox);
        this.Content = stack;
			
{% endhighlight %}

{% endtabs %}

N> Default Value of `Maximum` and `Minimum` is "null".

![SfNumericTextBox RangeSupport](images/RangeSupport.gif)