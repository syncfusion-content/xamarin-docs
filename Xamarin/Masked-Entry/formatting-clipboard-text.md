---
layout: post
title: Formatting clipboard text in Syncfusion SfMaskedEit in Xamarin.Forms
description: Learn how to format the clipboard text during cut and copy operation in SfMaskedEdit control for Xamarin.Forms plarform
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Formatting clipboard text

SfMaskedEdit allows you to format the clipboard text in a mask scenario (when the Mask property is set). When you perform the cut or copy operation, the clipboard text will be formatted with your input characters and the literals defined in the mask. You can modify this and allow the clipboard to hold the characters with or without prompt and literals by setting the [`CutCopyMaskFormat`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_CutCopyMaskFormat) property of the control. The clipboard text is formatted by any one of the following formatting enum values:

* ExcludePromptAndLiterals
* IncludePrompt
* IncludeLiterals
* IncludePromptAndLiterals

## ExcludePromptAndLiterals

Clipboard text will contain only the typed characters, the prompt characters and literals are excluded.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" CutCopyMaskFormat ="ExcludePromptAndLiterals"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.ExcludePromptAndLiterals;
{% endhighlight %}
{% endtabs %}

## IncludePrompt

Clipboard text contains the typed characters and prompt characters, literals are excluded.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" CutCopyMaskFormat ="IncludePrompt"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludePrompt;
{% endhighlight %}
{% endtabs %}

## IncludeLiterals

Clipboard text contains the typed characters and literals, prompt characters are excluded.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" CutCopyMaskFormat ="IncludeLiterals"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludeLiterals;
{% endhighlight %}
{% endtabs %}

## IncludePromptAndLiterals

Clipboard text contains typed characters, prompt characters, and literals.

{% tabs %}
{% highlight xaml %}
 <syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" CutCopyMaskFormat ="IncludePromptAndLiterals"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.CutCopyMaskFormat = MaskFormat.IncludePromptAndLiterals;
{% endhighlight %}
{% endtabs %}
