---
layout: post
title: Input validation in Syncfusion MaskedEdit control for Xamarin.Forms
description: Learn how and when to validate the input characters with the given Mask of SfMaskedEdit control for Xamarin.Forms.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Validation in SfMaskedEdit

## Validation Mode

Input validation happens based on the value of the [`ValidationMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_ValidationMode) property. The enum values of this property are:

* KeyPress
* LostFocus

The default value for validation mode is `LostFocus`.

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" ValidationMode="KeyPress"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.ValidationMode = InputValidationMode.KeyPress;
{% endhighlight %}
{% endtabs %}

When the ValidationMode is LostFocus, the validation takes place when the control lost its focus. For KeyPress, the validation triggers for each key press.

## HasError

This read only property is used to check whether the validation succeeds or not. It returns true once validation succeeds or else returns false. The following code example shows the usage of [`HasError`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_HasError) property.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.ValidationMode = InputValidationMode.LostFocus;
maskedEdit.ValueChanged += MaskedEdit_ValueChanged;


private void MaskedEdit_ValueChanged(object sender, Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs e)
{
    SfMaskedEdit maskedEdit = sender as SfMaskedEdit;
    if(maskedEdit.HasError)
    {
        DisplayAlert("Alert", "Please enter valid details", "OK");
    }
}
{% endhighlight %}
{% endtabs %}


Refer this [link](events.html#valuechanged-event) to know more about the `ValueChanged` event of SfMaskedEdit control.

![ValidationMode support in Xamarin.Forms masked edit](SfMaskedEditImages/Validation.png)