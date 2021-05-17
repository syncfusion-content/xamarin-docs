---
layout: post
title: Using Mask Characters as Literals in Xamarin Masked Entry control | Syncfusion
description: Learn here all about Using Mask Characters as Literals support in Syncfusion Xamarin Masked Entry (SfMaskedEdit) control and more.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Using Mask Characters as Literals in Xamarin Masked Entry (SfMaskedEdit)

To use mask character as a literal, precede the mask character with a backslash (\\). For example, to display the dollar sign ($), then set the mask as follows:

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="\$ 0000"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = @"\$ 0000";
{% endhighlight %}
{% endtabs %}

This will produce a mask that displays a dollar sign ($) followed by the prompt characters for entering numbers.

![MaskAsLiterals support in Xamarin.Forms masked edit](SfMaskedEditImages/MaskAsLiterals.png)
