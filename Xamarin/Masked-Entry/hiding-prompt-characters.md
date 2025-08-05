---
layout: post
title: Hiding Prompt Characters in Xamarin Masked Entry Control | Syncfusion
description: Learn about hiding prompt character support in the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Hiding Prompt Characters in Xamarin Masked Entry (SfMaskedEdit)

The [`HidePromptOnLeave`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_HidePromptOnLeave) property, when set to true, causes prompt characters to be hidden when the control loses focus. The prompt characters reappear when the control regains focus.

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
