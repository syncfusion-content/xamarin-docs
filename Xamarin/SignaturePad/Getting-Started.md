---
layout: post
title: Getting Started with Xamarin SignaturePad Control | Syncfusion
description: Learn how to get started with the Syncfusion Xamarin SignaturePad (SfSignaturePad) control, including its configuration and key elements.
platform: Xamarin
control: SfSignaturePad
documentation: ug
---

# Getting Started with Xamarin SignaturePad (SfSignaturePad)

This section explains the steps required to configure the SignaturePad.

## Assembly Deployment

After installing [Essential Studio® for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can find all the required assemblies in the installation folders at {Syncfusion Essential Studio Installed location}\Essential Studio\\{Version #}\Xamarin\lib.

E.g.: C:\Program Files (x86) \Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

> Note: Assemblies can be found in the unzipped package location (Documents/Syncfusion/{Version #}/Xamarin/lib) on a Mac.

## Adding SfSignaturePad Reference

You can add the SignaturePad reference using one of the following methods:

**Method 1: Adding SfSignaturePad Reference from NuGet.org**

Syncfusion Xamarin components are available on [nuget.org](https://www.nuget.org/). To add SignaturePad to your project, open the NuGet Package Manager in Visual Studio, search for [Syncfusion.Xamarin.SfSignaturePad](https://www.nuget.org/packages/Syncfusion.Xamarin.SfSignaturePad), and install it.

> Note: Install the same version of `SfSignaturePad` NuGet in all projects.

![Adding SignaturePad reference from NuGet](images/NugetPackage.png)

**Method 2: Adding SfSignaturePad Reference from Toolbox**

Syncfusion also provides a Xamarin Toolbox. By using this toolbox, you can drag the [`SfSignaturePad`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html) control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install the Syncfusion Xamarin Toolbox, refer to this [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfSignaturePad Assemblies Manually from the Installed Location**

If you prefer to manually reference the assemblies instead of using NuGet, add the following assemblies to the respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfSignaturePad.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfSignaturePad.XForms.dll<br/>Syncfusion.SfSignaturePad.XForms.Android.dll<br/>Syncfusion.Core.XForms.dll
<br/>Syncfusion.Core.XForms.Android.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfSignaturePad.XForms.dll<br/>Syncfusion.SfSignaturePad.XForms.iOS.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/></td>
</tr>
</table>

**Method 4: Adding SfSignaturePad Dependency Package**

Additionally, you need to install version 1.68.0 of the [SkiaSharp](https://www.nuget.org/packages/SkiaSharp.Views.Forms/1.68.0) NuGet package in all projects.

> Note: For more information on obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

## Launching the Application on Each Platform with SfSignaturePad

To use the SignaturePad in an application, each platform requires specific configurations. These configurations vary by platform and are discussed in the following sections:

> Note: If you add references from the toolbox, this step is not needed.

### iOS

To launch the [`SfSignaturePad`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html) on iOS, call `SfSignaturePadRenderer.Init()` in the `FinishedLaunching` method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before `LoadApplication` is called, as demonstrated in the following code sample.

{% highlight C# %} 

 public override bool FinishedLaunching(UIApplication app, NSDictionary options)
 {
            global::Xamarin.Forms.Forms.Init();
            LoadApplication(new App());
            // Add below line if you are using Signature Pad.
            Syncfusion.XForms.iOS.SignaturePad.SfSignaturePadRenderer.Init();
            return base.FinishedLaunching(app, options);
 }

{% endhighlight %}

### Android

The Android platform does not require any additional configurations to render the SignaturePad.

> Note: SignaturePad support has not been provided for the UWP platform.

## Adding a Namespace

Add the following namespace to your project.

{% tabs %}

{% highlight xaml %}

    xmlns:signature="clr-namespace:Syncfusion.XForms.SignaturePad;assembly=Syncfusion.SfSignaturePad.XForms"

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.XForms.SignaturePad;

{% endhighlight %}

{% endtabs %}

## Creating an SfSignaturePad Control

Create an instance of the SignaturePad control and add it as content.

{% tabs %}

{% highlight xaml %}

<signature:SfSignaturePad>        
</signature:SfSignaturePad>

{% endhighlight %}

{% highlight c# %}

// Creating an Signature Pad control.
SfSignaturePad signature = new SfSignaturePad();
Content = signature;
	
{% endhighlight %}

{% endtabs %}

## Getting Started with a SignaturePad Control

The SignaturePad control can be configured entirely in C# code or in XAML markup. The following steps explain how to create a SignaturePad and configure its elements.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             mc:Ignorable="d"
             xmlns:signature="clr-namespace:Syncfusion.XForms.SignaturePad;assembly=Syncfusion.SfSignaturePad.XForms"
             x:Class="SfSignaturePadGettingStarted.MainPage">

    <StackLayout>
        <Label Text="Input Your Signature"/>
        <Frame>
            <signature:SfSignaturePad HeightRequest="250"/>
        </Frame>
    </StackLayout>

</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System.ComponentModel;
using Xamarin.Forms;
using Syncfusion.XForms.SignaturePad;

namespace SfSignaturePadGettingStarted
{
    // Learn more about making custom code visible in the Xamarin.Forms previewer
    // by visiting https://aka.ms/xamarinforms-previewer
    [DesignTimeVisible(false)]
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();

            StackLayout stack = new StackLayout();
            Label text = new Label() { Text = "Input Your Signature" };
            Frame frame = new Frame();
            SfSignaturePad signature = new SfSignaturePad();
            signature.HeightRequest = 250;
            frame.Content = signature;
            stack.Children.Add(text);
            stack.Children.Add(frame);
            this.Content = stack;
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

![Xamarin SignaturePad](images/signature.png)

> Note: View the [sample](https://github.com/SyncfusionExamples/xamarin-sfsignaturepad-[REDACTED]) on GitHub.
