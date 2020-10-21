---
layout: post
title: Colors in Syncfusion NumericUpDown control for Xamarin.Forms
description: This section explain, color customizationin properties in Syncfusion NumericUpDown control for Xamarin.Forms.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Colors in Xamarin NumericUpDown (SfNumericUpDown)

SfNumericUpDown is used to set custom background, text, and border colors through the following bindable properties:

* `TextColor` - Sets the color of NumericUpDown's value

* `BackgroundColor` - Sets the background color of NumericUpDown.

* `BorderColor` - Sets the border custom color of NumericUpDown

* `WatermarkColor` - Sets the watermark custom color of NumericUpDown's watermark Text.

### TextColor

The following code sample demonstrates how to set the TextColor in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="NumericUpDown" Value="123" TextColor="Green" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.TextColor = Color.Green;
NumericUpDown.Value = 123;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with TextColor](images/textcolor.png)

### BackgroundColor

The following code sample demonstrates how to set the BackgroundColor in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="NumericUpDown" Value="123" BackgroundColor="Maroon" TextColor="White"/>
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.BackgroundColor = Color.Maroon;
NumericUpDown.TextColor = Color.White;
NumericUpDown.Value = 123;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with BackgroundColor](images/backgroundcolor.png)

### BorderColor

The following code sample demonstrates how to set the BorderColor color in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="NumericUpDown" Value="123" BorderColor="Red" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.BorderColor = Color.Red;
NumericUpDown.Value = 123;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with BorderColor](images/bordercolor.png)

### WatermarkColor

The following code sample demonstrates how to set the WatermarkColor in XAML and in C#:

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown  x:Name="NumericUpDown" AllowNull="true" WatermarkColor="Blue" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.WatermarkColor = Color.Blue;
NumericUpDown.AllowNull=true;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown with WatermarkColor](images/watermarkcolor.png)

## See also

[How to customize the color appearance of SfNumericUpDown](https://www.syncfusion.com/kb/11610/how-to-customize-the-color-appearance-of-numeric-controls-in-xamarin-forms)
