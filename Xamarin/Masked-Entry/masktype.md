---
layout: post
title: MaskType in Xamarin Masked Entry Control | Syncfusion
description: Learn about MaskType support in the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# MaskType in Xamarin Masked Entry (SfMaskedEdit)
Each [`MaskType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_MaskType) has a different set of mask characters combined to form a mask expression. Based on complexity and usage, mask types are categorized into:

- **Text**
- **RegEx**
## Text

Expressions generated using letters, digits, and special characters fall under this category. It is mainly used for fixed-length inputs, such as phone numbers and zip codes.
### Text Mask Characters

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
A
</td>
<td>
Alphanumeric, required.
</td>
</tr>
<tr>
<td>
a
</td>
<td>
Alphanumeric, optional.
</td>
</tr>
<tr>
<td>
L
</td>
<td>
Letter, required. Restricts input to the ASCII letters a-z and A-Z. 
</td>
</tr>
<tr>
<td>
l
</td>
<td>
Letter, optional. Restricts input to the ASCII letters a-z and A-Z. 
</td>
</tr>
<tr>
<td>
0
</td>
<td>
Digit, required. This character accepts any single digit between 0 and 9
</td>
</tr>
<tr>
<td>
9
</td>
<td>
Digit or space, optional. 
</td>
</tr>
<tr>
<td>
#
</td>
<td>
Digit or space, optional. Plus (+) and minus (-) signs are allowed.  
</td>
</tr>
<tr>
<td>
C
</td>
<td>
Character, optional. 
</td>
</tr>
<tr>
<td>
\
</td>
<td>
Escapes a mask character, turning it into a literal. "\" is the escape sequence for a backslash. 
</td>
</tr>
<tr>
<td>
Any other characters
</td>
<td>
Considered as literals. Literals always occupy a static position in the mask at run time, and cannot be moved or deleted. 
</td>
</tr>
</table>

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="+1(000)000000"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "+1(000)000000";
{% endhighlight %}
{% endtabs %}

This mask expression allows only numeric inputs in the positions marked by zero (0).

## RegEx

Expressions generated using regular expressions belong to this category, suitable for variable-length inputs and inputs within a range. Examples include hexadecimal values like [0-9A-C]. Regular expressions provide significant advantages over other mask modes by:

- Allowing inputs of indeterminate length.
- Restricting inputs to specific patterns, such as email addresses and passwords.
- Restricting inputs to specified ranges at specific positions.

### RegEx Mask Characters
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
\w
</td>
<td>
Accepts any alphabet, number, including the _(Underscore) character.
</td>
</tr>
<tr>
<td>
\d
</td>
<td>
Accepts any digit.
</td>
</tr>
<tr>
<td>
{n}
</td>
<td>
Accepts the input for ‘n’ number of times.
</td>
</tr>
<tr>
<td>
{n,m}
</td>
<td>
Accepts the input for ‘n’ minimum number of times and ‘m’ maximum number of times.
</td>
</tr>
<tr>
<td>
?
</td>
<td>
Optional input.
</td>
</tr>
<tr>
<td>
+
</td>
<td>
Accepts the input for one or more times.
</td>
</tr>
<tr>
<td>
*
</td>
<td>
Accepts the input for zero or more times.
</td>
</tr>
<tr>
<td>
[aeiou]
</td>
<td>
Accepts any single character included in the specified set of characters.
</td>
</tr>
<tr>
<td>
[0-9a-fA-F]
</td>
<td>
Accepts any character between[A-F]/[a-f] and numbers between [0-9].
</td>
</tr>
</table>

> **Note:** The `SfMaskedEdit` control only supports the regex mask characters listed above.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="RegEx" Mask="+1\(\d{3}\)\d{5}"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.RegEx;
maskedEdit.Mask = @"+1\(\d{3}\)\d{5}";
{% endhighlight %}
{% endtabs %}

This mask expression `\d{3}` and `\d{5}` allows numeric input, where `{n}` represents the count of accepted inputs.

![MaskType support in Xamarin.Forms masked edit](SfMaskedEditImages/MaskType.png)

## Troubleshooting

If you need to type special characters like _ and @, you can specify them directly in the mask as required.

When using a mask with the "_" character, the typed "_" (underscore) will not be accepted since the default `PromptChar` is "_". It will be replaced upon entry. To avoid this, set the `PromptChar` to a character other than "_", as shown below:

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="RegEx" Mask="[a-z0-9A-Z@_#*()-/$]*" PromptChar="*"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.RegEx;
maskedEdit.Mask = @"[a-z0-9A-Z@_#*()-/$]*";
maskedEdit.PromptChar = '*';
{% endhighlight %}
{% endtabs %}

