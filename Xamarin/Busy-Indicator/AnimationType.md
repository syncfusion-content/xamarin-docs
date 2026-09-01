---
layout: post
title: Animation Types in Xamarin Busy Indicator Control | Syncfusion
description: Learn about the various animation types supported by the Syncfusion Xamarin Busy Indicator (SfBusyIndicator) control.
platform: Xamarin
control: SfBusyIndicator
documentation: ug
---
# Animation Types in Xamarin Busy Indicator (SfBusyIndicator)

The [`AnimationType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_AnimationType) property of the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) allows users to select from 17 built-in animations. Available animations include: [`Ball`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Ball), [`HorizontalPulsingBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_HorizontalPulsingBox), [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Rectangle), [`Battery`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Battery), [`Globe`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Globe), [`SingleCircle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_SingleCircle), [`SlicedCircle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_SlicedCircle), [`DoubleCircle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_DoubleCircle), [`ECG`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_ECG), [`Print`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Print), [`Box`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Box), [`Gear`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Gear), [`Movie Timer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_MovieTimer), [`ZoomingTarget`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_ZoomingTarget), [`RollingBall`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_RollingBall), [`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Cupertino), and [`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Material).

N> Note that the [`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.AnimationTypes.html#Syncfusion_SfBusyIndicator_XForms_AnimationTypes_Material) animation is not supported on the UWP platform.

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

The following GIF showcases the various animations available in the BusyIndicator.

![AnimationTypes](images/animationtypes.gif)
