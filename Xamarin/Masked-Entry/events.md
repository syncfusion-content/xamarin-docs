---
layout: post
title: Events in Xamarin Masked Entry Control | Syncfusion
description: Learn about the various events supported in the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---
# Events in Xamarin Masked Entry (SfMaskedEdit)
The `SfMaskedEdit` control provides the following events:

- **[`ValueChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_ValueChanged)**: Triggered when the value of the [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_Value) property changes.
- **[`MaskInputRejected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_MaskInputRejected)**: Triggered when a character is rejected by the input mask.

## ValueChanged Event

The `ValueChanged` event is triggered when the `Value` property changes due to input or code setting. The event arguments are of type [`ValueChangedEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs.html), which provide:

- **[`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs.html#Syncfusion_XForms_MaskedEdit_ValueChangedEventArgs_Value)**: A read-only property containing the updated value of `SfMaskedEdit`.

> Note: Input validation is determined by the `ValidationMode` property. See [Validation Mode](validation#validation-mode) for more information.
{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" Watermark="dd/MM/YYYY" ValidationMode="LostFocus" ValueChanged="MaskedEdit_OnValueChanged" />

private void MaskedEdit_OnValueChanged(object sender, Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs e)
{
    string date= e.Value.ToString();
    
    if (!string.IsNullOrEmpty(date))
    {
        try
        {
            DateTime datetime = DateTime.ParseExact(date,CultureInfo.CurrentCulture.DateTimeFormat.ShortDatePattern, CultureInfo.InvariantCulture);
        }
        catch (Exception exception)
        {
            DisplayAlert("Error", "Invalid Date format", "Ok");
        }
    }
}
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.Watermark = "dd/MM/YYYY";
maskedEdit.ValidationMode = InputValidationMode.LostFocus;
maskedEdit.ValueChanged += MaskedEdit_OnValueChanged;

private void MaskedEdit_OnValueChanged(object sender, Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs e)
{
    string date= e.Value.ToString();
    
    if (!string.IsNullOrEmpty(date))
    {
        try
        {
            DateTime datetime = DateTime.ParseExact(date,CultureInfo.CurrentCulture.DateTimeFormat.ShortDatePattern, CultureInfo.InvariantCulture);
        }
        catch (Exception exception)
        {
            DisplayAlert("Error", "Invalid Date format", "Ok");
        }
    }
}
{% endhighlight %}
{% endtabs %}

![ValueChanged event support in Xamarin.Forms masked edit](SfMaskedEditImages/ValueChangedevent.png)

## MaskInputRejected Event

The `MaskInputRejected` event occurs when an input character or operation does not match the input mask. The event arguments are of type [`MaskInputRejectedEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.MaskInputRejectedEventArgs.html), offering:

- **[`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.MaskInputRejectedEventArgs.html#Syncfusion_XForms_MaskedEdit_MaskInputRejectedEventArgs_Position)**: The position of the invalid input within the mask.
- **[`RejectionHint`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.MaskInputRejectedEventArgs.html#Syncfusion_XForms_MaskedEdit_MaskInputRejectedEventArgs_RejectionHint)**: An enumeration detailing why rejection occurred.

Common causes for this event include:

- Invalid character and format mismatch (e.g., entering a letter instead of a number).
- Attempting to enter characters beyond the mask's length.
- A paste operation introduces invalid characters.
{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" MaskType="Text" Mask="00/00/0000" Watermark="dd/MM/YYYY" ValidationMode="LostFocus" MaskInputRejected="MaskedEdit_OnMaskInputRejected"/>

private void MaskedEdit_OnMaskInputRejected(object sender, MaskInputRejectedEventArgs e)
{
    if(e.RejectionHint!= MaskedTextResultHint.UnavailableEditPosition)
        DisplayAlert("Error", "Please enter valid input", "Ok");
}

{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.Watermark = "dd/MM/YYYY";
maskedEdit.ValidationMode = InputValidationMode.LostFocus;
maskedEdit.MaskInputRejected += MaskedEdit_OnMaskInputRejected;

private void MaskedEdit_OnMaskInputRejected(object sender, MaskInputRejectedEventArgs e)
{
    if(e.RejectionHint!= MaskedTextResultHint.UnavailableEditPosition)
        DisplayAlert("Error", "Please enter valid input", "Ok");
}

{% endhighlight %}
{% endtabs %}

![MaskInputRejected event support in Xamarin.Forms masked edit](SfMaskedEditImages/MaskInputRejectedevent.png)

## Cursor Position Changing Event

Triggered when the cursor position in the entry changes.
The [`CursorPositionChanging`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_CursorPositionChanging) event provides:

- **[`NewValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.CursorPositionChangingEventArgs.html#Syncfusion_XForms_MaskedEdit_CursorPositionChangingEventArgs_NewValue)**: The new cursor index.
- **[`OldValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.CursorPositionChangingEventArgs.html#Syncfusion_XForms_MaskedEdit_CursorPositionChangingEventArgs_OldValue)**: The previous cursor index.
- **[`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.CursorPositionChangingEventArgs.html#Syncfusion_XForms_MaskedEdit_CursorPositionChangingEventArgs_Cancel)**: A boolean to restrict cursor movement.

{% tabs %}
{% highlight xaml %}

         <edit:SfMaskedEdit x:Name="maskedEdit" Mask="+1 000 000 0000"  
                  CursorPositionChanging="maskedEdit_CursorPositionChanging"/>

{% endhighlight %}
{% highlight c# %}

        SfMaskedEdit maskedEdit = new SfMaskedEdit();
        maskedEdit.Mask = "+1 000 000 0000";
        maskedEdit.CursorPositionChanging += maskedEdit_CursorPositionChanging;
        this.Content = maskedEdit;

        private void maskedEdit_CursorPositionChanging(object sender, Syncfusion.XForms.MaskedEdit.CursorPositionChangingEventArgs e)
        {
            if (e.NewValue <= 2)
                e.Cancel = true;
        }

{% endhighlight %}
{% endtabs %}

![Cursor position changing event support in Xamarin.Forms masked edit](SfMaskedEditImages/CursorPosition.png)
