---
layout: post
title: Colors in Syncfusion NumericUpDown Control for Xamarin.Forms
description: Explore various color customization options available for the Syncfusion NumericUpDown control in Xamarin.Forms.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Colors in Xamarin NumericUpDown (SfNumericUpDown)

The [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) control allows customization of its background, text, and border colors using the following bindable properties:

- [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_TextColor): Sets the color of the NumericUpDown's value.

- `BackgroundColor`: Sets the background color of the NumericUpDown.

- [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_BorderColor): Sets the border color of the NumericUpDown control.

- [`WatermarkColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_WatermarkColor): Sets the color of the NumericUpDown's watermark text.

## Text Color Support in SfNumericUpDown

The following code samples demonstrate how to set the text color in XAML and C#:

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

## Background Color Support in SfNumericUpDown

The following code samples demonstrate how to set the background color in XAML and C#:

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

## Border Color Support in SfNumericUpDown

The following code samples demonstrate how to set the border color in XAML and C#:

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

## Watermark Color Support in SfNumericUpDown

The following code samples demonstrate how to set the watermark color in XAML and C#:

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

## See Also

[How to customize the color appearance of SfNumericUpDown](https://support.syncfusion.com/kb/article/10060/how-to-customize-the-color-appearance-of-numeric-entry-in-xamarinforms)
