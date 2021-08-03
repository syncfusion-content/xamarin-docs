---
layout: post
title: Font Settings in Xamarin Numeric Entry control | Syncfusion
description: Learn here all about Font Settings support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Font Settings in Xamarin Numeric Entry (SfNumericTextBox)

[`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) has the following two font-related properties that display the [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Value) text:

You can customize the font style of [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) by using the following properties.

* [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_FontSize) : Sets the font size for [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) text. 

* [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_FontAttributes) : Sets the style of [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) text. You can apply three types of style on it. It is specifying style information like Italic and Bold (using the FontAttributes enumeration in C#).

   1. Bold - The font is bold.
   2. Italic – The font is Italic.
   3. None – The font is unmodified.

N> Default value is None.

* [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_FontFamily) : Customizes the font family of the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) text.

* [`TextAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_TextAlignment) : Sets the style of [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) text. You can apply three types of style on it. It is specifying style information like Start, End, and Center (using the TextAlignment enumeration in C#).

N> Default value is [`Start`].

To set the font size and attributes in XAML as well as in C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox FontSize="27" FontAttributes="Bold" Value="123" TextAlignment="End" />
	
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

