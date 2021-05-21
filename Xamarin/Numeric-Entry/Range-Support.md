---
layout: post
title: Range Support in Xamarin Numeric Entry control | Syncfusion
description: Learn here all about Range Support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Range Support in Xamarin Numeric Entry (SfNumericTextBox)

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
