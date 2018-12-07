---
layout: post
title: Getting Started for Essential Xamarin.Forms backdrop page
description: How to initialze a backdrop page.
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Getting Started

This section explains the steps required to configure the backdrop page control.

## Adding backdrop page reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org). To add the backdrop page control to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfBackdrop](https://www.nuget.org/packages/Syncfusion.Xamarin.SfBackdrop), and then install it.


To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows).


I> From v16.2.0.x, you have to include a license key in your project if you reference Syncfusion assemblies from the trial setup or NuGet feed. Please refer to this [documentation](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your Xamarin applications and using our components.

## Launching an application on each platform with backdrop page

To use the backdrop page inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and are discussed in the following sections:

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

To deploy the backdrop page in `Release` mode, initialize the core assemblies in the App.xaml.cs file in the UWP project as demonstrated in the following code samples.

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

Android platform does not require any additional configuration to render the backdrop page control.

## Initializing text input layout

Import the SfBackdropPage control namespace in respective page as demonstrated in the following code sample.

{% tabs %} 

{% highlight xaml %} 

xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Backdrop;

{% endhighlight %}

{% endtabs %}

Now add the SfBackdropPage control with a required optimal name by using the included namespace.

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage  xmlns="http://xamarin.com/schemas/2014/forms"
        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
       xmlns:local="clr-namespace:GettingStarted"
        x:Class="GettingStarted.Backdrop" 
        xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
        >		
</backdrop:SfBackdropPage>

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Backdrop;
namespace GettingStarted
{
    public partial class Backdrop : SfBackdropPage
    {
        public Backdrop()
        {
            InitializeComponent();
         }
    }
}

{% endhighlight %}

{% endtabs %}

### Adding back layer content
Add any layouts such as StackLayout, AbsoluteLayout , RelativeLayout , or Grid to the back layer of backdrop control.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage>
        <backdrop:SfBackdropPage.BackLayer>
            <backdrop:BackdropBackLayer>
                <Grid />
            </backdrop:BackdropBackLayer>
        </backdrop:SfBackdropPage.BackLayer>
</backdrop:SfBackdropPage>
 

{% endhighlight %}

{% highlight C# %} 

var backdrop = new SfBackdropPage();
var backdropBackLayer = new BackdropBackLayer();
backdropBackLayer = new Grid();
backdrop.BackLayer = backdropBackLayer;


{% endhighlight %}

{% endtabs %}

### Adding front layer content
Add any layouts such as StackLayout, AbsoluteLayout , RelativeLayout , or Grid to the front layer of backdrop control.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage>
        <backdrop:SfBackdropPage.FrontLayer>
            <backdrop:BackdropFrontLayer>
                <Grid />
            </backdrop:BackdropFrontLayer>
        </backdrop:SfBackdropPage.FrontLayer>
</backdrop:SfBackdropPage>
 

{% endhighlight %}

{% highlight C# %} 

var backdrop = new SfBackdropPage();
var backdropFrontLayer = new BackdropFrontLayer();
backdropFrontLayer = new Grid();
backdrop.FrontLayer = backdropFrontLayer;


{% endhighlight %}

{% endtabs %}

## Reveal and conceal front layer

The visibility of the back layer can be disabled by setting the IsBackLayerRevealed property to false. By default, it is set to `true`.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage IsBackLayerRevealed = “false”>
</backdrop:SfBackdropPage>
 
{% endhighlight %}

{% highlight C# %} 

Var backdrop = new SfBackdropPage();
Backdrop.IsBackLayerRevealed = false;

{% endhighlight %}

{% endtabs %}
