---
layout: post
title: Hiding Prompt Characters in Xamarin Masked Entry control | Syncfusion
description: Learn here all about Hiding Prompt Characters support in Syncfusion Xamarin Masked Entry (SfMaskedEdit) control and more.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Hiding Prompt Characters in Xamarin Masked Entry (SfMaskedEdit)

When the [`HidePromptOnLeave`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_HidePromptOnLeave) property is set to true, prompt characters are ignored when control loses focus. Again, the prompt characters are restored when the control is focused.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" HidePromptOnLeave="True" />
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.HidePromptOnLeave = true;
{% endhighlight %}
{% endtabs %}

![HidePromptOnLeave support in Xamarin.Forms masked edit](SfMaskedEditImages/HPL.png)
