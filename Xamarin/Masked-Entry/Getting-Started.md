---
layout: post
title: Getting Started with Xamarin Masked Entry Control | Syncfusion
description: Learn about starting with the Syncfusion Xamarin Masked Entry (SfMaskedEdit) control, its elements, and more.
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Getting Started with Xamarin Masked Entry (SfMaskedEdit)

This section explains the steps required to configure an [`SfMaskedEdit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html) control in a real-time scenario and provides a walkthrough of some customization features available in the control.

## Assembly Deployment

After installing [Essential Studio® for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can find all the required assemblies in the installation folders: `{Syncfusion Essential Studio Installed location}\Essential Studio\{Version #}\Xamarin\lib`.

E.g.: C:\Program Files (x86) \Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

N> Assemblies can be found in unzipped package location(Documents/Syncfusion/{Version #}/Xamarin/lib) in Mac.

## Adding SfMaskedEdit Reference

You can add the `SfMaskedEdit` reference using one of the following methods:

**Method 1: Adding SfMaskedEdit Reference from nuget.org**

Syncfusion Xamarin components are available on [nuget.org](https://www.nuget.org/). To add `SfMaskedEdit` to your project, open the NuGet Package Manager in Visual Studio, search for [Syncfusion.Xamarin.SfMaskedEdit](https://www.nuget.org/packages/Syncfusion.Xamarin.SfMaskedEdit), and then install it.

![Adding SfMaskedEdit reference from NuGet](SfMaskedEditImages/Adding SfMaskedEdit reference.png)

> **Note:** Install the same version of the `SfMaskedEdit` NuGet package in all projects.

**Method 2: Adding SfMaskedEdit Reference from Toolbox**

Syncfusion provides a Xamarin Toolbox. Using this toolbox, you can drag the `SfMaskedEdit` control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. For installing the Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfMaskedEdit Assemblies Manually from the Installed Location**

If you prefer to manually reference the assemblies instead of using NuGet, add the following assemblies to the respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfMaskedEdit.XForms.Android.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfMaskedEdit.XForms.iOS.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfMaskedEdit.XForms.UWP.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> After adding the reference, an additional step is required for iOS and UWP projects. If you are adding the references from toolbox, this step is not needed.

### Additional step for iOS

To launch SfMaskedEdit in iOS, call the `SfMaskedEditRenderer.Init()` in `FinishedLaunching` overridden method of `AppDelegate` class in iOS Project, as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    SfMaskedEditRenderer.Init();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}

### Additional Step for UWP

This step is required if deploying the application in Release mode with the .NET native toolchain enabled and addresses the known framework issue "Custom controls not rendering in Release mode" on the UWP platform. Initialize the `SfMaskedEdit` assembly in the `OnLaunched` overridden method of the `App` class in the UWP project, as shown below.

{% tabs %}
{% highlight c# %}
protected override void OnLaunched(LaunchActivatedEventArgs e)
{

    ..... 

    rootFrame.NavigationFailed += OnNavigationFailed;
    // you'll need to add `using System.Reflection;` 
    List<Assembly> assembliesToInclude = new List<Assembly>();
    //Now, add all the assemblies your app uses 
    assembliesToInclude.Add(typeof(SfMaskedEditRenderer).GetTypeInfo().Assembly);
    // replaces Xamarin.Forms.Forms.Init(e);
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);

    ..... 

}
{% endhighlight %}
{% endtabs %}


## Create a Simple SfMaskedEdit

The `SfMaskedEdit` control is configured entirely in C# or using XAML markup. The following steps demonstrate how to create an `SfMaskedEdit` and configure its elements:

### Add Namespace for Referred Assemblies

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="clr-namespace:Syncfusion.XForms.MaskedEdit;assembly=Syncfusion.SfMaskedEdit.XForms"
{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.MaskedEdit;
{% endhighlight %}
{% endtabs %}

### Reference SfMaskedEdit Control with Declared Suffix Name for Namespace

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:syncmaskededit="clr-namespace:Syncfusion.XForms.MaskedEdit;assembly=Syncfusion.SfMaskedEdit.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <StackLayout Margin= "0,100,0,0">
            <syncmaskededit:SfMaskedEdit x:Name="maskedEdit" />
        </StackLayout>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.MaskedEdit;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
			stackLayout.Margin = new Thickness(0, 100, 0, 0);
            SfMaskedEdit maskedEdit = new SfMaskedEdit();
            stackLayout.Children.Add(maskedEdit);
            this.Content = stackLayout;
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Masking the Input

To mask the input, set the [`Mask`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_Mask) property as shown below:

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" Mask="00/00/0000"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
{% endhighlight %}
{% endtabs %}

This mask expression allows only numeric inputs where `0` is specified.

For more details about mask characters and types available in the `SfMaskedEdit` control, refer to this [link](masktype.html).

Run the project and verify that you obtain the following output to confirm proper configuration of the `SfMaskedEdit`.
![Xamarin.Forms masked edit](SfMaskedEditImages/GettingStarted.png)

A complete getting started sample is available in this [link](https://github.com/SyncfusionExamples/Getting-Started-Xamarin-Masked-edit).
