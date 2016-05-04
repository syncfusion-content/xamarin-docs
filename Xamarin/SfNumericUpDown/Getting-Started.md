---
layout: post
title: Getting Started with Syncfusion NumericUpDown control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion NumericUpDown control for Xamarin.Forms platform
platform: Xamarin.Forms
control: NumericUpDown
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NumericUpDown for Xamarin.Forms. You can walk through the entire process of creating a NumericUpDown.

![](images/gettingstarted.png)

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfNumericUpDown.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfNumericUpDown.Android.dll<br/>android\Syncfusion.SfNumericUpDown.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfNumericUpDown.iOS.dll<br/>ios-unified\Syncfusion.SfNumericUpDown.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfNumericUpDown.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfNumericUpDown.XForms.dll<br/>wp8\Syncfusion.SfNumericUpDown.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfNumericUpDown.XForms.dll<br/>wp81\Syncfusion.SfNumericUpDown.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfNumericUpDown.XForms.dll<br/>winrt\Syncfusion.SfNumericUpDown.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfNumericUpDown.UWP.dll<br/>uwp\Syncfusion.SfNumericUpDown.XForms.dll<br/>uwp\Syncfusion.SfNumericUpDown.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the NumericUpDown custom renderer as shown below. 

Create an instance of SfNumericUpDownRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 

{% highlight C# %}

public MainPage()

{

    new SfNumericUpDownRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfNumericUpDownRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfNumericUpDownRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the NumericUpDown

The NumericUpDown control configured entirely in C# code or by using XAML markup. The following steps explain on how to create a NumericUpDown and configure its elements,

* Adding reference to NumericUpDown.

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfNumericUpDown.XForms;

{% endhighlight %}

{% highlight xaml %}

	xmlns:numeric="clr-namespace:Syncfusion.SfNumericUpDown.XForms;assembly=Syncfusion.SfNumericUpDown.XForms"
	
{% endhighlight %}

{% endtabs %}


* Create an instance of NumericUpDown.

{% tabs %}

{% highlight C# %}

	SfNumericUpDown numericUpDown=new SfNumericUpDown();
	this.Content = numericUpDown;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown />
	
{% endhighlight %}

{% endtabs %}

## Setting Value

The NumericUpDown control display value can be set using `Value` property. 

{% tabs %}

{% highlight C# %}

	numericUpDown.Value= 5;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" Value="5"/>
	
{% endhighlight %}

{% endtabs %}

## Enable Parsing Mode

The value of the NumericUpDown can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal.

{% tabs %}

{% highlight c# %}

	numericUpDown.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" ParsingMode="Decimal"/>
	
{% endhighlight %}

{% endtabs %}


## Add Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

It has three types,

* c - Display the value with currency notation.
* n – Display the value in number format.
* p – Display the value in Percentage.

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

{% tabs %}

{% highlight C# %}

	numericUpDown.FormatString= “c”;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" FormatString="c"/>
	
{% endhighlight %}

{% endtabs %}
