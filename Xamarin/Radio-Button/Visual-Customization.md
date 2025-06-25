---
layout: post
title: Visual Customization in Xamarin Radio Button Control | Syncfusion
description: Learn about visual customization support in Syncfusion Xamarin Radio Button (SfRadioButton) control and more.
platform: Xamarin
control: SfRadioButton
documentation: ug 
keywords: button, SfRadioButton, RadioButton

---


# Visual Customization in Xamarin Radio Button (SfRadioButton)

## Customizing the State Color
The default state colors can be customized using the [`CheckedColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_CheckedColor) and [`UncheckedColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_UncheckedColor) properties. The checked state color is updated to the `CheckedColor` property value when the state changes to checked. The unchecked state color is updated to the `UncheckedColor` property value when the state changes to unchecked.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfRadioGroup x:Name="radioGroup">
<syncfusion:SfRadioButton x:Name="check" Text="RadioButton" IsChecked="True" CheckedColor="Green"/>
<syncfusion:SfRadioButton x:Name="uncheck" Text="RadioButton" UncheckedColor="Violet"/>
</syncfusion:SfRadioGroup>
{% endhighlight %}
{% highlight c# %}
SfRadioGroup radioGroup = new SfRadioGroup();
SfRadioButton check = new SfRadioButton();
check.Text = "RadioButton";
check.IsChecked = true;
check.CheckedColor = Color.Green;
SfRadioButton uncheck = new SfRadioButton();
uncheck.Text = "RadioButton";
uncheck.UncheckedColor = Color.Violet;
radioGroup.Children.Add(check);
radioGroup.Children.Add(uncheck);
{% endhighlight %}
{% endtabs %}

![CheckedColor and UncheckedColor in RadioButton](Images/StateColor.png)

## BorderWidth
The border thickness of the circle in the RadioButton control can be customized using the [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_BorderWidth) property.  

{% tabs %}
{% highlight xaml %}
<syncfusion:SfRadioGroup >
<syncfusion:SfRadioButton Text="Checked State" IsChecked="True" BorderWidth="3"/>
<syncfusion:SfRadioButton Text="UnChecked State" BorderWidth="3"/>
</syncfusion:SfRadioGroup>
{% endhighlight %}
{% highlight c# %}
SfRadioGroup radioGroup = new SfRadioGroup();
SfRadioButton check = new SfRadioButton();
check.Text = "Checked State";
check.IsChecked = true;
check.BorderWidth = 3;
SfRadioButton uncheck = new SfRadioButton();
uncheck.Text = "UnChecked State";
uncheck.BorderWidth = 3;
radioGroup.Children.Add(check);
radioGroup.Children.Add(uncheck);
{% endhighlight %}
{% endtabs %}

![RadioButton BorderWidth](Images/BorderWidth.png)

> **Note:** BorderWidth support is not provided for the Android platform.

## Setting Caption Text Appearance

You can customize the display text appearance of the [`SfRadioButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioButton.html) control using the following properties:

* [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_TextColor): Changes the color of the text.
* [`HorizontalTextAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_HorizontalTextAlignment): Changes the horizontal alignment of the caption text.
* [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_FontFamily): Changes the font family of the caption text.
* [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_FontAttributes): Sets font attributes (bold/italic/none) of the caption text.
* [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_FontSize): Sets the font size of the caption text.


{% tabs %}
{% highlight xaml %}
<syncfusion:SfRadioButton x:Name="radioButton" Text="RadioButton" IsChecked="True" TextColor="Violet" HorizontalTextAlignment="Center" FontFamily="Arial" FontAttributes="Bold" FontSize="20"/>
{% endhighlight %}
{% highlight c# %}
SfRadioButton radioButton = new SfRadioButton();
radioButton.Text = "RadioButton";
radioButton.IsChecked = true;
radioButton.TextColor = Color.Violet;
radioButton.HorizontalTextAlignment = TextAlignment.Center;
radioButton.FontFamily = "Arial";
radioButton.FontAttributes = FontAttributes.Bold;
radioButton.FontSize = 20;
{% endhighlight %}
{% endtabs %}

![RadioButton TextAppereance](Images/CaptionAppereance.png)

## LineBreakMode
The [`LineBreakMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_LineBreakMode) property allows you to wrap or truncate the text. The default value is [`NoWrap`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.LineBreakMode.html#Syncfusion_XForms_Buttons_LineBreakMode_NoWrap). Other available options include:

* [`NoWrap`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.LineBreakMode.html#Syncfusion_XForms_Buttons_LineBreakMode_NoWrap): Avoids text wrapping.
* [`WordWrap`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.LineBreakMode.html#Syncfusion_XForms_Buttons_LineBreakMode_WordWrap): Wraps text by words.
* [`CharacterWrap`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.LineBreakMode.html#Syncfusion_XForms_Buttons_LineBreakMode_CharacterWrap): Wraps text by character.
* [`HeadTruncation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.LineBreakMode.html#Syncfusion_XForms_Buttons_LineBreakMode_HeadTruncation): Truncates text at the start.
* [`MiddleTruncation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.LineBreakMode.html#Syncfusion_XForms_Buttons_LineBreakMode_MiddleTruncation): Truncates text at the center.
* [`TailTruncation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.LineBreakMode.html#Syncfusion_XForms_Buttons_LineBreakMode_TailTruncation): Truncates text at the end.

This demo can be downloaded from this [link](https://www.syncfusion.[REDACTED]RadioButton_VisualCustomization1644131704).

## Size Customization

The [`ControlSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_ControlSize) property is used to customize the size of the [`RadioButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioButton.html) control.

{% tabs %}
{% highlight xaml %}
<StackLayout>
    <syncfusion:SfRadioButton Text="RadioButton" ControlSize="60"/>
</StackLayout>
{% endhighlight %}
{% highlight c# %}
StackLayout stackLayout = new StackLayout();
SfRadioButton radioButton = new SfRadioButton();
radioButton.Text = "Radio Button";
radioButton.ControlSize = 60;
stackLayout.Children.Add(radioButton);
{% endhighlight %}
{% endtabs %}

> **Note:** [`ControlSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_ControlSize) is not applicable on the Android platform.

## See Also

- [How to wrap text in Xamarin.Forms radio button (SfRadioButton)](https://support.syncfusion.com/kb/article/10289/how-to-wrap-text-in-xamarin-forms-radiobutton)
