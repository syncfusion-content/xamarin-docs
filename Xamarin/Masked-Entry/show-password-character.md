---
layout: post
title: Show Password Character in Xamarin Masked Entry Control | Syncfusion
description: Learn about the support for displaying password characters in the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Show Password Character in Xamarin Masked Entry (SfMaskedEdit)

The `SfMaskedEdit` control can function as a password text box by setting a character for the [`PasswordChar`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_PasswordChar) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfMaskedEdit x:Name="maskedEdit" Mask="\w+" MaskType="RegEx" PasswordChar="*"  />
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = @"\w+";
maskedEdit.MaskType = MaskType.RegEx;
maskedEdit.PasswordChar = '*';
{% endhighlight %}
{% endtabs %}

![Show Password Character](SfMaskedEditImages/PasswordChar.png)

## Password Delay

While using a password character, you can display the typed character briefly by enabling the [`EnablePasswordDelay`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_EnablePasswordDelay) property. Once enabled, the typed character will appear for a few seconds before converting to the password character.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfMaskedEdit x:Name="maskedEdit" PasswordChar="*" EnablePasswordDelay="True" />
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.PasswordChar = '*';
maskedEdit.EnablePasswordDelay = true;
{% endhighlight %}
{% endtabs %}

![Delay password character](SfMaskedEditImages/Passworddelayfeature.gif)

> **Note:** The default value for the `EnablePasswordDelay` property is `false`.

## Password Delay Duration

When "PasswordDelay" is enabled, you can control the duration that the typed character is visible by using the [`PasswordDelayDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_PasswordDelayDuration) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfMaskedEdit x:Name="maskedEdit" Mask="\w+" MaskType="RegEx" PasswordChar="*" EnablePasswordDelay="True" PasswordDelayDuration="2" />
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = @"\w+";
maskedEdit.MaskType = MaskType.RegEx;
maskedEdit.PasswordChar = '*';
maskedEdit.EnablePasswordDelay = true;
maskedEdit.PasswordDelayDuration = 2;
{% endhighlight %}
{% endtabs %}
