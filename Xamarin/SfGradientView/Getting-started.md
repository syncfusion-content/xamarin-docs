---
layout: post
title: Getting started | SfGradientView | Xamarin | Syncfusion
description: A quick tour to initial users on Syncfusion border control for Xamarin.Forms platform.
platform: xamarin
control: SfGradientView
documentation: ug
---

# Getting Started

This section explains the steps required to work with the gradient view control for Xamarin.Forms.

## Adding SfGradientView reference

You can add SfGradientView reference using one of the following methods:

**Method 1: Adding SfGradientView reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfGradientView to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Core](https://www.nuget.org/packages/Syncfusion.Xamarin.Core), and then install it.

![Xamarin Forms SfGradientView Nuget reference](images/Adding SfGradientView reference.png)

N> Install the same version of SfGradientView NuGet in all the projects.

**Method 2: Adding SfGradientView reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfGradientView control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfGradientView assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v17.1.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching an application on each platform with SfGradientView.

To use the SfGradientView control inside an application, each platform application must initialize the SfGradientViewRenderer. This initialization step varies from platform to platform and is discussed in the following sections:

### Android and UWP

The Android and UWP platforms launch the SfGradientView without any initialization, and it is enough to only initialize the Xamarin.Forms Framework to launch an application.

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the SfGradientView in iOS, call the `SfGradientViewRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework has been initialized and before the LoadApplication is called, as demonstrated in the following code example.

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    Syncfusion.XForms.iOS.Graphics.SfGradientViewRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 

### Release mode issue in UWP platform

The known Framework issue in UWP platform is that the custom controls will not be rendered when deployed an application in `Release Mode`. It can be resolved by initializing the SfGradientView assemblies in the `App.xaml.cs` file in the UWP project, as demonstrated in the following code example.

{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
    {
        …
    	    rootFrame.NavigationFailed += OnNavigationFailed;
    
        // Add `using System.Reflection;`
        List<Assembly> assembliesToInclude = new List<Assembly>();
    
        // Now, add all the assemblies your app uses                 
        assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Graphics.SfGradientViewRenderer).GetTypeInfo().Assembly);
		
        // Replaces Xamarin.Forms.Forms.Init(e);        
        Xamarin.Forms.Forms.Init(e, assembliesToInclude);	
        …     
    }

{% endhighlight %}

## Creating SfGradientView control

The `SfGradientView` control is configured entirely in C# code or in XAML markup. The following steps explain how to create a `SfGradientView` and configure its elements.

### Adding namespace for referred assemblies

{% tabs %} 

{% highlight xaml %} 

xmlns:gradient ="clr-namespace:Syncfusion.XForms.Graphics;assembly=Syncfusion.Core.XForms" 

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Graphics; 

{% endhighlight %}

{% endtabs %}

### Add the SfGradientView control as the content of ContentPage.

#### Adding LinearGradientbrush for SfGradientView

{% tabs %}
{% highlight xaml %}

<Grid>    
    <gradient:SfGradientView>
        <gradient:SfGradientView.BackgroundBrush>           
            <gradient:SfRadialGradientBrush>                
                <gradient:SfRadialGradientBrush.GradientStops>
                    <gradient:SfGradientStop Color="#2d265b" Offset="0.0" />
                    <gradient:SfGradientStop Color="#b8495c" Offset="1.0" />
                </gradient:SfRadialGradientBrush.GradientStops>                
            </gradient:SfRadialGradientBrush>            
        </gradient:SfGradientView.BackgroundBrush>
    </gradient:SfGradientView>  
</Grid>

{% endhighlight %}
{% highlight c# %}

using Xamarin.Forms;
using Syncfusion.XForms.Graphics;
using System;

namespace GradientViewGettingStarted
{
    public partial class MainPage : ContentPage
    { 
        Public MainPage()
        {
            InitializeComponent();

            Grid grid = new Grid();
            SfGradientView gradientView = new SfGradientView();
            SfLinearGradientBrush linearGradientBrush = new SfLinearGradientBrush();
            linearGradientBrush.GradientStops = new GradientStopCollection()
            {
                new SfGradientStop(){Color = Color.FromHex("#2d265b "), Offset=0.0},
                new SfGradientStop(){Color = Color.FromHex("#b8495c "), Offset=1.0},
            };
            gradientView.BackgroundBrush = linearGradientBrush;
            grid.Children.Add(gradientView);
            this.Content = grid;
        }
    }
}
 
{% endhighlight %}
{% endtabs %}

![SfGradientView](images/LinearGradientView.png)

#### Adding RadialGradientBrush for SfGradientView

{% tabs %}
{% highlight xaml %}

<Grid>    
    <gradient:SfGradientView>
        <gradient:SfGradientView.BackgroundBrush>           
            <gradient:SfRadialGradientBrush>                
                <gradient:SfRadialGradientBrush.GradientStops>
                    <gradient:SfGradientStop Color="Red" Offset="0.0" />
                    <gradient:SfGradientStop Color="Yellow" Offset="0.5" />
                    <gradient:SfGradientStop Color="LightGreen" Offset="1.0" />
                </gradient:SfRadialGradientBrush.GradientStops>                
            </gradient:SfRadialGradientBrush>            
        </gradient:SfGradientView.BackgroundBrush>
    </gradient:SfGradientView>  
</Grid>

{% endhighlight %}
{% highlight c# %}

using Xamarin.Forms;
using Syncfusion.XForms.Graphics;
using System;

namespace GradientViewGettingStarted
{
    public partial class MainPage : ContentPage
    { 
        Public MainPage()
        {
            InitializeComponent();

            Grid grid = new Grid();
            SfGradientView gradientView = new SfGradientView();
            SfRadialGradientBrush radialGradientBrush = new SfRadialGradientBrush();
            radialGradientBrush.GradientStops = new GradientStopCollection()
            {
                new SfGradientStop(){Color = Color.Red, Offset=0.0},
                new SfGradientStop(){Color = Color.Yellow, Offset=0.5},
                new SfGradientStop(){Color = Color.LightGreen, Offset=1.0},
            };
            gradientView.BackgroundBrush = radialGradientBrush;
            grid.Children.Add(gradientView);
            this.Content = grid;
        }
    }
}

 
{% endhighlight %}
{% endtabs %}

![SfGradientView](images/RadialGradient.jpg)

You can find the complete getting started sample from [this](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted272847391.zip) link.