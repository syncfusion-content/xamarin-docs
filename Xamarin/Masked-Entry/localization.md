---
layout: post
title: Localization in Xamarin Masked Entry Control | Syncfusion
description: Learn about the localization support in the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Localization in Xamarin Masked Entry (SfMaskedEdit)

Special symbols, such as the currency symbol, date separator, and decimal separator, can be localized to any specific culture using the [`Culture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_Culture) property.

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

With the above settings, the currency symbol `$` will be localized to `€`, the decimal separator `.` will become `,`, and the group separator `,` will transform into a single whitespace ` `.
![Localization support in Xamarin.Forms masked edit](SfMaskedEditImages/Localization.png)
