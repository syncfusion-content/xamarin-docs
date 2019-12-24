---
layout: post
title: Mask Characters as Literals in Syncfusion MaskedEdit for Xamarin.Forms
description: Learn how to use the mask characters as literals in Syncfusion MaskedEdit control for Xamarin.Forms platform
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Using Mask Characters as Literals

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