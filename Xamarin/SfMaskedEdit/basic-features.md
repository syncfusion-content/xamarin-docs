---
layout: post
title: Basic features in SfMaskedEdit for Xamarin.Forms platform
description: Learn how to customize the basic features of SfMaskedEdit
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Basic Features

## Setting Value

The SfMaskedEdit control displays the value that can be set using the `Value` property:

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" Mask="00/00/0000" Value="14/11/2014"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.Value =@"14/11/2014";
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/BF_SetValue.png)


## Setting Prompt Character

Displays prompt character for the absence of your input in Mask and its default value is ‘_’. You can set the custom prompt character using `PromptChar` property.

{% tabs %}
{% highlight xaml %}
< syncmaskededit:SfMaskedEdit x:Name="maskedEdit" Mask="000000" MaskType="Text" PromptChar="*"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.PromptChar = '*';
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/BF_Prompt.png)

## Setting Watermark

The watermark will prompt you with instructions or important information when it is not on focus and any valid characters are not entered. The `Watermark` property of `SfMaskedEdit` is used to set the watermark text for the control.

The following properties are used to customize its appearance:

* `WatermarkColor`: Sets text color for the watermark.
* `WatermarkFontFamily`: Represents the font to be used in the watermark.
* `WatermarkFontAttributes`: Sets font attributes(bold/italic/none) for the watermark.
* `WatermarkFontSize`: Sets font size for the watermark.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" Mask="00/00/0000" Watermark="Type here" WatermarkColor="LightGray" WatermarkFontFamily="Arial" WatermarkFontAttributes="Bold" WatermarkFontSize="20"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
maskedEdit.Watermark = "Type here";
maskedEdit.WatermarkColor = Color.LightGray;
maskedEdit.WatermarkFontFamily = "Arial";
maskedEdit.WatermarkFontAttributes = FontAttributes.Bold;
maskedEdit.WatermarkFontSize = 20;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/BF_Hint.png)

You can find the complete basic features sample from this [link](http://files2.syncfusion.com/Xamarin.Forms/Samples/MaskedEdit_BasicFeatures.zip).
