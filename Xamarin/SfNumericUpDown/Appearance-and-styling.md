---
layout: post
title: Appearance and styling in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to add customize spin buttons position in NumericUpDown.
platform: xamarin
control: NumericUpDown
documentation: ug
---

# Appearance and Styling

## SpinButton Alignment

Spin Button position in the NumericUpDown control can be changed relative to the TextBox based on `SpinButtonAlignment` property. 

There are three built-in modes.

### Right

Spin Buttons will get aligned to the right side of the control.

{% highlight C# %}

	sfNumericUpDown.SpinButttonAlignment = SpinButtonAlignment.Right;

{% endhighlight %}

![](images/right.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% highlight C# %}

	sfNumericUpDown.SpinButttonAlignment = SpinButtonAlignment.Left;

{% endhighlight %}

![](images/left.png)

### Both

Spin Buttons will get aligned to the both side of the control.

{% highlight C# %}

	sfNumericUpDown.SpinButttonAlignment = SpinButtonAlignment.Both;

{% endhighlight %}

![](images/both.png)

N> By default the property value is Right.



