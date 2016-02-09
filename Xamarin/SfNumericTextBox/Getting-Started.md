---
layout: post
title: Getting Started with Syncfusion NumericTextBox control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion numerictextbox control for Xamarin.Forms platform
platform: Xamarin.Forms
control: NumericTextBox
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NumericTextBox for Xamarin.Forms. You can walk through the entire process of creating an NumericTextBox.

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
<td>iOS (Classic)</td>
<td>ios\Syncfusion.SfNumericTextBox.iOS.dll<br/>ios\Syncfusion.SfNumericTextBox.XForms.iOS.dll<br/>ios\Syncfusion.SfNumericTextBox.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfNumericTextBox.iOS.dll<br/>ios-unified\Syncfusion.SfNumericTextBox.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfNumericTextBox.XForms.dll</td>
</tr>
<tr>
<td>WindowsPhone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfNumericTextBox.XForms.dll<br/>wp8\Syncfusion.SfNumericTextBox.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WindowsPhone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfNumericTextBox.XForms.dll<br/>wp81\Syncfusion.SfNumericTextBox.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfNumericTextBox.XForms.dll<br/>winrt\Syncfusion.SfNumericTextBox.XForms.WinRT.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, WindowsPhone 8.1, WinRT and iOS projects. We need to create an instance of the numeric custom renderer as shown below. 

Create an instance of SfNumericTextBoxRenderer in MainPage constructor of the Windows Phone , WindowsPhone 8.1 and WinRT project as shown 

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

## Adding and Configuring the NumericTextBox

* Adding reference to numerictextbox.

{% highlight c# %}

	using Syncfusion.SfNumericTextBox.XForms;

{% endhighlight %}

* Create an instance of NumericTextBox.

{% highlight c# %}

	SfNumericTextBox sfNumericTextBox=new SfNumericTextBox();

{% endhighlight %}

* Configure the properties of NumericTextBox.

{% highlight c# %}

	SfNumericTextBox sfNumericTextBox = new SfNumericTextBox ();
	sfNumericTextBox.Value = 1000;
	sfNumericTextBox.Watermark = "Principal Amount";
	sfNumericTextBox.MaximumNumberDecimalDigits = 2;
	sfNumericTextBox.FormatString = "c";
	sfNumericTextBox.AllowNull = true;
	sfNumericTextBox.Culture = new System.Globalization.CultureInfo("fr-FR");

{% endhighlight %}


