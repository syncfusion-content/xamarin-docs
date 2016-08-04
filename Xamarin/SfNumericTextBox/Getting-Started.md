---
layout: post
title: Getting Started with Syncfusion NumericTextBox control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion NumericTextBox control for Xamarin.Forms platform
platform: Xamarin
control: NumericTextBox
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfNumericTextBox control in a real-time scenario and also provides a walk-through on some of the customization features available in SfNumericTextBox control.

## Add SfNumericTextBox

You can then add the assembly references to the respective projects as shown below

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfNumericTextBox.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfNumericTextBox.Android.dll<br/>android\Syncfusion.SfNumericTextBox.XForms.Android.dll<br/>android\Syncfusion.SfNumericTextBox.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfNumericTextBox.iOS.dll<br/>iOS-unified\Syncfusion.SfNumericTextBox.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfNumericTextBox.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfNumericTextBox.XForms.dll<br/>wp8\Syncfusion.SfNumericTextBox.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfNumericTextBox.XForms.dll<br/>wp81\Syncfusion.SfNumericTextBox.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfNumericTextBox.XForms.dll<br/>winrt\Syncfusion.SfNumericTextBox.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfNumericTextBox.XForms.dll<br/>uwp\Syncfusion.SfNumericTextBox.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the NumericTextBox custom renderer as shown below. 

Create an instance of SfNumericTextBoxRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfNumericTextBoxRenderer(); 
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfNumericTextBoxRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfNumericTextBoxRenderer ();
}	

{% endhighlight %}

{% endtabs %}


The SfNumericTextBox control configured entirely in C# code or by using XAML markup. The following steps explains how to create a NumericTextBox and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:numeric="clr-namespace:Syncfusion.SfNumericTextBox.XForms;assembly=Syncfusion.SfNumericTextBox.XForms"/> 
	
{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfNumericTextBox.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfNumericTextBox control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" />
	
{% endhighlight %}

{% highlight c# %}

	SfNumericTextBox numericTextBox=new SfNumericTextBox();
	this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

## Set Value

The SfNumericTextBox control display value can be set using `Value` property.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" Value="123.45" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.Value = 123.45;
	this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}


## Enable Parsing Mode

SfNumericTextBox provides option to display the value in double or decimal. Following code shows the Decimal parsing mode which can be set through `ParsingMode` property.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" Value="123.45" ParsingMode="Decimal" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.ParsingMode=Parsers.Decimal;
	numericTextBox.Value = 123.45;
	this.Content = numericTextBox;
	
{% endhighlight %}

{% endtabs %}


## Add Format String

SfNumericTextBox provides option to format the display text in currency format. Following code explains how to set the currency format using `FormatString` property.

{% tabs %}

{% highlight xaml %}


	<numeric:SfNumericTextBox x:Name="numericTextBox" Value="123.45" ParsingMode="Decimal" FormatString="c" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
	numericTextBox.FormatString = "c";
	numericTextBox.Value = 123.45;
	this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

![](images/gettingstarted.png)