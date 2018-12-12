---
layout: post
title: Getting started | SfBorder | Xamarin | Syncfusion
description: A quick tour to initial users on Syncfusion border control for Xamarin.Forms platform.
platform: xamarin
control: SfBorder
documentation: ug
---

# Getting Started

This section provides an overview for working with the SfBorder control for Xamarin.Forms and explains the entire process of creating a real-world application.

### Adding SfBorder reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org). To add the border control to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Core](https://www.nuget.org/packages/Syncfusion.Xamarin.Core), and then install it.

![Xamarin Forms SfBorder Nuget reference](images/Xamarin_Forms_Border_Nuget.png)

To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows).


N> Install the same version of the core NuGet in all the projects. The border control will be available in core NuGet from v16.4.0.x onwards.

I> From v16.2.0.x, you have to include a license key in your project if you reference Syncfusion assemblies from the trial setup or NuGet feed. Please refer to this [documentation](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your Xamarin applications and using our components.

## Launching an application on each platform with SfBorder.

To use the SfBorder control inside an application, each platform application must initialize the SfBorder renderer. This initialization step varies from platform to platform and is discussed in the following sections:

### Android

Android launches the SfBorder without any initialization, and it is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the SfBorder in iOS, call the `SfBorderRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework has been initialized and before the LoadApplication is called, as demonstrated in the following code example.

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

### Universal Windows Platform (UWP)

To launch SfBorder in UWP, call `SfBorderRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called, as demonstrated in the following code example.

{% highlight c# %}
public MainPage()
{
    …
    Syncfusion.XForms.UWP.Border.SfBorderRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %}

### Release mode issue in UWP platform

The known Framework issue in UWP platform is that the custom controls will not be rendered when deployed an application in `Release Mode`. It can be resolved by initializing the SfBorder assemblies in the `App.xaml.cs` file in the UWP project, as demonstrated in the following code example.

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

## Creating SfBorder control

The `SfBorder` control is configured entirely in C# code or in XAML markup. The following steps explain how to create a `SfBorder` and configure its elements.

### Adding namespace for referred assemblies

{% tabs %} 

{% highlight xaml %} 

xmlns:border="clr-namespace:Syncfusion.XForms.Border;assembly=Syncfusion.Core.XForms" 

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Border; 

{% endhighlight %}

{% endtabs %}

### Add the SfBorder control as the content of ContentPage.

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
            this.Content = stack;
        }
    }
}
 
{% endhighlight %}
{% endtabs %}

![border](images/Xamarin_Forms_Border.png)
