---
layout: post
title: Formatting Clipboard Text in Xamarin Masked Entry Control | Syncfusion
description: Learn about formatting clipboard text in the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Formatting Clipboard Text in Xamarin Masked Entry (SfMaskedEdit)

`SfMaskedEdit` allows you to format the clipboard text in scenarios where the `Mask` property is set. During cut or copy operations, the clipboard text is formatted with your input characters and the literals defined in the mask. You can customize this behavior using the [`CutCopyMaskFormat`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_CutCopyMaskFormat) property. The clipboard text can be formatted using the following enumeration values:

- **ExcludePromptAndLiterals**
- **IncludePrompt**
- **IncludeLiterals**
- **IncludePromptAndLiterals**

## ExcludePromptAndLiterals

In this mode, the clipboard text will contain only the typed characters, excluding prompt characters and literals.

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

This setting makes the clipboard text include typed characters and prompt characters, but excludes literals.

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

With this option, the clipboard text will include typed characters and literals, excluding prompt characters.
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

This setting includes typed characters, prompt characters, and literals in the clipboard text.

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
