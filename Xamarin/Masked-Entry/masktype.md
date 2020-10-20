---
layout: post
title: Mask Types of Syncfusion MaskedEdit control for Xamarin.Forms
description: Learn the different types of mask characters available in SfMaskedEdit control to restrict the user input
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# MaskType in SfMaskedEdit
Each [`MaskType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_MaskType) has different set of mask characters that are combined to form a mask expression. Based on the complexity and usage, mask types are classified as:

* Text
* RegEx

## Text

The expressions that are generated with letters, digits, and special characters come under this group. This is mainly used for fixed length inputs. For example: phone number, zip code, and so on.

### Text Mask characters

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

This mask expression allows only numeric inputs in the places of 0.

## Regex

The expressions that are generated with regular expressions come under this group, preferable for variable length inputs and input in range. For example: hexadecimal values [0-9A-C].
The regular expressions provide significant advantages when creating masks as compared with other mask modes. 

**Advantages**

* Allows you to enter the value of indeterminate length.
* Restricts with specific pattern. Example email, password, and more.
* Restricts you to enter specific range at specific position.

### Regex Mask Characters

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

N> SfMaskedEdit control only supports the above listed regex mask characters. 

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="RegEx" Mask="+1(\d{3})\d{5}"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.RegEx;
maskedEdit.Mask = @"+1(\d{3})\d{5}";
{% endhighlight %}
{% endtabs %}

This mask expression ’\d{3}’ and’ \d{5}’ allows only numeric, where {n} is the count that the input should be accepted.

![MaskType support in Xamarin.Forms masked edit](SfMaskedEditImages/MaskType.png)

## Troubleshooting

In case of having the requirement is to type the special characters such as _ and @, you can specify that directly in Mask as per your required order. 

If you use the mask with "_" then typed character _ (underscore) will not be accepted since the default value of the PromptChar is _ (underscore). Hence, it will be replaced by the character when you enter. To avoid this, you can set the PromptChar text other than _ (underscore) as shown below,

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

