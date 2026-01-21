---
layout: post
title: Visual Customization in Xamarin Masked Entry Control | Syncfusion
description: Learn about visual customization support in the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Visual Customization in Xamarin Masked Entry (SfMaskedEdit)

The appearance of the [`SfMaskedEdit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html) control can be customized using various properties.

## BorderColor

Customize the border color of the `SfMaskedEdit` by setting the [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_BorderColor) property.

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

![BorderColor customization in Xamarin.Forms masked edit](SfMaskedEditImages/Visual_BorderColor.png)

## ErrorBorderColor

Customize the error border color using the [`ErrorBorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_ErrorBorderColor) property. The error border color is used when validation fails based on the mask used.

> Validation occurs according to the `ValidationMode` property. See this [link](validation#validation-mode) for more on the `ValidationMode` property of the `SfMaskedEdit` control.
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

![ErrorBorderColor customization in Xamarin.Forms masked edit](SfMaskedEditImages/Visual_ErrorBorderColor.png)

 
## Setting Appearance of Text

Customizing the text appearance in the `SfMaskedEdit` control can be achieved using the following properties:

- [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_TextColor): Sets the color of the text.
- [`HorizontalTextAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_HorizontalTextAlignment): Sets the horizontal alignment of the text.
- [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_FontFamily): Sets the font family of the text.
- [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_FontAttributes): Sets font attributes (bold/italic/none).
- [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_FontSize): Sets the font size of the text.

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

![TextColor customization in Xamarin.Forms masked edit](SfMaskedEditImages/Visual_TextColor.png)
