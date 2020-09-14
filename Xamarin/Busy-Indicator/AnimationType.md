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

The `AnimationType` property for the SfBusyIndicator allows the users to set one of the 16 animations from the built-in animations. The different types of Animations are `Ball`, `Battery`, `Box`, `Cupertino` `DoubleCircle`,  `ECG`, `Gear`,  `Globe`, `HorizontalPulsingBox`, `Movie Timer`,  `Print`, `Rectangle`, `RollingBall`, `SingleCircle`, `SlicedCircle`, `ZoomingTarget`.

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
                                       Title="Ball"
                                       AnimationType="Ball" 
                                       ViewBoxHeight="150"
                                       ViewBoxWidth="150"
                                       BackgroundColor="LightGray"
                                       TextColor="Blue"/>
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
                ViewBoxWidth = 150,
                ViewBoxHeight = 150,
                Title = "Ball",
                BackgroundColor="LightGray",
                TextColor = Color.Blue
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

"Ball"

![Ball](images/Ball.JPG)

"Battery"

![Battery](images/Battery.JPG)

"Box"

![Box](images/Box.JPG)

"Cupertino"

![Cupertino](images/Cupertino.JPG)

"DoubleCircle"

![DoubleCircle](images/DoubleCircle.JPG)

"ECG"

![ECG](images/ECG.JPG)

"Gear"

![Gear](images/Gear.JPG)

"Globe"

![Globe](images/Globe.JPG)

"HorizontalPulsingBox"

![HorizontalPulsingBox](images/HorizontalPulsingBox.JPG)

"MovieTimer"

![MovieTimer](images/MovieTimer.JPG)

"Print"

![Print](images/Print.JPG)

"Rectangle"

![Rectangle](images/Rectangle.JPG)

"RollingBall"

![RollingBall](images/RollingBall.JPG)

"SingleCircle"

![SingleCircle](images/SingleCircle.JPG)

"SlicedCircle"

![SlicedCircle](images/SlicedCircle.JPG)

"ZoomingTarget"

![ZoomingTarget](images/ZoomingTarget.JPG)