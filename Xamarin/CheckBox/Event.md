---
layout: post
title: Event for Syncfusion.Xamarin.Forms SfCheckBox
description: How to get the notification of StateChanged event action in Syncfusion Xamarin.Forms CheckBox (SfCheckBox) control.
platform: Xamarin.Forms
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Event in Xamarin Checkbox (SfCheckbox)

## StateChanged event
Occurs when the value(state) of the [`IsChecked`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.ToggleButton~IsChecked.html) property is changed by either touching the check box or setting the value to the [`IsChecked`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.ToggleButton~IsChecked.html) property using XAML or C# code. The event arguments are of type [`StateChangedEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.StateChangedEventArgs.html) and expose the following property:

* [`IsChecked`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.ToggleButton~IsChecked.html): The new value(state) of the [`IsChecked`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.ToggleButton~IsChecked.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfCheckBox x:Name="checkBox" Text="Unchecked State" IsThreeState="True" StateChanged="CheckBox_StateChanged"/>

{% endhighlight %}
{% highlight c# %}

SfCheckBox checkBox = new SfCheckBox();
checkBox.Text = "Unchecked State";
checkBox.IsThreeState = true;
checkBox.StateChanged += CheckBox_StateChanged;
	
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (e.IsChecked.HasValue && e.IsChecked.Value)
    {
        checkBox.Text = "Checked State";
    }
    else if(e.IsChecked.HasValue && !e.IsChecked.Value)
    {
        checkBox.Text = "Unchecked State";
    }
    else
    {
    checkBox.Text = "Indeterminate State";
    }
}

{% endhighlight %}
{% endtabs %}

![Checked state image](Images/Event1.png)
![Unchecked state image](Images/Event2.png)
![Indeterminate state image ](Images/Event3.png)
