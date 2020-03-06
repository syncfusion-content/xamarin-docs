---
layout: post
title: AnimationTypes in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: The following section will explain about different types of animation available in Xamarin.Forms SfBusyIndicator 
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Animation Type in SfBusyIndicator

## Animation Type in Xamarin BusyIndicator (SfBusyIndicator)

The `AnimationType` property for the SfBusyIndicator allows the users to set one of the 15 animations from the built-in animations. The different types of Animations are `Ball`, `HorizontalPulsingBox`, `Rectangle`, `Battery`, `Globe`, `SingleCircle`, `SlicedCircle`, `DoubleCircle`, `ECG`, `Print`, `Box`, `Gear`, `Movie Timer`, `ZoomingTarget`, and `RollingBall`.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <busyindicator:SfBusyIndicator x:Name="busyindicator" 
                                       Title="Loading..."
                                       AnimationType="Ball" 
                                       ViewBoxHeight="100"
                                       ViewBoxWidth="100"
                                       BackgroundColor="Blue"
                                       TextColor="White"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfBusyIndicator busyIndicator = new SfBusyIndicator()
            {
                AnimationType = AnimationTypes.Ball,
                ViewBoxWidth = 100,
                ViewBoxHeight = 100,
                Title = "Loading...",
                BackgroundColor="Blue",
                TextColor = Color.White
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![ball](images/ball1.png)

The Busy Indicator with Ball type animation 
{:.caption}

![HorizontalPulsingBox](images/HorizontalPulsingBox.png) 

The Busy Indicator with HorizontalPulsingBox type animation 
{:.caption}

![rectangle](images/rectangle.png) 

The Busy Indicator with Rectangle type animation 
{:.caption}
 
![battery](images/battery.png) 

The Busy Indicator with Battery type animation 
{:.caption}
 
![globe](images/globe.png) 

The Busy Indicator with Globe type animation 
{:.caption}
 
![singlecircle](images/singlecircle.png) 

The Busy Indicator with SingleCircle type animation 
{:.caption}

![SlicedCircle](images/SlicedCircle.png) 

The Busy Indicator with SlicedCircle type animation 
{:.caption}
 
![doublecircle](images/doublecircle.png) 

The Busy Indicator with DoubleCircle type animation 
{:.caption}
 
![ECG](images/ecg.png) 

The Busy Indicator with ECG type animation 
{:.caption}
 
![Print](images/print.png) 

The Busy Indicator with Print type animation 
{:.caption}

![Box](images/box.png) 

The Busy Indicator with Box type animation 
{:.caption}

![Gear](images/gear.png) 

The Busy Indicator with Gear type animation 
{:.caption}

![Timer](images/timer.png) 

The Busy Indicator with MovieTimer type animation 
{:.caption}

![Zooming target](images/zoomingtarget.png) 

The Busy Indicator with ZoomingTarget type animation 
{:.caption}

![Rolling ball](images/rollingball.png) 

The Busy Indicator with RollingBall type animation 
{:.caption}

![Cupertino](images/Cupertino.png) 

The Busy Indicator with Cupertino type animation 
{:.caption}






 
