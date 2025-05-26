---
layout: post
title: Event in Xamarin Radio Button Control | Syncfusion
description: Learn about event support in Syncfusion Xamarin Radio Button (SfRadioButton) control and more.
platform: Xamarin
control: SfRadioButton
documentation: ug 
keywords: button, SfRadioButton, RadioButton

---

# Event in Xamarin Radio Button (SfRadioButton)

## StateChanged Event

The `StateChanged` event occurs when the value (state) of the [`IsChecked`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_IsChecked) property changes. This change can occur either through user interaction with the radio button or by programmatically setting the value using XAML or C# code. The event arguments are of type [`StateChangedEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.StateChangedEventArgs.html) and expose the following property:

* [`IsChecked`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ToggleButton.html#Syncfusion_XForms_Buttons_ToggleButton_IsChecked): Represents the new value (state) of the `IsChecked` property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfRadioGroup x:Name="radioGroup">
<syncfusion:SfRadioButton x:Name="check" Text="Checked State" IsChecked="True" StateChanged="RadioButton_StateChanged"/>
<syncfusion:SfRadioButton x:Name="uncheck" Text="Unchecked  State" StateChanged="RadioButton_StateChanged"/>
</syncfusion:SfRadioGroup>

private void RadioButton_StateChanged(object sender, StateChangedEventArgs e)
 {
    if (e.IsChecked.HasValue && e.IsChecked.Value)
    {
        (sender as SfRadioButton).Text = "Checked State";
    }
    else if (e.IsChecked.HasValue && !e.IsChecked.Value)
    {
        (sender as SfRadioButton).Text = "Unchecked State";
    }
 }
{% endhighlight %}
{% highlight c# %}
SfRadioGroup radioGroup = new SfRadioGroup();
SfRadioButton check = new SfRadioButton();
check.Text = "Checked State";
check.IsChecked = true;
check.StateChanged += RadioButton_StateChanged;
SfRadioButton uncheck = new SfRadioButton();
uncheck.Text = "Unchecked State";
uncheck.StateChanged += RadioButton_StateChanged;
radioGroup.Children.Add(check);
radioGroup.Children.Add(uncheck);

private void RadioButton_StateChanged(object sender, StateChangedEventArgs e)
 {
    if (e.IsChecked.HasValue && e.IsChecked.Value)
    {
        (sender as SfRadioButton).Text = "Checked State";
    }
    else if (e.IsChecked.HasValue && !e.IsChecked.Value)
    {
        (sender as SfRadioButton).Text = "Unchecked State";
    }
 }
 
{% endhighlight %}
{% endtabs %}

![StateChanged event 1](Images/Event1.png)
![StateChanged event 2](Images/Event2.png)

This demo can be downloaded from this [link](https://www.syncfusion.com/downloads/support/directtrac/general/ze/RadioButton_Event1787482656).

## See Also

- [How to notify the selection changes in Xamarin.Forms radio button (SfRadioButton)](https://support.syncfusion.com/kb/article/9544/how-to-notify-the-selection-changes-in-xamarin-forms-radiobutton-sfradiobutton)
 
- [How to get the selected Xamarin.Forms radio button (SfRadioButton)](https://support.syncfusion.com/kb/article/9506/how-to-get-the-selected-xamarinforms-radio-button)
