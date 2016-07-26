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

### PCL 
pcl\Syncfusion.SfGauge.XForms.dll

### Android 
android\Syncfusion.SfGauge.Android.dll
android\Syncfusion.SfGauge.XForms.Android.dll
android\Syncfusion.SfGauge.XForms.dll

### iOS 
iOS-unified\Syncfusion.SfGauge.iOS.dll
iOS-unified\Syncfusion.SfGauge.XForms.iOS.dll
iOS-unified\Syncfusion.SfGauge.XForms.dll

### Windows Phone
wp8\Syncfusion.SfInput.WP8.dll
wp8\Syncfusion.SfShared.WP8.dll
wp8\Syncfusion.SfGauge.XForms.dll
wp8\Syncfusion.SfGauge.XForms.WinPhone.dll

### Windows Phone 8.1
wp81\Syncfusion.SfInput.WP.dll
wp81\Syncfusion.SfShared.WP.dll
wp81\Syncfusion.SfGauge.XForms.dll
wp81\Syncfusion.SfGauge.XForms.WinPhone.dll

### WinRT 
winrt\Syncfusion.SfInput.WinRT.dll
winrt\Syncfusion.SfShared.WinRT.dll
winrt\Syncfusion.SfGauge.XForms.dll
winrt\Syncfusion.SfGauge.XForms.WinRT.dll

### UWP 
uwp\Syncfusion.SfInput.UWP.dll
uwp\Syncfusion.SfShared.UWP.dll
uwp\Syncfusion.SfGauge.XForms.dll
uwp\Syncfusion.SfGauge.XForms.UWP.dll

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the linear gauge custom renderer as shown below. 

Create an instance of SfLinearGaugeRenderer in MainPage constructor of the Windows Phone and  Windows Phone 8.1 project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
	new SfLinearGaugeRenderer();  
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfLinearGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfLinearGaugeRenderer ();
}	

{% endhighlight %}

{% endtabs %}

## Add SfLinearGauge

The SfLinearGauge control configured entirely in C# code or by using XAML markup.The following steps explains how to create an SfLinearGauge and configure its elements.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:linear="clr-namespace:Syncfusion.SfGauge.XForms;assembly=Syncfusion.SfGauge.XForms"/>
	
{% endhighlight %}


{% highlight c# %}

	using Syncfusion.SfGauge.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfLinearGauge control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}
<ContentPage.Content>
	<gauge:SfLinearGauge x:Name="linearGauge" />
</ContentPage.Content>
{% endhighlight %}


{% highlight c# %}

SfLinearGauge linearGauge=new SfLinearGauge();
this.Content = linearGauge;

{% endhighlight %}

{% endtabs %}

## Add Scales

The scale that point out to the values can be added by instantiating LinearScale class and setting minimum values, maximum values, scale intervals and colors etc.

{% tabs %}

{% highlight xaml %}
<ContentPage.Content>
	<linear:SfLinearGauge>
				<linear:SfLinearGauge.Scales>
					<linear:LinearScale x:Name="scale" MinimumValue="0" MaximumValue="100" Interval="20" ScaleBarLength="100" ScaleBarColor="#FAECEC" MinorTicksPerInterval="1" ScaleBarSize="13" ScalePosition="BackWard" >						
					</linear:LinearScale>
				</linear:SfLinearGauge.Scales>
			</linear:SfLinearGauge>	
</ContentPage.Content>
{% endhighlight %}


{% highlight c# %}

//Adding scale to SfLinearGauge.
SfLinearGauge linearGauge = new SfLinearGauge();
LinearScale scale = new LinearScale();
scale.MinimumValue = 0;
scale.MaximumValue = 100;
scale.Interval = 20;
scale.ScaleBarLength = 100;
scale.ScaleBarColor = Color.FromRgb(250, 236, 236);
scale.LabelColor = Color.FromRgb(84, 84, 84);
scale.MinorTicksPerInterval = 1;
scale.ScaleBarSize = 13;
scale.ScalePosition = ScalePosition.BackWard;
linearGauge.Scales.Add(scale);

			
this.Content = linearGauge;
	
{% endhighlight %}

{% endtabs %}

## Add a Symbol Pointer

An arrow head that points to the value is called the Symbol Pointer which can be added by instantiating the SymbolPointer class and assigning it to the Pointers collection.

{% tabs %}

{% highlight xaml %}
<ContentPage.Content>
		<linear:SfLinearGauge>
				<linear:SfLinearGauge.Scales>
					<linear:LinearScale x:Name="scale" MinimumValue="0" MaximumValue="100" Interval="20" ScaleBarLength="100" ScaleBarColor="#FAECEC" MinorTicksPerInterval="1" ScaleBarSize="13" ScalePosition="BackWard" >
						<linear:LinearScale.Pointers>
							<linear:SymbolPointer x:Name="symbolPointer" Value="50"  Offset="0.0" Thickness="3" />
						</linear:LinearScale.Pointers>
					</linear:LinearScale>
				</linear:SfLinearGauge.Scales>
			</linear:SfLinearGauge>
</ContentPage.Content>
{% endhighlight %}

{% highlight c# %}

SfLinearGauge linearGauge = new SfLinearGauge();
LinearScale scale = new LinearScale();
scale.MinimumValue = 0;
scale.MaximumValue = 100;
scale.Interval = 20;
scale.ScaleBarLength = 100;
scale.ScaleBarColor = Color.FromRgb(250, 236, 236);
scale.LabelColor = Color.FromRgb(84, 84, 84);
scale.MinorTicksPerInterval = 1;
scale.ScaleBarSize = 13;
scale.ScalePosition = ScalePosition.BackWard;
linearGauge.Scales.Add(scale);

SymbolPointer symbolPointer = new SymbolPointer();
symbolPointer.Value = 50;
symbolPointer.Offset = 0.0;
symbolPointer.Thickness = 3;
scale.Pointers.Add(symbolPointer);

this.Content = linearGauge;
	
{% endhighlight %}

{% endtabs %}

## Add a Bar Pointer

A flat solid bar that points to the current value can be added by instantiating BarPointer and it can be added to pointers collection.

{% tabs %}

{% highlight xaml %}
<ContentPage.Content>
		<linear:SfLinearGauge>
				<linear:SfLinearGauge.Scales>
					<linear:LinearScale x:Name="scale" MinimumValue="0" MaximumValue="100" Interval="20" ScaleBarLength="100" ScaleBarColor="#FAECEC" MinorTicksPerInterval="1" ScaleBarSize="13" ScalePosition="BackWard" >
						<linear:LinearScale.Pointers>
							<linear:SymbolPointer x:Name="symbolPointer" Value="50"  Offset="0.0" Thickness="3" />
							<linear:BarPointer x:Name="rangePointer" Value="50"  Thickness="10" />
						</linear:LinearScale.Pointers>
					</linear:LinearScale>
				</linear:SfLinearGauge.Scales>
			</linear:SfLinearGauge>
</ContentPage.Content>
{% endhighlight %}

{% highlight C# %}

SfLinearGauge linearGauge = new SfLinearGauge();
LinearScale scale = new LinearScale();
scale.MinimumValue = 0;
scale.MaximumValue = 100;
scale.Interval = 20;
scale.ScaleBarLength = 100;
scale.ScaleBarColor = Color.FromRgb(250, 236, 236);
scale.LabelColor = Color.FromRgb(84, 84, 84);
scale.MinorTicksPerInterval = 1;
scale.ScaleBarSize = 13;
scale.ScalePosition = ScalePosition.BackWard;
linearGauge.Scales.Add(scale);

SymbolPointer symbolPointer = new SymbolPointer();
symbolPointer.Value = 50;
symbolPointer.Offset = 0.0;
symbolPointer.Thickness = 3;
scale.Pointers.Add(symbolPointer);

BarPointer rangePointer = new BarPointer();
rangePointer.Value = 50;
rangePointer.Color = Color.FromRgb(206, 69, 69);
rangePointer.Thickness = 10;
scale.Pointers.Add(rangePointer);		
this.Content = linearGauge;
	
{% endhighlight %}

{% endtabs %}

## Add a Range

We can improve the readability of data by including ranges that quickly displays when values fall within a specific ranges.

{% tabs %}

{% highlight xaml %}
<ContentPage.Content>
		<linear:SfLinearGauge>
				<linear:SfLinearGauge.Scales>
					<linear:LinearScale x:Name="scale" MinimumValue="0" MaximumValue="100" Interval="20" ScaleBarLength="100" ScaleBarColor="#FAECEC" MinorTicksPerInterval="1" ScaleBarSize="13" ScalePosition="BackWard" >
						<linear:LinearScale.Ranges>
							<linear:LinearRange x:Name="symbolRange" StartValue="0" Color="#FAECEC" EndValue="50" StartWidth="10" EndWidth="10" />
						</linear:LinearScale.Ranges>
						<linear:LinearScale.Pointers>
							<linear:SymbolPointer x:Name="symbolPointer" Value="50"  Offset="0.0" Thickness="3" />
							<linear:BarPointer x:Name="rangePointer" Value="50" Color="#CE4545"  Thickness="10" />
						</linear:LinearScale.Pointers>
					</linear:LinearScale>
				</linear:SfLinearGauge.Scales>
			</linear:SfLinearGauge>
</ContentPage.Content>
{% endhighlight %}

{% highlight c# %}    
	
SfLinearGauge linearGauge = new SfLinearGauge();
LinearScale scale = new LinearScale();
scale.MinimumValue = 0;
scale.MaximumValue = 100;
scale.Interval = 20;
scale.ScaleBarLength = 100;
scale.ScaleBarColor = Color.FromRgb(250, 236, 236);
scale.LabelColor = Color.FromRgb(84, 84, 84);
scale.MinorTicksPerInterval = 1;
scale.ScaleBarSize = 13;
scale.ScalePosition = ScalePosition.BackWard;
linearGauge.Scales.Add(scale);

SymbolPointer symbolPointer = new SymbolPointer();
symbolPointer.Value = 50;
symbolPointer.Offset = 0.0;
symbolPointer.Thickness = 3;
scale.Pointers.Add(symbolPointer);

BarPointer rangePointer = new BarPointer();
rangePointer.Value = 50;
rangePointer.Color = Color.FromRgb(206, 69, 69);
rangePointer.Thickness = 10;
scale.Pointers.Add(rangePointer);

LinearRange symbolRange = new LinearRange();
symbolRange.StartValue = 0;
symbolRange.EndValue = 50;
symbolRange.Color = Color.FromRgb(234, 248, 249);
symbolRange.StartWidth = 10;
symbolRange.EndWidth = 10;
scale.Ranges.Add(symbolRange);

this.Content = linearGauge;
	
{% endhighlight %}

{% endtabs %}

![](images/LinearGauge.png)