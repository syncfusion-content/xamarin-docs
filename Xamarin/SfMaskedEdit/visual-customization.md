---
layout: post
title: Visual appearence customization of SfMaskedEdit control for Xamarin.Forms Platform
description: Learn how to customize the visual appearence of SfMaskedEdit control
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Visual Customization

The appearance of `SfMaskedEdit` can be customized using the following properties:

## BorderColor

Sets the custom border color to SfMaskedEdit.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" BorderColor="Green"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.BorderColor = Color.Green;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Visual_BorderColor.png)

## ErrorBorderColor

Sets the custom error border color to SfMaskedEdit. Error border color indicates the color to be used when the validation fails for your input with respect to the mask used. 

> Validation triggers based on `ValidationMode` property.
> Refer this [link](validation.html#validation-mode) to know more about the `ValidationMode` property of SfMaskedEdit control.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" BorderColor="Green" ErrorBorderColor="Yellow"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.ErrorBorderColor = Color.Yellow;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Visual_ErrorBorderColor.png)

 
## Setting Appearance of Text

You can customize the display text appearance of SfMaskedEdit control using the following properties:

* `TextColor`: Changes the color of the text.
* `HorizontalTextAlignment`: Changes the horizontal alignment of the text.
* `FontFamily`: Changes the font family of the text.
* `FontAttributes`: Sets font attributes(bold/italic/none) of the text.
* `FontSize`: Sets font size of the text.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" TextColor="Brown" HorizontalTextAlignment="Center" FontFamily="Arial" FontAttributes="Bold" FontSize="20"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.TextColor = Color.Brown;
maskedEdit.HorizontalTextAlignment = TextAlignment.Center;
maskedEdit.FontFamily = "Arial";
maskedEdit.FontAttributes = FontAttributes.Bold;
maskedEdit.FontSize = 20;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Visual_TextColor.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Forms/Samples/MaskedEdit_VisualCustomize.zip).
