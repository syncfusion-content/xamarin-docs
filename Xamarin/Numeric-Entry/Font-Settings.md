---
layout: post
title: Font Settings in Syncfusion NumericTextBox control for Xamarin.Forms
description: This section explains how to set the Font style in Syncfusion NumericTextBox control for Xamarin.Forms.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Font Settings in Xamarin Numeric Entry (SfNumericTextBox)

NumericTextBox has the following two font-related properties that display the value's text:
We can customize the font style of NumericTextBox by using the following properties.

* `FontSize` : Sets the font size for NumericTextBox’s text. 

* `FontAttributes` : Sets the style of NumericTextBox’s text. We can give three types of style on it.It is specifying style information like Italic and Bold (using the FontAttributes enumeration in C#)

1. Bold- The font is bold
2. Italic – The font is Italic
3. None – The font is unmodified.

N> Default value is None.

* `FontFamily` : Customizes the font family of the NumericTextBox’s text.

* `TextAlignment` : Sets the style of NumericTextBox’s text. We can give three types of style on it.It is specifying style information like Start,End and Center (using the TextAlignment enumeration in C#)

N> Default value is Start.

To set the font size and attributes in XAML as well as in C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" FontSize="27" FontAttributes="Bold" Value="123" TextAlignment="End" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.FontSize = 27;
numericTextBox.Value = 123;
numericTextBox.TextAlignment=TextAlignment.End;
numericTextBox.FontAttributes = FontAttributes.Bold;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display SfNumericTextBox control with TextAlignment](images/textformatend.png)

## See also

[How to customize the font in SfNumericTextBox](https://www.syncfusion.com/kb/7585/how-to-custom-the-font-in-numerictextbox)

