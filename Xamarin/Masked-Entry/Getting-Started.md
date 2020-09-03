---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.Forms 
description: A quick tour to initial users for getting started with Syncfusion SfMaskedEdit control for Xamarin.Forms
platform: Xamarin
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit
---

# Getting Started with SfMaskedEdit 

This section explains you the steps required to configure a [`SfMaskedEdit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html) control in a real-time scenario and provides a walk-through on some of the customization features available in [`SfMaskedEdit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html) control.

## Adding SfMaskedEdit reference

You can add SfMaskedEdit reference using one of the following methods:

**Method 1: Adding SfMaskedEdit reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfMaskedEdit to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfMaskedEdit](https://www.nuget.org/packages/Syncfusion.Xamarin.SfMaskedEdit), and then install it.

![Adding SfMaskedEdit reference from NuGet](SfMaskedEditImages/Adding SfMaskedEdit reference.png)

N> Install the same version of SfMaskedEdit NuGet in all the projects.

**Method 2: Adding SfMaskedEdit reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfMaskedEdit control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfMaskedEdit assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

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

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

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

### Additional step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled and it is for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the SfMaskedEdit assembly at `OnLaunched` overridden method of the `App` class in UWP project is the suggested work around, as demonstrated in the following code example.

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

The SfMaskedEdit control is configured entirely in C# code or by using XAML markup. The following steps explain how to create a SfMaskedEdit and configure its elements:

### Add namespace for referred assemblies

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="clr-namespace:Syncfusion.XForms.MaskedEdit;assembly=Syncfusion.SfMaskedEdit.XForms"
{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.MaskedEdit;
{% endhighlight %}
{% endtabs %}

### Refer SfMaskedEdit control with declared suffix name for Namespace

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

## Masking the input

To mask the input, set the [`Mask`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.SfMaskedEdit.html#Syncfusion_XForms_MaskedEdit_SfMaskedEdit_Mask) property as follows:

{% tabs %}
{% highlight xaml %}
<syncmaskededit:SfMaskedEdit x:Name="maskedEdit" Mask="00/00/0000"/>
{% endhighlight %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.Mask = "00/00/0000";
{% endhighlight %}
{% endtabs %}

This mask expression allows only numeric inputs in the places of 0.

Refer to this [link](masktype.html) to know more about the Mask characters and Mask Types available in SfMaskedEdit control.

Run the project and check if you get the following output to make sure that you have configured your project properly to add `SfMaskedEdit`.

![Xamarin.Forms masked edit](SfMaskedEditImages/GettingStarted.png)

You can find the complete getting started sample from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted449308990).
