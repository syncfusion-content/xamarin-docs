---
layout: post
title: Getting Started with Syncfusion NumericTextBox control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion NumericTextBox control for Xamarin.Forms platform
platform: Xamarin.Forms
control: NumericTextBox
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NumericTextBox for Xamarin.Forms. You can walk through the entire process of creating a NumericTextBox.

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
<td>pcl\Syncfusion.SfNumericTextBox.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfNumericTextBox.Android.dll<br/>android\Syncfusion.SfNumericTextBox.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfNumericTextBox.iOS.dll<br/>ios-unified\Syncfusion.SfNumericTextBox.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfNumericTextBox.XForms.dll</td>
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
<td>uwp\Syncfusion.SfNumericTextBox.UWP.dll<br/>uwp\Syncfusion.SfNumericTextBox.XForms.dll<br/>uwp\Syncfusion.SfNumericTextBox.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the NumericTextBox custom renderer as shown below. 

Create an instance of SfNumericTextBoxRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% highlight C# %}

public MainPage()

{

    new SfNumericTextBoxRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfNumericTextBoxRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfNumericTextBoxRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the NumericTextBox

The NumericTextBox control configured entirely in C# code or by using XAML markup. The following steps explain on how to create a NumericTextBox and configure its elements,

* Adding reference to NumericTextBox.

{% highlight c# %}

	using Syncfusion.SfNumericTextBox.XForms;

{% endhighlight %}

* Create an instance of NumericTextBox.

{% highlight c# %}

	SfNumericTextBox sfNumericTextBox=new SfNumericTextBox();

{% endhighlight %}

## Setting Value

The NumericTextBox control display value can be set using `Value` property.

{% highlight c# %}

	sfNumericTextBox.Value = 123.45;

{% endhighlight %}


## Enable Parsing Mode

The value of the NumericTextBox can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal.

{% highlight c# %}

	sfNumericTextBox.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}


## Add Format String

The `FormatString` property determines the format specifier by which the display text has to be formatted. 

It has three types,

* c - Display the value with currency notation.
* n – Display the value in number format.
* p – Display the value in Percentage.

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

{% highlight c# %}

	sfNumericTextBox.FormatString = "c";

{% endhighlight %}

![](images/FormatString.png)