---
layout: post
title: Getting Started with Syncfusion NumericTextBox control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion NumericTextBox control for Xamarin.Forms platform
platform: Xamarin
control: NumericTextBox
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NumericTextBox for Xamarin.Forms.

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
{% tabs %}

{% highlight PCL %}
pcl\Syncfusion.SfNumericTextBox.XForms.dll
{% endhighlight %}

{% highlight Android %}
android\Syncfusion.SfNumericTextBox.Android.dll
android\Syncfusion.SfNumericTextBox.XForms.Android.dll
android\Syncfusion.SfNumericTextBox.XForms.dll
{% endhighlight %}

{% highlight iOS %}
iOS-unified\Syncfusion.SfNumericTextBox.iOS.dll
iOS-unified\Syncfusion.SfNumericTextBox.XForms.iOS.dll
iOS-unified\Syncfusion.SfNumericTextBox.XForms.dll
{% endhighlight %}

{% highlight Windows %}
### Windows Phone
wp8\Syncfusion.SfInput.WP8.dll
wp8\Syncfusion.SfShared.WP8.dll
wp8\Syncfusion.SfNumericTextBox.XForms.dll
wp8\Syncfusion.SfNumericTextBox.XForms.WinPhone.dll

### Windows Phone 8.1
wp81\Syncfusion.SfInput.WP.dll
wp81\Syncfusion.SfShared.WP.dll
wp81\Syncfusion.SfNumericTextBox.XForms.dll
wp81\Syncfusion.SfNumericTextBox.XForms.WinPhone.dll
{% endhighlight %}

{% highlight WinRT %}
winrt\Syncfusion.SfInput.WinRT.dll
winrt\Syncfusion.SfShared.WinRT.dll
winrt\Syncfusion.SfNumericTextBox.XForms.dll
winrt\Syncfusion.SfNumericTextBox.XForms.WinRT.dll
{% endhighlight %}

{% highlight UWP %}
uwp\Syncfusion.SfInput.UWP.dll
uwp\Syncfusion.SfShared.UWP.dll
uwp\Syncfusion.SfNumericTextBox.XForms.dll
uwp\Syncfusion.SfNumericTextBox.XForms.UWP.dll
{% endhighlight %}

{% endtabs %}

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the NumericTextBox custom renderer as shown below. 

Create an instance of SfNumericTextBoxRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% highlight C# %}

public MainPage()

{
    new SfNumericTextBoxRenderer(); 
}

{% endhighlight %}

Create an instance of SfNumericTextBoxRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{
    new SfNumericTextBoxRenderer ();
}	

{% endhighlight %}

## Add and Configure the SfNumericTextBox

The SfNumericTextBox control configured entirely in C# code or by using XAML markup. The following steps explain on how to create a NumericTextBox and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfNumericTextBox.XForms;

{% endhighlight %}

{% highlight xaml %}

	<xmlns:numeric="clr-namespace:Syncfusion.SfNumericTextBox.XForms;assembly=Syncfusion.SfNumericTextBox.XForms"/> 
	
{% endhighlight %}

{% endtabs %}

* Now add the SfNumericTextBox control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

	SfNumericTextBox numericTextBox=new SfNumericTextBox();

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" />
	
{% endhighlight %}

{% endtabs %}

## Setting Value

The SfNumericTextBox control display value can be set using `Value` property.

{% tabs %}

{% highlight c# %}

	numericTextBox.Value = 123.45;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" Value="123.45" />
	
{% endhighlight %}

{% endtabs %}


## Enable Parsing Mode

The value of the SfNumericTextBox can be parsed based on the `ParsingMode` property. 

N> The `ParsingMode` is of type Parsers containing enum values of Double and Decimal.

{% tabs %}

{% highlight c# %}

	numericTextBox.ParsingMode=Parsers.Decimal;
	
{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" ParsingMode="Decimal" />
	
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

{% highlight c# %}

	numericTextBox.FormatString = "c";

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericTextBox x:Name="numericTextBox" FormatString="c" />
	
{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)