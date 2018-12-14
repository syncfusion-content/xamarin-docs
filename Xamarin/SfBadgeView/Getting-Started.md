---
layout: post
title: Getting Started with Syncfusion Badge View control for Xamarin.Forms
description: A quick tour about Syncfusion badge view control in Xamarin.Forms platform
platform: xamarin
control: SfBadgeView
documentation: ug
---

# Getting Started

This section explains the steps required to configure the [`SfBadgeView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.SfBadgeView.html) control and customize its elements.

## Adding SfBadgeView reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org/). To add badge view to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfBadgeView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfBadgeView), and then install it.

![Xamarin badge view nuget](getting-started_images/cg_nuget.png)

To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). If you prefer to manually reference the assemblies instead of using NuGet, refer to this [`documentation`](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfbadgeview) to learn about the dependent assemblies.

N> Install the same version of the badge view in all the projects.

I> If you reference Syncfusion assemblies from the trial setup or NuGet feed, you have to include a license key in your project. Please refer to this [documentation](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the application on each platform with badge view

To use the badge view in an application, each platform requires some additional configurations. The configurations vary from platform to platform and is discussed in the following sections:

### iOS

To launch the badge view in iOS, call the SfBadgeViewRenderer.Init() in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the LoadApplication is called as demonstrated in the following code sample.

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options) 
{ 
    … 
    global::Xamarin.Forms.Forms.Init();

    // Add the below line if you are using SfBadgeView.
     Syncfusion.XForms.iOS.BadgeView.SfBadgeViewRenderer.Init();

    LoadApplication(new App()); 
    …
}

{% endhighlight %}

### Universal Windows Platform (UWP)

You need to initialize the badge view assemblies in App.xaml.cs in UWP project as demonstrated in the following code samples. This is required to deploy the application with badge view in `Release` mode in UWP platform.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();

      // Add the below line if you are using SfBadgeView.
       assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.BadgeView.SfBadgeViewRenderer).GetTypeInfo().Assembly);

      Xamarin.Forms.Forms.Init(e, assembliesToInclude); 
   } 
  … 
}

{% endhighlight %}

### Android

The Android platform does not require any additional configuration to render the badge view.

## Adding namespace

Add the following namespace.

{% tabs %}

{% highlight xaml %}

    xmlns:badge ="clr-namespace:Syncfusion.XForms.BadgeView;assembly=Syncfusion.SfBadgeView.XForms"

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.XForms.BadgeView;

{% endhighlight %}

{% endtabs %}

## Initializing badge view

Create an instance for the badge view control, and add it as content.

{% tabs %}

{% highlight xaml %}

<badge:SfBadgeView>        
</badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}

//Initializing the badge view.
SfBadgeView sfBadgeView = new SfBadgeView();
	
{% endhighlight %}

{% endtabs %}

## Adding badge text

You can add text to badge view using the [`BadgeText`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.SfBadgeView~BadgeText.html) property.

{% tabs %}

{% highlight xaml %}

<badge:SfBadgeView>        
    <badge:SfBadgeView BadgeText="20+" />          
</badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}
   
SfBadgeView sfBadgeView = new SfBadgeView();
//Adding text to the badge view.
sfBadgeView.BadgeText = "20+";

{% endhighlight %}

{% endtabs %}

## Adding content

You can add an image, button, or label to the badge view using the [`Content`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.SfBadgeView~Content.html) property.

{% tabs %}

{% highlight xaml %}

<badge:SfBadgeView>
    <badge:SfBadgeView.Content>
        <Image Source="BadgeWhatsApp.png" />
    </badge:SfBadgeView.Content>   
</badge:SfBadgeView>       

{% endhighlight %}

{% highlight c# %}
	
SfBadgeView sfBadgeView = new SfBadgeView();
//Adding image to the content of the badge view.
Image image = new Image();
image.Source = "BadgeWhatsApp.png";
sfBadgeView.Content = image;

{% endhighlight %}
 
{% endtabs %}

## Adding badge type

You can change the colors of the badge view using the [`BadgeType`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.BadgeSetting~BadgeType.html) property. The badge supports the following eight different essential colors for various situations:

 * Dark
 * Error
 * Info
 * Light
 * None
 * Primary
 * Secondary
 * Success
 * Warning

{% tabs %}

{% highlight xaml %}

<badge:SfBadgeView>
    <badge:SfBadgeView.BadgeSettings>
        <badge:BadgeSetting BadgeType="Error"/>
    </badge:SfBadgeView.BadgeSettings>                  
</badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}
	
SfBadgeView sfBadgeView = new SfBadgeView();
//Adding badge type to the badge view.
BadgeSetting badgeSetting = new BadgeSetting();
badgeSetting.BadgeType = BadgeType.Error;
sfBadgeView.BadgeSettings = badgeSetting;

{% endhighlight %}

{% endtabs %}

## Adding badge position

The default position of the notification is `TopRight`. The position can be changed to the `TopLeft`, `BottomLeft`, and `BottomRight` using the [`BadgePosition`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.BadgeSetting~BadgePosition.html) property.

{% tabs %}

{% highlight xaml %}

<badge:SfBadgeView>
    <badge:SfBadgeView.BadgeSettings>
        <badge:BadgeSetting BadgePosition="TopRight" />
    </badge:SfBadgeView.BadgeSettings>        
</badge:SfBadgeView>       

{% endhighlight %}

{% highlight c# %}
	   
SfBadgeView sfBadgeView = new SfBadgeView();
//Adding badge position to the badge view.
BadgeSetting badgeSetting = new BadgeSetting();
badgeSetting.BadgePosition = BadgePosition.TopRight;
sfBadgeView.BadgeSettings = badgeSetting;

{% endhighlight %}

{% endtabs %}
 
## Adding badge icon

You can change the badge icon using the [`BadgeIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.BadgeSetting~BadgeIcon.html) property. Badge supports the following types of [`BadgeIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.BadgeSetting~BadgeIcon.html):

* Add
* Available
* Away
* Busy
* Delete 
* Dot
* None
* Prohibit1
* Prohibit2 

{% tabs %}

{% highlight xaml %}

<badge:SfBadgeView>
    <badge:SfBadgeView.BadgeSettings>
        <badge:BadgeSetting BadgeIcon="None"/>
    </badge:SfBadgeView.BadgeSettings>           
</badge:SfBadgeView>>

{% endhighlight %}

{% highlight c# %}
	
SfBadgeView sfBadgeView = new SfBadgeView();
//Adding badge icon to the badge view.
BadgeSetting badgeSetting = new BadgeSetting();
badgeSetting.BadgeIcon = BadgeIcon.None;
sfBadgeView.BadgeSettings = badgeSetting;

{% endhighlight %}

{% endtabs %}

The following code sample gives you the complete code for badge view with badge types and text.

{% tabs %}

{% highlight xaml %}

    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage"
             xmlns:badge ="clr-namespace:Syncfusion.XForms.BadgeView;assembly=Syncfusion.SfBadgeView.XForms">
        <ContentPage.Content>
            <badge:SfBadgeView BadgeText="20+">
                <badge:SfBadgeView.Content>
                    <Image Source="BadgeWhatsApp.png" HeightRequest="200" 
                           WidthRequest="200"/>
                </badge:SfBadgeView.Content>
                <badge:SfBadgeView.BadgeSettings>
                    <badge:BadgeSetting BadgeType="Error" BadgePosition="TopRight" 
                                        FontSize="30" Offset="-24,20"  BadgeIcon="None"/>
                 </badge:SfBadgeView.BadgeSettings>
            </badge:SfBadgeView>
        </ContentPage.Content>
    </ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;
using Syncfusion.XForms.BadgeView;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();

            //Initializing the badge view 
            SfBadgeView sfBadgeView = new SfBadgeView();
            sfBadgeView.BadgeText = "20+";

            //Adding the image to the content of the badge view.
            Image image = new Image();
            image.Source = "BadgeWhatsApp.png";
            image.HeightRequest = 200;
            image.WidthRequest = 200;
            sfBadgeView.Content = image;

            //Adding the badge type, position, and icon of the badge view.
            BadgeSetting badgeSetting = new BadgeSetting();
            badgeSetting.BadgeType = BadgeType.Error;
            badgeSetting.BadgePosition = BadgePosition.TopRight;
            badgeSetting.BadgeIcon = BadgeIcon.None;

            //Adding offset to adjust the badge view text.
            badgeSetting.Offset = new Point(-24, 20);
            badgeSetting.FontSize = 30;       
            sfBadgeView.BadgeSettings = badgeSetting;

            this.Content = sfBadgeView;
        }
    }
}

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the result of the above code sample.

![Xamarin badge view getting started](getting-started_images/Badgeview.png) 

You can download the complete `Getting started` sample.