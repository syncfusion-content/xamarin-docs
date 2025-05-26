---
layout: post
title: Customization Options in Xamarin NumericUpDown Control | Syncfusion
description: Explore the various customization options available in the Syncfusion Xamarin NumericUpDown (SfNumericUpDown) control.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Customization in Xamarin NumericUpDown (SfNumericUpDown)

## Parsing Mode in SfNumericUpDown

The value of [`SfNumericUpDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html) is determined by the [`ParsingMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_ParsingMode) property. This enum property supports [`Double`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.ParsingMode.html#Syncfusion_SfNumericUpDown_XForms_ParsingMode_Double) and [`Decimal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.ParsingMode.html#Syncfusion_SfNumericUpDown_XForms_ParsingMode_Decimal) values, allowing value updates in either format.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown Value="123.45" ParsingMode="Decimal" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.ParsingMode=ParsingMode.Decimal;
NumericUpDown.Value = 123.45;
this.Content = NumericUpDown;
	
{% endhighlight %}

{% endtabs %}

N> The default value of ParsingMode is Double.

![ParsingMode](images/value.PNG)

## Maximum Decimal Digits in SfNumericUpDown

Specify the maximum number of digits after the decimal point using the [`MaximumDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_MaximumDecimalDigits) property.

N> The [`MaximumDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_MaximumDecimalDigits) property is provided with positive value only. By default, the value of this property is 2.

{% tabs %}

{% highlight xaml %}

<numeric:SfNumericUpDown Value="3.234" MaximumDecimalDigits ="3"/>
		
{% endhighlight %}


{% highlight C# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.Value = 3.234;
NumericUpDown.MaximumDecimalDigits = 3;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the SfNumericUpDown control with MaximumDecimalDigits](images/MaximumDecimalDigits.PNG)

## Nullable Values in SfNumericUpDown

Assign null values to the [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Value) property by setting the [`AllowNull`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_AllowNull) property to true.

N> By default, the property value is false.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown  AllowNull="true"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.AllowNull = true;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![AllowNull](images/AllowNull.png)

## Hint Text in SfNumericUpDown

Use the [`Watermark`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Watermark) property to provide a hint for the user input. The watermark text is visible when the value is empty or null.

{% tabs %}

{% highlight xaml %}

<numeric:SfNumericUpDown AllowNull="True" Watermark="NumericUpDown"/>	

{% endhighlight %}

{% highlight C# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.AllowNull = true;
NumericUpDown.Watermark = "NumericUpDown";
this.Content = NumericUpDown;
	
{% endhighlight %}

{% endtabs %}

![Watermark](images/Watermark.png)

## Auto Reverse in SfNumericUpDown

With `AutoReverse`, the control iterates from the [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Minimum) to the [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Maximum) value, and vice-versa.

N> By default the property value is false.

{% tabs %}

{% highlight xaml %}

<numeric:SfNumericUpDown AutoReverse="true" Minimum="0" Maximum="20"/>
		
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown NumericUpDown = new SfNumericUpDown();
NumericUpDown.AutoReverse = true;
NumericUpDown.Minimum =0;
NumericUpDown.Maximum = 20;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![NumericUpDown AutoReverse](images/AutoReverse.gif)

## Value Range Restriction in SfNumericUpDown
Restrict values within a specific range using the [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_Maximum) properties.

{% tabs %}

{% highlight xaml %}

<StackLayout HorizontalOptions="Center" VerticalOptions="Center">
    <Label Text="Minimum numbers of Adult"/>
    <updown:SfNumericUpDown  Minimum="10" Maximum="100"/>
    
    <Label Text="Maximum numbers of Adult" />
    <updown:SfNumericUpDown Value="100" Minimum="10" Maximum="100"/>
</StackLayout>
	
{% endhighlight %}

{% highlight C# %}

StackLayout stack = new StackLayout();
Label label1 = new Label();
label1.Text = "Minimum numbers of Adult";
SfNumericUpDown updown1 = new SfNumericUpDown();
updown1.Minimum = 10;
updown1.Maximum = 100;

Label label2 = new Label();
label2.Text = "Minimum numbers of Adult";
SfNumericUpDown updown2 = new SfNumericUpDown();
updown2.Minimum = 10;
updown2.Maximum = 100;
updown2.Value = 100;

stack.Children.Add(label1);
stack.Children.Add(updown1);
stack.Children.Add(label2);
stack.Children.Add(updown2);
this.Content = stack;

{% endhighlight %}

{% endtabs %}

![Display the value with maximum and minimum](images/minimum_maximum.png)

## Step Value in SfNumericUpDown

Set the frequency of value increments and decrements using the [`StepValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_StepValue) property.

N> By default the property value is 1.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown StepValue="6"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.StepValue = 6;
this.Content = numericUpDown;

{% endhighlight %}

{% endtabs %}

![NumericUpDown StepValue](images/StepValue.gif)

## Editing Options in SfNumericUpDown

The [`IsEditable`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_IsEditable) property determines if users can edit the input field.

N> By default, the value of [`IsEditable`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_IsEditable) property is true.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown Value="123"  IsEditable="True"/>
	
{% endhighlight %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.IsEditable = true;
this.Content = numericUpDown;

{% endhighlight %}

{% endtabs %}

![Allow editing to the SfNumericUpDown control](images/IsEditableMode.PNG)

## Selection Options in SfNumericUpDown

The [`SelectAllOnFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown.html#Syncfusion_SfNumericUpDown_XForms_SfNumericUpDown_SelectAllOnFocus) property defines whether the text is selected when the control gets focus.

{% tabs %}

{% highlight xaml %}

       <numeric:SfNumericUpDown SelectAllOnFocus="True" Value="12345"/>
	
{% endhighlight %}

{% highlight c# %}
 
SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.Value=12345;
NumericUpDown.SelectAllOnFocus = true;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the SfNumericUpDown control with Selection](images/SelectAllOnFocus.PNG)

## See Also

[Restricting SfNumericUpDown Values within a Range](https://support.syncfusion.com/kb/article/6983/how-to-restrict-the-values-of-sfnumericupdown-within-certain-range)

[Setting AutoReverse Property in SfNumericUpDown](https://support.syncfusion.com/kb/article/6985/how-to-set-autoreverse-property-in-sfnumericupdown)
