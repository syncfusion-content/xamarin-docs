---
layout: post
title: Getting Started with Syncfusion Badge View control for Xamarin.Forms
description: A quick tour about Syncfusion badge view control in Xamarin.Forms platform
platform: xamarin
control: SfBadgeView
documentation: ug
---

# Getting Started

This section explains the steps required to configure the badge view control and customize its elements.

## Adding SfBadgeView reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org/). To add badge view to your project, open the NuGet package manager in Visual Studio, search for `Syncfusion.Xamarin.SfBadgeView`, and then install it.

To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). If you prefer to manually reference the assemblies instead of using NuGet, refer to this `documentation` to learn about the dependent assemblies.

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

    SfBadgeView sfBadgeView = new SfBadgeView();

    this.Content = sfBadgeView;
	
{% endhighlight %}

{% endtabs %}

## Adding badge text

You can add text to badge view using the `BadgeText` property.

{% tabs %}

{% highlight xaml %}

    <badge:SfBadgeView BadgeText="20+">
            
    </badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}

    SfBadgeView sfBadgeView = new SfBadgeView();

    sfBadgeView.BadgeText = "20+";

    this.Content = sfBadgeView;

{% endhighlight %}

{% endtabs %}

## Adding content

You can add an image, button, or label to the badge view using the `Content` property.

{% tabs %}

{% highlight xaml %}

    <badge:SfBadgeView>

    <badge:SfBadgeView.Content>

    <Image Source="BadgeWhatsApp.png" HeightRequest="200" WidthRequest="200"/>

    </badge:SfBadgeView.Content>
            
    </badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}
	
    SfBadgeView sfBadgeView = new SfBadgeView();

    Image image = new Image();

    image.Source = "BadgeWhatsApp.png";

    image.HeightRequest = 200;

    image.WidthRequest = 200;

    sfBadgeView.Content = image;

{% endhighlight %}
 
{% endtabs %}

## Adding badge type

You can change the colors of the badge view using the `BadgeType` property. The badge supports the following eight different essential colors for various situations:

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

            BadgeSetting badgeSetting = new BadgeSetting();

            badgeSetting.BadgeType = BadgeType.Error;

            sfBadgeView.BadgeSettings = badgeSetting;

            this.Content = sfBadgeView; 

{% endhighlight %}

{% endtabs %}

## Adding badge position

The default position of the notification is `TopRight`. The position can be changed to the `TopLeft`, `BottomLeft`, and `BottomRight` using the `BadgePosition` property.

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

            BadgeSetting badgeSetting = new BadgeSetting();

            badgeSetting.BadgePosition = BadgePosition.TopRight;

            sfBadgeView.BadgeSettings = badgeSetting;

            this.Content = sfBadgeView;

{% endhighlight %}

{% endtabs %}
 
## Adding badge icon

You can change the badge icon using the `BadgeIcon` property. Badge supports the following types of `BadgeIcon`:

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

            BadgeSetting badgeSetting = new BadgeSetting();

            badgeSetting.BadgeIcon = BadgeIcon.None;

            sfBadgeView.BadgeSettings = badgeSetting;

           this.Content = sfBadgeView; 

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

        <badge:SfBadgeView BadgeText="20+" HeightRequest="200" WidthRequest="200">

            <badge:SfBadgeView.Content>

                <Image Source="BadgeWhatsApp.png" HeightRequest="200" WidthRequest="200"/>

            </badge:SfBadgeView.Content>

            <badge:SfBadgeView.BadgeSettings>

                <badge:BadgeSetting BadgeType="Error" BadgePosition="TopRight" FontSize="30" Offset="-24,20"  BadgeIcon="None"/>

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

            SfBadgeView sfBadgeView = new SfBadgeView();

             sfBadgeView.HeightRequest = 200;

            sfBadgeView.WidthRequest = 200;

            sfBadgeView.BadgeText = "20+";

            Image image = new Image();

            image.Source = "BadgeWhatsApp.png";

            image.HeightRequest = 200;

            image.WidthRequest = 200;

            sfBadgeView.Content = image;

            BadgeSetting badgeSetting = new BadgeSetting();

            badgeSetting.BadgeType = BadgeType.Error;

            badgeSetting.BadgePosition = BadgePosition.TopRight;

            badgeSetting.Offset = new Point(-24, 20);

            badgeSetting.FontSize = 30;

            badgeSetting.BadgeIcon = BadgeIcon.None;

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