---
layout: post
title: Getting Started with Xamarin Effects View Control | Syncfusion
description: Learn how to get started with the Syncfusion Xamarin Effects View (SfEffectsView) control, including its elements and configuration.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Getting Started with Xamarin Effects View (SfEffectsView)

This section outlines the steps required to configure the SfEffectsView control.

## Assembly Deployment

After installing [Essential Studio® for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can locate the necessary assemblies in the installation folders at `{Syncfusion Essential Studio Installed location}\Essential Studio\{Version #}\Xamarin\lib`. For example: `C:\Program Files (x86)\Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib`.

> **Note:** Assemblies are also available in the unzipped package location at `Documents/Syncfusion/{Version #}/Xamarin/lib` on Mac.

## Adding SfEffectsView Reference

You can add the SfEffectsView reference using one of the following methods:

**Method 1: Adding SfEffectsView Reference from NuGet**

Syncfusion Xamarin components are available on [nuget.org](https://www.nuget.org/). To add SfEffectsView to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Core](https://www.nuget.org/packages/Syncfusion.Xamarin.Core), and install it.

![Add Packages](Getting-Started_images/Reference.png)

**Method 2: Adding SfEffectsView Reference from Toolbox**

Syncfusion provides a Xamarin Toolbox. Using this toolbox, you can drag the SfEffectsView control to the XAML page, automatically installing the required NuGet packages and adding the namespace. Refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox) for installation details.

**Method 3: Adding SfEffectsView Assemblies Manually**

If you prefer to manually reference the assemblies instead of using NuGet, add the following assemblies to the respective projects:

Location : {Installed location}/{version}/Xamarin/lib

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

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching an application on each platform with SfEffectsView

To use the SfEffectsView inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and are discussed in the following sections:

N> If you are adding the references from toolbox, the following steps are not needed.

### iOS

To launch the SfEffectsView in iOS, call the `SfEffectsViewRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the `LoadApplication` method, as demonstrated below.

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    Syncfusion.XForms.iOS.EffectsView.SfEffectsViewRenderer.Init();
    LoadApplication(new App());
    return base.FinishedLaunching(app, options);
} 

{% endhighlight %}

### Universal Windows Platform (UWP)

To deploy the effects view in `Release` mode, initialize the core assemblies in the App.xaml.cs file in the UWP project as shown below.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();
      assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.EffectsView.SfEffectsViewRenderer).GetTypeInfo().Assembly);
      Xamarin.Forms.Forms.Init(e, assembliesToInclude);
   } 
   … 
}

{% endhighlight %}

### Android

The Android platform does not require additional configuration to render the SfEffectsView control.

## Initializing SfEffectsView

Import the [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control namespace into the respective page.

{% tabs %} 

{% highlight xaml %} 

xmlns:syncEffectsView="clr-namespace:Syncfusion.XForms.EffectsView;assembly=Syncfusion.Core.XForms"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.EffectsView;

{% endhighlight %}

{% endtabs %}

Then, initialize the SfEffectsView as demonstrated below.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView CornerRadius="0,25,0,25">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

SfEffectsView effectsView = new SfEffectsView();
effectsView.CornerRadius = new Thickness(0, 25, 0, 25);

{% endhighlight %}

{% endtabs %}

![EffectsView Initialization](Getting-Started_images/RippleEffect.gif)

You can find a complete getting started sample from this [link](https://github.com/SyncfusionExamples/Getting-started-of-SfEffectsView-in-Xamarin.Forms).

## See Also

- [How to get the selected item from ListView while using SfEffectsView within ItemTemplate](https://support.syncfusion.com/kb/article/10193/how-to-get-the-selected-item-from-listview-while-using-effectsview-within-itemtemplate)
- [How to use effects view in SfListView](https://support.syncfusion.com/kb/article/9569/how-to-use-the-effects-view-in-xamarinforms-listview-sflistview)
