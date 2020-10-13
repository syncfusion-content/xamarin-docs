---
layout: post
title: Font Settings in Syncfusion NumericUpDown control for Xamarin.Forms
description: This section explain, how to set the Font style in  Syncfusion NumericUpDown control for Xamarin.Forms.
platform: Xamarin
control: NumericUpDown
documentation: ug
---
# Font Settings in Xamarin NumericUpDown (SfNumericUpDown)

You can customize the font style of NumericUpDown using the following font-related properties that display the value's text:

* `FontSize` : Sets the font size for NumericUpDown’s text. 

* `FontAttributes` : Sets the style of NumericUpDown’s text. You can add three types of styles to it. It specifies style information like Italic and Bold (using the FontAttributes enumeration in C#).

1. Bold: Sets the style of NumericUpDown’s text to bold.
2. Italic: Sets the style of NumericUpDown’s text to italic.
3. None: Keeps the style of NumericUpDown’s text as same. It will not modify the style.

N> The default value of this property is None.

* `FontFamily` : Customizes the font family of the NumericUpDown’s text.

* `TextAlignment` : Sets the style of NumericUpDown’s text. We can give three types of style on it. It is specifying style information like Start,End and Center (using the TextAlignment enumeration in C#)

N> The default value of this property is Start.

The following code sample demonstrates how to set the font size and attributes in XAML and in C#.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="NumericUpDown" 
	                         FontSize="27" 
	                         FontAttribute="Bold" 
	                         Value="123" 
	                         TextAlignment="End" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericUpDown NumericUpDown=new SfNumericUpDown();
NumericUpDown.FontSize = 27;
NumericUpDown.Value = 123;
NumericUpDown.TextAlignment=TextAlignment.End;
NumericUpDown.FontAttribute = FontAttributes.Bold;
this.Content = NumericUpDown;

{% endhighlight %}

{% endtabs %}

![Display the NumericUpDown control with FontCustomization](images/textformatend.png)

## See also

[How to customize the text in the SfNumericUpDown](https://www.syncfusion.com/kb/7672/how-to-customise-the-text-present-in-the-sfnumericupdown)
