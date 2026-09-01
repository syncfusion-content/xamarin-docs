---
layout: post
title: Font Settings in Syncfusion NumericUpDown Control for Xamarin.Forms
description: This section explains how to set the font style in Syncfusion NumericUpDown control for Xamarin.Forms.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Font Settings in Xamarin NumericUpDown (SfNumericUpDown)

You can customize the font style of the [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) using the following font-related properties that control the display of the value's text:

- [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_FontSize): Sets the font size for the NumericUpDown's text.

- [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_FontAttribute): Specifies the style of the NumericUpDown's text. Styles available include:
  1. Bold: Applies bold styling to the text.
  2. Italic: Applies italic styling to the text.
  3. None: Leaves the text style unchanged (default).

- [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_FontFamily): Customizes the font family of the NumericUpDown's text.

- [`TextAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_TextAlignment): Specifies the alignment of the NumericUpDown's text. Options include Start, End, and Center. The default is **Start**.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown FontSize="27"  FontAttribute="Bold" Value="123" TextAlignment="End" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.FontSize = 27;
NumericUpDown.Value = 123;
NumericUpDown.TextAlignment=TextAlignment.End;
NumericUpDown.FontAttribute = FontAttributes.Bold;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown control with Font Customization](images/textformatend.PNG)

## See Also

[How to Customize the Text in the SfNumericUpDown](https://support.syncfusion.com/kb/article/6894/how-to-customise-the-text-present-in-the-sfnumericupdown)
