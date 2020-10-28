---
layout: post
title: Getting Started with Syncfusion Backdrop Page
description: How to initialze the Syncfusion backdrop page control in Xamarin.Forms platform and it's customization.
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Getting Started with Xamarin.Forms Backdrop Page

This section explains the steps required to configure the backdrop page.

## Adding SfBackdropPage reference

You can add SfBackdropPage reference using one of the following methods:

**Method 1: Adding SfBackdropPage reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfBackdropPage to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfBackdrop](https://www.nuget.org/packages/Syncfusion.Xamarin.SfBackdrop), and then install it.

![Adding Xamarin.Forms Backdrop page reference](Getting-Started_images/Adding_SfBackdropPage_reference.png)

N> Install the same version of SfBackdropPage NuGet in all the projects.

**Method 2: Adding SfBackdropPage assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location : {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfBackdrop.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfBackdrop.XForms.Android.dll<br/>Syncfusion.SfBackdrop.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfBackdrop.XForms.iOS.dll<br/>Syncfusion.SfBackdrop.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfBackdrop.XForms.UWP.dll<br/>Syncfusion.SfBackdrop.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launch an application on each platform with backdrop page

To use the backdrop page inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and are discussed in the following sections:

N> If you are adding the references from toolbox, below steps are not needed.

### iOS

To launch the backdrop page in iOS, call the `SfBackdropPageRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the `LoadApplication` method is called as demonstrated in the following code sample.


{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    SfBackdropPageRenderer.Init();
    LoadApplication(new App());
    return base.FinishedLaunching(app, options);
} 

{% endhighlight %}


### Universal Windows Platform (UWP)

To deploy the backdrop page in `Release` mode, initialize the backdrop page assemblies in the App.xaml.cs file in the UWP project as demonstrated in the following code sample.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();
      assembliesToInclude.Add(typeof(SfBackdropPageRenderer).GetTypeInfo().Assembly);
      Xamarin.Forms.Forms.Init(e, assembliesToInclude);
   } 
   … 
}

{% endhighlight %}

### Android

Android platform does not require any additional configuration to render the backdrop page.

## Initialize backdrop page

Create a page and import the SfBackdropPage namespace along with [XAML namespaces](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/xaml/namespaces) in Xamarin.Forms.

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    Title="Menu">
</backdrop:SfBackdropPage>

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Backdrop;	
namespace BackdropGettingStarted
{
    public partial class BackdropSamplePage : SfBackdropPage
    {
        public BackdropSamplePage()
        {
            InitializeComponent();
	    this.Title = "Menu";
        }
    }
}

{% endhighlight %}

{% endtabs %}

>**NOTE**
[`Title`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.page.title?view=xamarin-forms) and [`ToolBarItems`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.page.toolbaritems?view=xamarin-forms) properties of the [`Page`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.page?view=xamarin-forms) can used to customize the  appearance of header.

### Configure header

Page header for the backdrop appears only when adding backdrop as a child of NavigationPage. To know more about it, refer to [header configuration](https://help.syncfusion.com/xamarin/Sfbackdroppage/header-configuration).
 
## Add back layer content
The back layer holds actionable content (navigation or filtration), which is relevant to the front layer. The back layer will either fill the entire background or occupy the background based on the content height.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.BackLayer>
        <backdrop:BackdropBackLayer>
            <StackLayout>
                <ListView>
                    <ListView.ItemsSource>
                        <x:Array Type="{x:Type x:String}">
                            <x:String>Appetizers</x:String>
                            <x:String>Soups</x:String>
                            <x:String>Desserts</x:String>
                            <x:String>Salads</x:String>
                        </x:Array>
                    </ListView.ItemsSource>
                </ListView>
            </StackLayout>
        </backdrop:BackdropBackLayer>
 </backdrop:SfBackdropPage.BackLayer> 

{% endhighlight %}

{% highlight C# %} 

this.BackLayer = new BackdropBackLayer
{
    Content = new StackLayout
    {
        Children =
        {
            new ListView
            {
                ItemsSource = new string[] { "Appetizers", "Soups", "Desserts" ,"Salads"}
            }
        }
    }
};


{% endhighlight %}

{% endtabs %}

## Add front layer content
The front layer always appears in front of the back layer. It is displayed to the full width and holds primary content.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer>
            <Grid BackgroundColor="WhiteSmoke" VerticalOptions="FillAndExpand" />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 

{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
{
	Content = new Grid
    {
		BackgroundColor = Color.WhiteSmoke,
		VerticalOptions = LayoutOptions.FillAndExpand
    }
};

{% endhighlight %}

{% endtabs %}

## Reveal and conceal the back layer

The following options are provided in backdrop to reveal and conceal the back layer:

* **Programmatically** - Reveals back layer by setting the [`IsBackLayerRevealed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html#Syncfusion_XForms_Backdrop_SfBackdropPage_IsBackLayerRevealed) property to true. By default, it is set to false.
* **Touch interaction** - Reveals back layer by clicking the tool bar icon at the top-right corner of navigation bar header. The Hamburger (or menu ) icon reveals and the Close icon conceals the back layer. When adding the backdrop as a child of MasterDetailPage, the Hamburger and Close icons will be replaced by expand (or down arrow) and collapse (or up arrow) icons, respectively.
* **Swipe or fling action** - Reveals back layer by swipe/fling action on the front layer to the required direction. Swipe downwards to reveal, and swipe upwards to conceal the back layer.  The swipe/fling action will be handled only on the top of the front layer to the [`RevealedHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.BackdropFrontLayer.html#Syncfusion_XForms_Backdrop_BackdropFrontLayer_RevealedHeight).

To know more information about reveal height customization ,refer this [link](https://help.syncfusion.com/xamarin/sfbackdroppage/revealingheight-customization).

![Reveal and conceal back layer](Getting-Started_images/Backdrop_reveal.gif)

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    IsBackLayerRevealed="True">
</backdrop:SfBackdropPage>
 
{% endhighlight %}

{% highlight C# %} 

#region Constructor

public BackdropSamplePage()
{
    this.IsBackLayerRevealed = true;
}

#endregion

{% endhighlight %}

{% endtabs %}

You can find the complete getting started sample from this [link.]( http://files2.syncfusion.com/Xamarin.Forms/Samples/BackdropGettingStarted.zip)

## See also

[How to reveal a back layer based on a gesture in a Xamarin.Forms application]( https://www.syncfusion.com/kb/11658/how-to-reveal-a-back-layer-based-on-a-gesture-in-a-xamarin-forms-application)