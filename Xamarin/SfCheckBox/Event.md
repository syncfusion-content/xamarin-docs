---
layout: post
title: Event in SfCheckBox for Xamarin.Forms platform
description: Learn how to customize the basic features of SfCheckBox
platform: Xamarin.Forms
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Event

## StateChanged event
Occurs when the value(state) of the `IsChecked` property is changed by either touching the check box or setting the value to the `IsChecked` property through XAML or C# code. The event arguments are of type `StateChangedEventArgs` and expose the following property:

* `IsChecked`: The new value(state) of the `IsChecked` property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfCheckBox x:Name="checkBox" Text="Unchecked State" IsThreeState="True" StateChanged="CheckBox_StateChanged"/>

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
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox();
checkBox.Text = "Unchecked State";
checkBox.IsThreeState = true;
checkBox.StateChanged += CheckBox_StateChanged;

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

![](Images/Event1.png)
![](Images/Event2.png)
![](Images/Event3.png)

This demo can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Event1605323609.zip).