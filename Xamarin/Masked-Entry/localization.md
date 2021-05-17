---
layout: post
title: Localization in Xamarin Masked Entry control | Syncfusion
description: Learn here all about Localization support in Syncfusion Xamarin Masked Entry (SfMaskedEdit) control and more.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Localization in Xamarin Masked Entry (SfMaskedEdit)

The special symbols such as currency symbol, date separator, decimal separator etc., can be localized to any specific culture using the [`Culture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_Culture) property.

<table>
<tr>
<td>
{{'**Characters**'| markdownify }}
</td>
<td>
{{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
.
</td>
<td>
Decimal separator determined by current culture.
</td>
</tr>
<tr>
<td>
,
</td>
<td>
Group separator determined by current culture.
</td>
</tr>
<tr>
<td>
/
</td>
<td>
Date separator determined by current culture.
</td>
</tr>
<tr>
<td>
:
</td>
<td>
Time separator determined by current culture.
</td>
</tr>
<tr>
<td>
$
</td>
<td>
Currency symbol determined by current culture.
</td>
</tr>
</table>

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "$ 0,000.00";
maskedEdit.Culture = new CultureInfo("fr-FR");
{% endhighlight %}
{% endtabs %}

Now the ‘$’ will be localized to ‘€’;‘.’ will be localized to ‘,’ and ‘,’ will be localized to ‘ ‘(single white space).

![Localization support in Xamarin.Forms masked edit](SfMaskedEditImages/Localization.png)
