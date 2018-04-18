---
layout: post
title: Localization with Syncfusion SfMaskedEdit control for Xamarin.Forms platform
description: Learn how to localize the special symbols such as currency symbol, date separator, decimal separator etc., in SfMaskedEdit control for Xamarin.Forms platform
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Localization

The special symbols such as currency symbol, date separator, decimal separator etc., can be localized to any specific culture using the `Culture` property.

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

![](SfMaskedEditImages/Localization.png)

You can find the runnable localization sample from this [link](http://files2.syncfusion.com/Xamarin.Forms/Samples/MaskedEdit_Localization.zip).
