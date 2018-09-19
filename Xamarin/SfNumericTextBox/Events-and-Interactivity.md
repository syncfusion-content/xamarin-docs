---
layout: post
title: Events and Interactivity in Syncfusion NumericTextBox control for Xamarin.Forms
description: Learn how to get the value changed event and some interactivity in  NumericTextBox
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Events and Interactivity

## Events

### ValueChanged Event

We can perform operation while the changing the value of NumericTextBox's Value using ValueChanged event. ValueChanged event returns the changed value in NumericTextBox.

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

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" ValueChanged="Handle_ValueChanged" Value="123"  />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123;
numericTextBox.ValueChanged += (object sender, ValueEventArgs e) =>
{
	System.Diagnostics.Debug.WriteLine(e.Value.ToString());
};
this.Content=numericTextBox;

{% endhighlight %}

{% endtabs %}

### Completed Event

Occurs when the user finalizes the text in the NumericTextBox by pressing return key on the keyboard.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfNumericTextBox x:Name="numericTextBox" Completed="Handle_Completed” Value="123"/>
    
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123;
numericTextBox.Completed += (object sender, EventArgs e) =>
{
    System.Diagnostics.Debug.WriteLine(“Completed”);
};
this.Content=numericTextBox;

{% endhighlight %}

{% endtabs %}

## Interactivity : ValueChangeMode

The ValueChangeMode property is used to mention when the validation need to take place, either in key pressed or in focus lost. When ValueChangeMode is set to OnKeyFocus, the validation will be carried out for each key press. When ValueChangeMode is OnLostFocus, the validation occur when the control lost the focus or the focus move to next control. ValueChangeMode includes the following options:

1. OnKeyFocus
2. OnLostFocus

### OnKeyFocus

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox ValueChangeMode="OnKeyFocus" x:Name="numericTextBox"  Value="123"  />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123;
numericTextBox.ValueChangeMode = ValueChangeMode.OnKeyFocus;
this.Content=numericTextBox;

{% endhighlight %}

{% endtabs %}

![](images/onkeyfocus.png)

### OnLostFocus

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox ValueChangeMode="OnLostFocus" x:Name="numericTextBox"  Value="123"  />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123;
numericTextBox.ValueChangeMode = ValueChangeMode.OnLostFocus;
this.Content=numericTextBox;

{% endhighlight %}

{% endtabs %}

![](images/onlostfocus.png)
