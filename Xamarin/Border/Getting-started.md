---
layout: post
title: Getting Started with SfBorder | Xamarin | Syncfusion
description: This section provides a quick tour for new users of the Syncfusion SfBorder control in Xamarin.Forms.
platform: Xamarin
control: SfBorder
documentation: ug
---

# Getting Started with SfBorder

This tutorial provides an overview for working with the SfBorder control in Xamarin.Forms and guides you through creating a real-world application.

## Assembly Deployment

After installing [Essential Studio® for Xamarin](https://www.syncfusion.com/downloads/xamarin), locate all necessary assemblies in: `{Syncfusion Essential Studio Installed location}/Essential Studio/{Version #}/Xamarin/lib`.

E.g.: C:\Program Files (x86) \Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

> **Note:** On Mac, assemblies can be found in: `Documents/Syncfusion/{Version #}/Xamarin/lib`.
## Adding SfBorder Reference

You can add the SfBorder reference using one of the following methods:

You can add SfBorder reference using one of the following methods:

**Method 1: Adding SfBorder reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfBorder to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Core](https://www.nuget.org/packages/Syncfusion.Xamarin.Core), and then install it.

![Xamarin Forms SfBorder Nuget reference](images/Adding SfBorder reference.png)

N> 
* Install the same version of SfBorder NuGet in all the projects.
* In addition, you need to install the [Syncfusion.Xamarin.Core.WPF]() package for Xamarin.Forms WPF platform only.

**Method 2: Adding SfBorder reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfBorder control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfBorder assemblies manually from the installed location**

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
<tr>
<td>WPF</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.WPF.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

> **Note:** Refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download) setup guides.

> **Important:** Starting with v16.2.0.x, you need to include a license key for Syncfusion assemblies from the trial setup or NuGet feed. See the [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) guide for details on registering a license key in your Xamarin application.

## Launching the Application on Each Platform with SfBorder

To use SfBorder within an application, each platform requires initialization of the SfBorder renderer, as outlined below:

> **Note:** If using references from the Toolbox, further steps are unnecessary.
### Android and UWP

For Android and UWP, launching SfBorder requires only initializing the Xamarin.Forms Framework.
### iOS

To launch SfBorder in iOS, call `SfBorderRenderer.Init()` within the `FinishedLaunching` method of the AppDelegate class after the Xamarin.Forms Framework initialization and before `LoadApplication`.

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    Syncfusion.XForms.iOS.Border.SfBorderRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 

### Release Mode Issue on UWP Platform

UWP platforms have a known issue where custom controls are not rendered when deploying an application in `Release Mode`. Resolve this by initializing SfBorder assemblies in the `App.xaml.cs` file in the UWP project, as shown:

{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
    {
        …
    	    rootFrame.NavigationFailed += OnNavigationFailed;
    
        // you'll need to add `using System.Reflection;`
        List<Assembly> assembliesToInclude = new List<Assembly>();
    
        //Now, add all the assemblies your app uses                 
        assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Border.SfBorderRenderer).GetTypeInfo().Assembly);
    
        // replaces Xamarin.Forms.Forms.Init(e);        
        Xamarin.Forms.Forms.Init(e, assembliesToInclude);	
        …     
    }

{% endhighlight %}

### Windows Presentation Foundation (WPF)

Launch SfBorder in WPF by calling `SfBorderRenderer.Init()` in the `MainWindow` constructor after Xamarin.Forms initialization and before `LoadApplication`.
{% highlight c# %}

public partial class MainWindow : FormsApplicationPage
{
     public MainWindow()
     { 
            InitializeComponent();

            Forms.Init();

            Syncfusion.XForms.WPF.Border.SfBorderRenderer.Init();

            LoadApplication(new App());
     }
}

{% endhighlight %}

## Creating the SfBorder Control

The `SfBorder` control can be configured entirely in C# code or using XAML markup. Below are steps to create `SfBorder` and its elements:

### Adding Namespace for Referred Assemblies

{% tabs %}

{% highlight xaml %}

xmlns:border="clr-namespace:Syncfusion.XForms.Border;assembly=Syncfusion.Core.XForms" 

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Border; 

{% endhighlight %}

{% endtabs %}

### Adding SfBorder Control as Content of ContentPage

{% tabs %}
{% highlight xaml %}

<Grid>
<border:SfBorder 
   BorderColor="Red"
   BackgroundColor="#ffb6c1" 
   HorizontalOptions="Center" 
   VerticalOptions="Center"
   BorderWidth="3">
<Label 
  Text="Rose" 
  Margin="10" 
  Font="15"  />
</border:SfBorder>
</Grid>

{% endhighlight %}
{% highlight c# %}

using System;
using Syncfusion.XForms.Border;
using Xamarin.Forms;

namespace BorderGettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();

            Grid mainGrid = new Grid();

            // Create Border control
            SfBorder border = new SfBorder();
            border.VerticalOptions = LayoutOptions.Center;
            border.HorizontalOptions = LayoutOptions.Center;
            border.BorderColor = Color.Red;
            border.BackgroundColor = Color.FromHex("#ffb6c1");

            //Create Label control
            Label label = new Label();
            label.Text = "Rose";
            label.FontSize = 15;

            border.Content = label;
            mainGrid.Children.Add(border);
            this.Content = mainGrid;
        }
    }
}
 
{% endhighlight %}
{% endtabs %}

![Border Example](images/Xamarin_Forms_Border.png)

The complete Getting Started sample is available in [this](https://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted828010295.zip) link.
