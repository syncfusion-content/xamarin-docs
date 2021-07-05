---
layout: post
title: Events and Interactivity in Xamarin Numeric Entry control | Syncfusion
description: Learn here all about Events and Interactivity support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Events in Xamarin Numeric Entry (SfNumericTextBox)

## ValueChanged event in SfNumericTextBox

We can perform operation while the changing the value of [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) value using [`ValueChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ValueChanged) event. ValueChanged event returns the changed value in NumericTextBox.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Displays changed value in NumericTextBox</td>
</tr>
</table>

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfNumericTextBox ValueChanged="Handle_ValueChanged" Value="123"  />
    
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123;
numericTextBox.ValueChanged += Handle_ValueChanged;
this.Content=numericTextBox;

void Handle_ValueChanged(object sender, Syncfusion.SfNumericTextBox.XForms.ValueEventArgs e)
{
    System.Diagnostics.Debug.WriteLine(e.Value.ToString());
}

{% endhighlight %}

{% endtabs %}

## Interactivity : ValueChangeMode in SfNumericTextBox

The [`ValueChangeMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ValueChangeMode) property is used to mention when the validation need to take place, either in key pressed or in focus lost. When ValueChangeMode is set to [`OnKeyFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.ValueChangeMode.html#Syncfusion_SfNumericTextBox_XForms_ValueChangeMode_OnKeyFocus), the validation will be carried out for each key press. When ValueChangeMode is [`OnLostFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.ValueChangeMode.html#Syncfusion_SfNumericTextBox_XForms_ValueChangeMode_OnLostFocus), the validation occur when the control lost the focus or the focus move to next control. ValueChangeMode includes the following options:

1. [`OnKeyFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.ValueChangeMode.html#Syncfusion_SfNumericTextBox_XForms_ValueChangeMode_OnKeyFocus)
2. [`OnLostFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.ValueChangeMode.html#Syncfusion_SfNumericTextBox_XForms_ValueChangeMode_OnLostFocus)

### OnKeyFocus in SfNumericTextBox

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox ValueChangeMode="OnKeyFocus" Value="123" ValueChanged="SfNumericTextBox_ValueChanged" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123;
numericTextBox.ValueChanged += NumericTextBox_ValueChanged;
numericTextBox.ValueChangeMode = ValueChangeMode.OnKeyFocus;
this.Content=numericTextBox;

private void SfNumericTextBox_ValueChanged(object sender, Syncfusion.SfNumericTextBox.XForms.ValueEventArgs e)
{
    DisplayAlert("OnKeyFocus", e.Value.ToString(), "OK");
}

{% endhighlight %}

{% endtabs %}

![Display SfNumericTextBox control with ValueChanged event OnKeyFocus](images/onkeyfocus.png)

### OnLostFocus in SfNumericTextBox

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox ValueChangeMode="OnLostFocus" Value="123"  ValueChanged="SfNumericTextBox_ValueChanged" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();
numericTextBox.Value = 123;
numericTextBox.ValueChanged += NumericTextBox_ValueChanged;
numericTextBox.ValueChangeMode = ValueChangeMode.OnLostFocus;
this.Content = numericTextBox;

private void SfNumericTextBox_ValueChanged(object sender, Syncfusion.SfNumericTextBox.XForms.ValueEventArgs e)
{
    DisplayAlert("OnLostFocus", e.Value.ToString(), "OK");
}

{% endhighlight %}

{% endtabs %}

![Display SfNumericTextBox control with ValueChanged event OnLostFocus](images/onlostfocus.png)

## Completed in SfNumericTextBox

Raised [`completed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Completed) event when the user finalizes the text in the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) by pressing return key on the keyboard.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfNumericTextBox Completed="Handle_Completed”/>
    
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Completed += Handle_Completed;
this.Content=numericTextBox;

void Handle_Completed(object sender, System.EventArgs e)
{
System.Diagnostics.Debug.WriteLine("Completed");      
}

{% endhighlight %}

{% endtabs %}

## See also

[How to change the SfNumericTextBox style using its visual states]( https://www.syncfusion.com/kb/11785/how-to-change-the-xamarin-forms-numeric-textbox-style-using-its-visual-states)

[How to define and apply a common style for SfNumericTextBox]( https://www.syncfusion.com/kb/11670/how-to-define-and-apply-a-common-style-for-sfnumerictextbox-in-xamarin-forms)
