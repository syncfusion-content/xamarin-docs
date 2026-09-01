---
layout: post
title: Events and Interactivity in Xamarin Numeric Entry Control | Syncfusion
description: Learn all about Events and Interactivity support in the Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Events in Xamarin Numeric Entry (SfNumericTextBox)

## ValueChanged Event in SfNumericTextBox

Perform operations while changing the value of the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) using the [`ValueChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ValueChanged) event. This event returns the changed value in the NumericTextBox.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Value</td>
<td>Displays the changed value in the NumericTextBox</td>
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

## Interactivity: ValueChangeMode in SfNumericTextBox

The [`ValueChangeMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ValueChangeMode) property is used to specify when the validation should occur: either on key press or on focus loss. When `ValueChangeMode` is set to [`OnKeyFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.ValueChangeMode.html#Syncfusion_SfNumericTextBox_XForms_ValueChangeMode_OnKeyFocus), validation occurs for each key press. When `ValueChangeMode` is [`OnLostFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.ValueChangeMode.html#Syncfusion_SfNumericTextBox_XForms_ValueChangeMode_OnLostFocus), validation occurs when the control loses focus. The `ValueChangeMode` options include:

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

## Completed Event in SfNumericTextBox

The [`Completed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Completed) event is raised when the user finalizes the text in the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) by pressing the return key on the keyboard.

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

## See Also

[How to change the SfNumericTextBox style using its visual states](https://support.syncfusion.com/kb/article/10286/how-to-change-the-xamarin-forms-numeric-textbox-style-using-its-visual-states)

[How to define and apply a common style for SfNumericTextBox](https://support.syncfusion.com/kb/article/10232/how-to-define-and-apply-a-common-style-for-sfnumerictextbox-in-xamarin-forms)
