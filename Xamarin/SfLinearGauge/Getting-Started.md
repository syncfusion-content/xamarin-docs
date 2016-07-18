---
layout: post
title: Getting Started with Syncfusion LinearGauge control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion linearGauge control for Xamarin.Forms platform
platform: Xamarin
control: LinearGauge
documentation: ug
---

# Getting Started

This section explains the entire process of creating SfLinearGauge and configuring its properties.

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references needs to be added manually.

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
<td>pcl\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfGauge.Android.dll<br/>android\Syncfusion.SfGauge.XForms.Android.dll<br/>android\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfGauge.iOS.dll<br/>iOS-unified\Syncfusion.SfGauge.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfGauge.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfGauge.XForms.dll<br/>wp8\Syncfusion.SfGauge.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfGauge.XForms.dll<br/>wp81\Syncfusion.SfGauge.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfGauge.XForms.dll<br/>winrt\Syncfusion.SfGauge.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfGauge.XForms.dll<br/>uwp\Syncfusion.SfGauge.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the linear gauge custom renderer as shown below. 

Create an instance of SfLinearGaugeRenderer in MainPage constructor of the Windows Phone and  Windows Phone 8.1 project as shown 

{% highlight C# %}

public MainPage()

{

    new SfLinearGaugeRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfLinearGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfLinearGaugeRenderer ();

    ...

}	

{% endhighlight %}

## Adding and Configuring the SfLinearGauge

The SfLinearGauge control configured entirely in C# code or by using XAML markup.The following steps explain on how to create an SfLinearGauge and configure its elements.

* Adding reference to SfLinearGauge.

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfGauge.XForms;

{% endhighlight %}

{% highlight xaml %}

	xmlns:linear="clr-namespace:Syncfusion.SfGauge.XForms;assembly=Syncfusion.SfGauge.XForms"
	
{% endhighlight %}

{% endtabs %}

* Create an instance of SfLinearGauge.

{% tabs %}

{% highlight c# %}

   SfLinearGauge linearGauge=new SfLinearGauge();

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfLinearGauge x:Name="linearGauge" />
	
{% endhighlight %}

{% endtabs %}

## Add Scales

We will add one or more scale value to SfLinearGauge. Before adding that scales we have to set Maximum and Minimum value to this.

{% tabs %}

{% highlight c# %}

    //Adding scale to SfLinearGauge.
	LinearScale scale=new LinearScale();
	scale.MinimumValue=0;
	scale.MaximumValue=100;
	scale.Interval=20;
	scale.ScaleBarLength=100;
	scale.ScaleBarColor= Color.FromRgb (250, 236, 236);
	scale.LabelColor = Color.FromRgb (84, 84, 84); 
	scale.MinorTicksPerInterval = 1;
	scale.ScaleBarSize = 13;
	scale.ScalePosition = ScalePosition.BackWard;	
	linearGauge.Scales=scale;
	
{% endhighlight %}

{% highlight xaml %}

	<gauge:LinearScale x:Name="scale" MinimumValue="0" MaximumValue="100" Interval="20" ScaleBarLength="100" ScaleBarColor="Color.Red" MinorTicksPerInterval="1" ScaleBarSize="13" ScalePosition="Backward" />
	
{% endhighlight %}

{% endtabs %}

## Add Symbol Pointer

We can point a value on scale in SfLinearGauge by creating instance of `SymbolPointer`.

{% tabs %}

{% highlight c# %}

	SymbolPointer symbolPointer = new SymbolPointer ();
	symbolPointer.Value = 50;
	symbolPointer.Offset = 0.0;
	symbolPointer.Thickness = 3; 
	
{% endhighlight %}

{% highlight xaml %}

	<gauge:SymbolPointer x:Name="symbolPointer" Value="50" Offset="0.0" Thickness="3" />
	
{% endhighlight %}

{% endtabs %}

## Add a Bar Pointer

Before adding that symbol and bar pointer into Scale’s pointer add value of that pointers.

{% tabs %}

{% highlight C# %}

	BarPointer rangePointer = new BarPointer ();
	rangePointer.Value = 50;
	rangePointer.Color = Color.FromRgb (206, 69, 69);
	rangePointer.Thickness = 10;
	pointers.Add (symbolPointer);
	pointers.Add (rangePointer);
	
{% endhighlight %}

{% highlight xaml %}

	<gauge:BarPointer x:Name="rangePointer" Value="50" Offset="0.0" Thickness="10" />
	
{% endhighlight %}

{% endtabs %}


## Add a Range

We can improve the readability of data by including ranges that quickly displays when values fall within a specific ranges.

{% tabs %}

{% highlight c# %}

	LinearRange symbolRange = new LinearRange ();
	symbolRange.StartValue = 0;
	symbolRange.EndValue = 50;
	symbolRange.Color = Color.FromRgb (234, 248, 249);
	symbolRange.StartWidth = 10;
	symbolRange.EndWidth = 10; 
	
{% endhighlight %}

{% highlight xaml %}

	<gauge:LinearRange x:Name="symbolRange" StartValue="0" EndValue="50" StartWidth="10" EndWidth="10" />
	
{% endhighlight %}

{% endtabs %}

![](images/LinearGauge.png)