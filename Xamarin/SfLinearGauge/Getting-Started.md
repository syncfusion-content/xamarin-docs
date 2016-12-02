---
layout: post
title: Getting Started with Syncfusion LinearGauge control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion linearGauge control for Xamarin.Forms platform
platform: Xamarin
control: LinearGauge
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfLinearGauge control in a real-time scenario and also provides a walk-through on some of the customization features available in SfLinearGauge control.

## Add SfLinearGauge

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
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfGauge.XForms.dll<br/>uwp\Syncfusion.SfGauge.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for iOS project. We need to create an instance of the linear gauge custom renderer as shown below. 

Create an instance of SfLinearGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfLinearGaugeRenderer ();
}	

{% endhighlight %}

{% endtabs %}

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