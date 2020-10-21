---
layout: post
title: Getting Started with Syncfusion LinearGauge control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion linearGauge control for Xamarin.Forms platform and also describes how to add pointers and ranges
platform: Xamarin
control: LinearGauge
documentation: ug
---

# Getting Started with SfLinearGauge

This section explains the steps required to configure a [`SfLinearGauge`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SfLinearGauge.html) control in a real-time scenario and also provides a walk-through on some of the customization features available in [`SfLinearGauge`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SfLinearGauge.html) control.

## Adding SfLinearGauge reference

You can add SfLinearGauge reference using one of the following methods:

**Method 1: Adding SfLinearGauge reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfLinearGauge to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfGauge](https://www.nuget.org/packages/Syncfusion.Xamarin.SfGauge), and then install it.

![Adding SfLinearGauge reference from NuGet](getting-started_images/Adding SfLinearGauge reference.png)

N> Install the same version of SfLinearGauge NuGet in all the projects.

**Method 2: Adding SfLinearGauge reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfLinearGauge control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfLinearGauge assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfGauge.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfGauge.Android.dll<br/>Syncfusion.SfGauge.XForms.Android.dll<br/>Syncfusion.SfGauge.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfGauge.iOS.dll<br/>Syncfusion.SfGauge.XForms.iOS.dll<br/>Syncfusion.SfGauge.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfGauge.UWP.dll<br/>Syncfusion.SfGauge.XForms.UWP.dll<br/>Syncfusion.SfGauge.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching an application on each platform with SfLinearGauge.

To use the SfLinearGauge control inside an application, each platform requires some additional configurations. The configurations vary from platform to platform and is discussed in the following sections:

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the SfLinearGauge in iOS, call the `SfLinearGaugeRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework has been initialized and before the LoadApplication is called, as demonstrated in the following code example.

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    Syncfusion.SfGauge.XForms.iOS.SfGaugeRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 

### Universal Windows Platform (UWP)

You need to initialize the linear gauge view assemblies in App.xaml.cs in UWP project as demonstrated in the following code samples. This is required to deploy the application with linear gauge in Release mode in UWP platform.

{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
    {
        …
    	    rootFrame.NavigationFailed += OnNavigationFailed;
    
        // Add `using System.Reflection;`
        List<Assembly> assembliesToInclude = new List<Assembly>();
    
        // Now, add all the assemblies your app uses                 
        assembliesToInclude.Add(typeof(Syncfusion.SfGauge.XForms.UWP.SfGaugeRenderer).GetTypeInfo().Assembly);
		
        // Replaces Xamarin.Forms.Forms.Init(e);        
        Xamarin.Forms.Forms.Init(e, assembliesToInclude);	
        …     
    }

{% endhighlight %}

### Android

The Android platform does not require any additional configuration to render the linear gauge.

## Reference Mono.Android.Export

1. In the Solution Explorer in the Android project, right-click on References and choose Add Reference.

2. In the Add Reference window, select the Assemblies tab and choose the Framework.

3. In the Framework tab, ensure Mono.Android and Mono.Android.Export  is checked and click ok.

![Add Reference in Linear Gauge](getting-started_images/add_reference.png)

**Adding namespace for the added assemblies**

{% tabs %}

{% highlight xaml %}

	     xmlns:linear="clr-namespace:Syncfusion.SfGauge.XForms;assembly=Syncfusion.SfGauge.XForms"
	
{% endhighlight %}

{% highlight c# %}

	      using Syncfusion.SfGauge.XForms;

{% endhighlight %}

{% endtabs %}

## Initialize gauge

You can initialize the [`SfLinearGauge`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SfLinearGauge.html) control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

			<gauge:SfLinearGauge/>

{% endhighlight %}

{% highlight c# %}

		SfLinearGauge linearGauge = new SfLinearGauge();
		this.Content = linearGauge;

{% endhighlight %}

{% endtabs %}

## Adding header

You can assign a unique header to [`SfLinearGauge`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SfLinearGauge.html) by using the [`LinearHeader`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearHeader.html) property and position it wherever as you desired by using the [`Offset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearHeader.html#Syncfusion_SfGauge_XForms_LinearHeader_Offset) property.

{% tabs %}

{% highlight xaml %}

         <gauge:SfLinearGauge>
		 
             <gauge:SfLinearGauge.Header>
                <gauge:LinearHeader Text="Thermometer" TextSize="20" FontAttributes="Bold" Offset="0.35,0.35"/>
             </gauge:SfLinearGauge.Header>
			 
         </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

		SfLinearGauge linearGauge=new SfLinearGauge(); 
        LinearHeader linearHeader = new LinearHeader();
        linearHeader.Text = "Thermometer";
        linearHeader.TextSize = 20;
        linearHeader.FontAttributes = FontAttributes.Bold;
        linearHeader.Offset = new Point(0.35, 0.35);
        linearGauge.Header = linearHeader;

{% endhighlight %}

{% endtabs %}

## Configuring scales

Scales is a collection of [`LinearScale`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearScale.html), which is used to indicate the numeric values. Scale bar, ticks, labels, ranges, and pointers are the sub elements of a scale. 

The [`MinimumValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearScale.html#Syncfusion_SfGauge_XForms_LinearScale_MinimumValue) and [`MaximumValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearScale.html#Syncfusion_SfGauge_XForms_LinearScale_MaximumValue) properties allow you to set the scale range.

{% tabs %}

{% highlight xaml %}

	    <gauge:SfLinearGauge>
            <gauge:SfLinearGauge.Scales>
            <gauge:LinearScale ScaleBarColor="#e0e0e0" LabelColor="#424242">
                    <gauge:LinearScale.MajorTickSettings>
                        <gauge:LinearTickSettings Thickness="1"  Color="Gray" Length="15"/>
                    </gauge:LinearScale.MajorTickSettings>
                    <gauge:LinearScale.MinorTickSettings>
                        <gauge:LinearTickSettings Thickness="1"  Color="Gray" Length="7"/>
                    </gauge:LinearScale.MinorTickSettings>
                </gauge:LinearScale>
        </gauge:SfLinearGauge.Scales>
        </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

		LinearScale linearScale = new LinearScale();
        linearScale.ScaleBarColor = Color.FromHex("#e0e0e0");
        linearScale.LabelColor = Color.FromHex("#424242");
        linearScale.MajorTickSettings.Thickness = 1;
        linearScale.MajorTickSettings.Length = 15;
        linearScale.MajorTickSettings.Color = Color.Gray;
        linearScale.MinorTickSettings.Color = Color.Gray;
        linearScale.MinorTickSettings.Length = 7;
        linearScale.MinorTickSettings.Thickness = 1;
        linearGauge.Scales.Add(linearScale);
	    this.Content = linearGauge;
	
{% endhighlight %}

{% endtabs %}

## Adding a symbol pointer

[`SymbolPointer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SymbolPointer.html) is a shape that can be placed to mark the pointer value in gauge.

{% tabs %}

{% highlight xaml %}

            <gauge:LinearScale.Pointers>
                <gauge:SymbolPointer Value="60" Offset="45" Color="#757575"/>
            </gauge:LinearScale.Pointers>

{% endhighlight %}

{% highlight c# %}

	    SymbolPointer symbolPointer = new SymbolPointer();
        symbolPointer.Value = 60;
        symbolPointer.Offset = 45;
        symbolPointer.Color = Color.FromHex("#757575");
        linearScale.Pointers.Add(symbolPointer);

{% endhighlight %}

{% endtabs %}

## Adding a bar pointer

[`BarPointer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.BarPointer.html) is used to mark the scale values. It starts at the beginning of gauge and ends at the pointer value.

{% tabs %}

{% highlight xaml %}

                    <gauge:LinearScale.Pointers>
                        <gauge:BarPointer Value="50" Color="#757575" />
                    </gauge:LinearScale.Pointers>

{% endhighlight %}

{% highlight C# %}

		BarPointer barPointer = new BarPointer();
        barPointer.Value = 50;
        barPointer.Color = Color.FromHex("#757575");
        linearScale.Pointers.Add(barPointer);
	
{% endhighlight %}

{% endtabs %}

## Adding ranges

You can categorize the scale values using the start and end values properties in [`LinearRange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearRange.html). You can add multiple ranges for a scale using the `ranges` property.

{% tabs %}

{% highlight xaml %}
		
                    <gauge:LinearScale.Ranges>
                        <gauge:LinearRange StartValue="0" EndValue="40" Color="#27beb7" Offset="-20"/>
                        <gauge:LinearRange StartValue="40" EndValue="100" Color="LightCyan" Offset="-20"/>
                    </gauge:LinearScale.Ranges>

{% endhighlight %}

{% highlight c# %}    
	
		LinearRange linearRange = new LinearRange();
        linearRange.StartValue = 0;
        linearRange.EndValue = 40;
        linearRange.Color = Color.FromHex("#27beb7");
        linearRange.Offset = -20;
        linearScale.Ranges.Add(linearRange);

        LinearRange linearRange1 = new LinearRange();
        linearRange1.StartValue = 40;
        linearRange1.EndValue = 100;
        linearRange1.Color = Color.LightCyan;
        linearRange1.Offset = -20;
        linearScale.Ranges.Add(linearRange1);
        linearGauge.Scales.Add(linearScale);
	
{% endhighlight %}

{% endtabs %}

The following code example gives you the complete code of above configurations.

{% tabs %}

{% highlight xaml %} 

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:gauge="clr-namespace:Syncfusion.SfGauge.XForms;assembly=Syncfusion.SfGauge.XForms"  
             xmlns:local="clr-namespace:Gauge_GettingStarted"
             x:Class="Gauge_GettingStarted.MainPage">

    <gauge:SfLinearGauge>
        <gauge:SfLinearGauge.Header>
            <gauge:LinearHeader Text="Thermometer" TextSize="20" FontAttributes="Bold" Offset="0.35,0.35"/>
        </gauge:SfLinearGauge.Header>
        <gauge:SfLinearGauge.Scales>
            <gauge:LinearScale ScaleBarColor="#e0e0e0" LabelColor="#424242">
                <gauge:LinearScale.MajorTickSettings>
                    <gauge:LinearTickSettings Thickness="1"  Color="Gray" Length="15"/>
                </gauge:LinearScale.MajorTickSettings>
                <gauge:LinearScale.MinorTickSettings>
                    <gauge:LinearTickSettings Thickness="1"  Color="Gray" Length="7"/>
                </gauge:LinearScale.MinorTickSettings>
                <gauge:LinearScale.Pointers>
                    <gauge:SymbolPointer Value="60" Offset="45" Color="#757575"/>
                    <gauge:BarPointer Value="50" Color="#757575" />
                </gauge:LinearScale.Pointers>
                <gauge:LinearScale.Ranges>
                    <gauge:LinearRange StartValue="0" EndValue="40" Color="#27beb7" >
                        <gauge:LinearRange.Offset>
                            <OnPlatform x:TypeArguments="x:Double" iOS="-20" Android="-20" WinPhone="-40" />
                        </gauge:LinearRange.Offset>
                    </gauge:LinearRange>
                    <gauge:LinearRange StartValue="40" EndValue="100" Color="LightCyan">
                        <gauge:LinearRange.Offset>
                            <OnPlatform x:TypeArguments="x:Double" iOS="-20" Android="-20" WinPhone="-40" />
                        </gauge:LinearRange.Offset>
                    </gauge:LinearRange>
                </gauge:LinearScale.Ranges>
            </gauge:LinearScale>
        </gauge:SfLinearGauge.Scales>
        
    </gauge:SfLinearGauge>
</ContentPage>
	 
{% endhighlight %}

{% highlight c# %}  
   
using Syncfusion.SfGauge.XForms;
using Xamarin.Forms;

namespace Gauge_GettingStarted
{
	public partial class MainPage : ContentPage
	{
		public MainPage()
		{
			InitializeComponent();

            //Initializing linear gauge
            SfLinearGauge linearGauge = new SfLinearGauge();

            //Adding header 
            LinearHeader linearHeader = new LinearHeader();
            linearHeader.Text = "Thermometer";
            linearHeader.TextSize = 20;
            linearHeader.FontAttributes = FontAttributes.Bold;
            linearHeader.Offset = new Point(0.35, 0.35);
            linearGauge.Header = linearHeader;

            //Initializing scale for linear gauge
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarColor = Color.FromHex("#e0e0e0");
            linearScale.LabelColor = Color.FromHex("#424242");
            linearScale.MajorTickSettings.Thickness = 1;
            linearScale.MajorTickSettings.Length = 15;
            linearScale.MajorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Length = 7;
            linearScale.MinorTickSettings.Thickness = 1;
            linearGauge.Scales.Add(linearScale);

            //Adding symbol pointer
            SymbolPointer symbolPointer = new SymbolPointer();
            symbolPointer.Value = 60;
            symbolPointer.Offset = 45;
            symbolPointer.Color = Color.FromHex("#757575");
            linearScale.Pointers.Add(symbolPointer);

            //Adding bar pointer
            BarPointer barPointer = new BarPointer();
            barPointer.Value = 50;
            barPointer.Color = Color.FromHex("#757575");
            linearScale.Pointers.Add(barPointer);

            //Adding linear ranges
            LinearRange linearRange = new LinearRange();
            linearRange.StartValue = 0;
            linearRange.EndValue = 40;
            linearRange.Color = Color.FromHex("#27beb7");
            linearRange.Offset = Device.RuntimePlatform == Device.iOS ? -20 : Device.RuntimePlatform == Device.Android ? -20 : -40;
            linearScale.Ranges.Add(linearRange);

            LinearRange linearRange1 = new LinearRange();
            linearRange1.StartValue = 40;
            linearRange1.EndValue = 100;
            linearRange1.Color = Color.LightCyan;
            linearRange1.Offset = Device.RuntimePlatform == Device.iOS ? -20 : Device.RuntimePlatform == Device.Android ? -20 : -40;
            linearScale.Ranges.Add(linearRange1);
            linearGauge.Scales.Add(linearScale);
            this.Content = linearGauge;
        }
    }
}
	
{% endhighlight %}
       
{% endtabs %}

The following screenshot illustrates the result of the above codes.
 
![Linear Gauge Getting Started](getting-started_images/getting-started.png)

You can find the complete getting started sample from this [`link`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Gauge-GettingStarted323564295).  

## See also

[How to resolve gauge not rendering issue in Xamarin.Forms for iOS](https://www.syncfusion.com/kb/7994/how-to-resolve-sfgauge-not-rendering-issue-in-xamarin-forms-for-ios)

[How to design a thermometer using the linear gauge](https://www.syncfusion.com/kb/11384/how-to-design-a-thermometer-using-the-xamarin-forms-linear-gauge-sflineargauge)

