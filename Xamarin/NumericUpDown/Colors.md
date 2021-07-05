---
layout: post
title: Colors in Syncfusion NumericUpDown control for Xamarin.Forms
description: This section explain, different color customization supports in Syncfusion NumericUpDown control for Xamarin.Forms.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Colors in Xamarin NumericUpDown (SfNumericUpDown)

[`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) is used to set custom background, text, and border colors through the following bindable properties:

* [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_TextColor) - Sets the color of NumericUpDown's value

* `BackgroundColor` - Sets the background color of NumericUpDown.

* [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_BorderColor) - Sets the border custom color of NumericUpDown

* [`WatermarkColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_WatermarkColor) - Sets the watermark custom color of NumericUpDown's watermark Text.

## Text color support in SfNumericUpDown

The following code sample demonstrates how to set the text color in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown Value="123" TextColor="Green" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.TextColor = Color.Green;
NumericUpDown.Value = 123;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with TextColor](images/TextColor.PNG)

## Background color support in SfNumericUpDown

The following code sample demonstrates how to set the background color in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown Value="123" BackgroundColor="Maroon" TextColor="White"/>
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.BackgroundColor = Color.Maroon;
NumericUpDown.TextColor = Color.White;
NumericUpDown.Value = 123;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with BackgroundColor](images/backgroundcolor.PNG)

## Border color support in SfNumericUpDown

The following code sample demonstrates how to set the border color color in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown Value="123" BorderColor="Red" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.BorderColor = Color.Red;
NumericUpDown.Value = 123;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with BorderColor](images/bordercolor.PNG)

## Watermark color support in SfNumericUpDown

The following code sample demonstrates how to set the watermark color in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown AllowNull="true" Watermark="NumericUpDown" WatermarkColor="Blue" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.WatermarkColor = Color.Blue;
NumericUpDown.Watermark = "NumericUpDown";
NumericUpDown.AllowNull = true;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with WatermarkColor](images/watermarkcolor.PNG)

## See also

[How to customize the color appearance of SfNumericUpDown](https://www.syncfusion.com/kb/11610/how-to-customize-the-color-appearance-of-numeric-controls-in-xamarin-forms)
