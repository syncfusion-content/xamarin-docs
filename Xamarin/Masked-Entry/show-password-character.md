---
layout: post
title: Show Password Character in Xamarin Masked Entry control | Syncfusion<sup>®</sup>
description: Learn here all about Show Password Character support in Syncfusion<sup>®</sup> Xamarin Masked Entry (SfMaskedEdit) control and more.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Show Password Character in Xamarin Masked Entry (SfMaskedEdit)

The SfMaskedEdit control supports to work as a password text box when setting a character to the [`PasswordChar`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_PasswordChar) property.

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

![Show Password Char](SfMaskedEditImages/PasswordChar.png)

## Password Delay

When providing password character, you can show the typed character with some delay using the [`EnablePasswordDelay`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_EnablePasswordDelay) property. When enabling the EnablePasswordDelay property, the typed character will be displayed for a few seconds before it is converted to the password character.  

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

N> The default value of the EnablePasswordDelay property is false.

## Password Delay Duration

When “PasswordDelay” is enabled, you can handle the duration of the displaying typed character using the [`PasswordDelayDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_PasswordDelayDuration) property.   

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
