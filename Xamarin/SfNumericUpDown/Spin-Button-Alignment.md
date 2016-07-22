---
layout: post
title: Appearance and styling in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to add customize spin buttons position in NumericUpDown.
platform: Xamarin
control: NumericUpDown
documentation: ug
---

# Spin Button Alignment

Spin Button position in the NumericUpDown control can be changed relative to the TextBox based on `SpinButtonAlignment` property. 

There are three built-in modes.

### Right

Spin Buttons will get aligned to the right side of the control.

{% tabs %}

{% highlight C# %}

	numericUpDown.SpinButttonAlignment = SpinButtonAlignment.Right;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" SpinButtonAlignment="Right"/>
	
{% endhighlight %}

{% endtabs %}


![](images/right.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" SpinButtonAlignment="Left"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.SpinButttonAlignment = SpinButtonAlignment.Left;

{% endhighlight %}

{% endtabs %}


![](images/left.png)

### Both

Spin Buttons will get aligned to the both side of the control.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" SpinButtonAlignment="Both"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.SpinButttonAlignment = SpinButtonAlignment.Both;

{% endhighlight %}

{% endtabs %}


![](images/both.png)

N> By default the property value is Right.



