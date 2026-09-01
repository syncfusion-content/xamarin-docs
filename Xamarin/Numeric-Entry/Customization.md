---
layout: post
title: Customization Options in Xamarin NumericTextBox Control | Syncfusion
description: Discover various customization options available in Syncfusion Xamarin NumericTextBox (SfNumericTextBox) control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Customization in Xamarin Numeric Entry (SfNumericTextBox)

## Assign Nullable Value in SfNumericTextBox

You can assign null values to the [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Value) property of `SfNumericTextBox` by setting the [`AllowNull`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_AllowNull) property to `true`.

> **Note:** By default, the `AllowNull` property is set to `false`.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox AllowNull="true" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();
numericTextBox.AllowNull=true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display nullable value image](images/AllowNull.png)

## Set Hint Text in SfNumericTextBox

The [`Watermark`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Watermark) property provides a helpful hint to users. The watermark text is displayed when the `Value` is empty or null.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox  AllowNull = "true"  Watermark="Enter value" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox  numericTextBox=new SfNumericTextBox();
numericTextBox.Watermark = "Enter value";
numericTextBox.AllowNull = true;
this.Content=numericTextBox;
	
{% endhighlight %}

{% endtabs %}

![Display watermark text image](images/WaterMark.png)

For customizing the color of the `SfNumericTextBox` [`Watermark`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Watermark), refer to this [link](https://help.syncfusion.com/xamarin/numeric-entry/colors).

## Parsing the Value in SfNumericTextBox

The value in `SfNumericTextBox` gets parsed based on the [`ParserMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ParserMode) property. You can choose between [`Double`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.Parsers.html#Syncfusion_SfNumericTextBox_XForms_Parsers_Double) and [`Decimal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.Parsers.html#Syncfusion_SfNumericTextBox_XForms_Parsers_Decimal) parsing modes.

The following code snippet demonstrates the Double parsing mode:
{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="123.45" ParserMode="Double" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.ParserMode=Parsers.Double;
numericTextBox.Value = 123.45;
this.Content = numericTextBox;
	
{% endhighlight %}

{% endtabs %}

> **Note:** The default value for [`ParserMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ParserMode) is [`Decimal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.Parsers.html#Syncfusion_SfNumericTextBox_XForms_Parsers_Decimal).

![Shows parser mode behavior](images/value.png)

## Range Support in SfNumericTextBox

Restrict values within a specific range by setting the [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Maximum) and [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Minimum) properties.

{% tabs %}

{% highlight xaml %}

	   <syncfusion:SfNumericTextBox Maximum="1000" Minimum="50" Value="10"/>
	
{% endhighlight %}
	
{% highlight c# %}
	
        SfNumericTextBox numericTextBox = new SfNumericTextBox();
        numericTextBox.Minimum = 50;
        numericTextBox.Maximum = 1000;
        numericTextBox.Value = 10;
        this.Content = numericTextBox;
			
{% endhighlight %}

{% endtabs %}

> **Note:** The default value for [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Maximum) and [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Minimum) is `null`.

![SfNumericTextBox Range Support](images/RangeSupport.gif)

## Set the Maximum Number of Decimal Digits in SfNumericTextBox

Specify the maximum number of decimal digits using the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_MaximumNumberDecimalDigits) property.

> **Note:** The `MaximumNumberDecimalDigits` property must be a positive value.
{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="123.459" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123.459;
numericTextBox.MaximumNumberDecimalDigits=2;
this.Content = numericTextBox;
  
{% endhighlight %}

{% endtabs %}

![Display the textbox value](images/MaximumNumberDecimalDigits.png)

## Remove Default Decimal Digits in SfNumericTextBox

Based on the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_MaximumNumberDecimalDigits) property, the default number of decimal digits is displayed. Disable the [`AllowDefaultDecimalDigits`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_AllowDefaultDecimalDigits) property to remove default digits from the numeric entry view.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123" AllowDefaultDecimalDigits="False" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% highlight c# %}

            SfNumericTextBox numericTextBox = new SfNumericTextBox();
            numericTextBox.Value = 123;
            numericTextBox.MaximumNumberDecimalDigits = 2;
            numericTextBox.AllowDefaultDecimalDigits = false;
            this.Content = numericTextBox;
  
{% endhighlight %}

{% endtabs %}

![Display the textbox value without default decimal digits](images/AllowDefaultDecimalDigits.png)

## Selection Support in SfNumericTextBox

The [`SelectAllOnFocus`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_SelectAllOnFocus) property specifies whether the text should be selected when the control gets focus.

{% tabs %}

{% highlight xaml %}

       <numeric:SfNumericTextBox SelectAllOnFocus="True" Value="12345"/>
	
{% endhighlight %}

{% highlight c# %}
 
SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value=12345;
numericTextBox.SelectAllOnFocus = true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display the value with selection mode](images/SelectAllOnFocus.PNG)

## See Also

- [How to set the MaximumDecimalDigits in SfNumericTextBox](https://support.syncfusion.com/kb/article/6839/how-to-set-the-maximumdecimaldigits-in-numerictextbox)
- [How to have null values in SfNumericTextBox](https://support.syncfusion.com/kb/article/6838/how-to-have-null-values-in-numerictextbox)
- [How to provide null value to SfNumericTextBox](https://support.syncfusion.com/kb/article/6306/how-to-provide-null-value-to-numerictextbox)
- [How to change the SfNumericTextBox style using its visual states](https://support.syncfusion.com/kb/article/10286/how-to-change-the-xamarin-forms-numeric-textbox-style-using-its-visual-states)
- [How to define and apply a common style for SfNumericTextBox](https://support.syncfusion.com/kb/article/10232/how-to-define-and-apply-a-common-style-for-sfnumerictextbox-in-xamarin-forms)
